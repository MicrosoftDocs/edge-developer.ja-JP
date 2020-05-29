---
description: 名前を指定して、新しい JavaScript 関数を作成します。
title: JsCreateNamedFunction 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d963fe196b8e56394e22501ed3898a0d887a3d3b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569363"
---
# <span data-ttu-id="2bd5d-103">JsCreateNamedFunction 関数</span><span class="sxs-lookup"><span data-stu-id="2bd5d-103">JsCreateNamedFunction Function</span></span>
<span data-ttu-id="2bd5d-104">名前を指定して、新しい JavaScript 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-104">Creates a new JavaScript function with name.</span></span>
  
## <span data-ttu-id="2bd5d-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bd5d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="2bd5d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bd5d-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2bd5d-107">診断と stringification の目的で使用されるこの関数の名前。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-107">The name of this function that will be used for diagnostics and stringification purposes.</span></span>  
  
 `nativeFunction`  
 <span data-ttu-id="2bd5d-108">関数が呼び出されたときに呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-108">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="2bd5d-109">コールバックに戻される、ユーザーによって指定された状態。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-109">User provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="2bd5d-110">新しい関数オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-110">The new function object.</span></span>  
  
## <span data-ttu-id="2bd5d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bd5d-111">Return Value</span></span>  
  
## <span data-ttu-id="2bd5d-112">注釈</span><span class="sxs-lookup"><span data-stu-id="2bd5d-112">Remarks</span></span>  
 <span data-ttu-id="2bd5d-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="2bd5d-114">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2bd5d-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="2bd5d-115">要件</span><span class="sxs-lookup"><span data-stu-id="2bd5d-115">Requirements</span></span>  
 <span data-ttu-id="2bd5d-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2bd5d-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2bd5d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bd5d-117">See Also</span></span>  
 [<span data-ttu-id="2bd5d-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2bd5d-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)