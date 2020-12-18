---
description: 現在のスクリプト コンテキスト内のグローバル オブジェクトを取得します。
title: JsGetGlobalObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetGlobalObject
helpviewer_keywords:
- JsGetGlobalObject function
ms.assetid: d3e91e64-1ca3-4d2b-aada-725ded0fd0b1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cda960710180c135b99abd359d0cc76776ff0225
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234770"
---
# <span data-ttu-id="3e995-103">JsGetGlobalObject 関数</span><span class="sxs-lookup"><span data-stu-id="3e995-103">JsGetGlobalObject Function</span></span>

<span data-ttu-id="3e995-104">現在のスクリプト コンテキスト内のグローバル オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e995-104">Gets the global object in the current script context.</span></span>  
  
## <span data-ttu-id="3e995-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e995-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetGlobalObject(  
   _Out_ JsValueRef *globalObject  
);  
```  
  
#### <span data-ttu-id="3e995-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e995-106">Parameters</span></span>  
 `globalObject`  
 <span data-ttu-id="3e995-107">グローバル オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3e995-107">The global object.</span></span>  
  
## <span data-ttu-id="3e995-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e995-108">Return Value</span></span>  
 <span data-ttu-id="3e995-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="3e995-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3e995-110">注釈</span><span class="sxs-lookup"><span data-stu-id="3e995-110">Remarks</span></span>  
 <span data-ttu-id="3e995-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="3e995-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3e995-112">要件</span><span class="sxs-lookup"><span data-stu-id="3e995-112">Requirements</span></span>  
 <span data-ttu-id="3e995-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3e995-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3e995-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e995-114">See Also</span></span>  
 [<span data-ttu-id="3e995-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="3e995-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
