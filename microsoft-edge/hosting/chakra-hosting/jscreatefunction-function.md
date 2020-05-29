---
description: 新しい JavaScript 関数を作成します。
title: JsCreateFunction 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 22585afcb379c281eda621c3b233ccf4bc278ad1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569365"
---
# <span data-ttu-id="dd3f0-103">JsCreateFunction 関数</span><span class="sxs-lookup"><span data-stu-id="dd3f0-103">JsCreateFunction Function</span></span>
<span data-ttu-id="dd3f0-104">新しい JavaScript 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-104">Creates a new JavaScript function.</span></span>
  
## <span data-ttu-id="dd3f0-105">構文</span><span class="sxs-lookup"><span data-stu-id="dd3f0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="dd3f0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd3f0-106">Parameters</span></span>  
 `nativeFunction`  
 <span data-ttu-id="dd3f0-107">関数が呼び出されたときに呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-107">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="dd3f0-108">コールバックに戻される、ユーザーが指定した状態。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="dd3f0-109">新しい関数オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-109">The new function object.</span></span>  
  
## <span data-ttu-id="dd3f0-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="dd3f0-110">Return Value</span></span>  
 <span data-ttu-id="dd3f0-111">通話の結果 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-111">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="dd3f0-112">注釈</span><span class="sxs-lookup"><span data-stu-id="dd3f0-112">Remarks</span></span>  
 <span data-ttu-id="dd3f0-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd3f0-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="dd3f0-114">要件</span><span class="sxs-lookup"><span data-stu-id="dd3f0-114">Requirements</span></span>  
 <span data-ttu-id="dd3f0-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="dd3f0-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dd3f0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd3f0-116">See Also</span></span>  
 [<span data-ttu-id="dd3f0-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="dd3f0-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)