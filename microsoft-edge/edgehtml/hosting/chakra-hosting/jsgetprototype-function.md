---
description: オブジェクトのプロトタイプを返します。
title: JsGetPrototype 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d64e8b090753e5d0627f0d40ee8745eeadd65227
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235025"
---
# <span data-ttu-id="98f5f-103">JsGetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="98f5f-103">JsGetPrototype Function</span></span>

<span data-ttu-id="98f5f-104">オブジェクトのプロトタイプを返します。</span><span class="sxs-lookup"><span data-stu-id="98f5f-104">Returns the prototype of an object.</span></span>  
  
## <span data-ttu-id="98f5f-105">構文</span><span class="sxs-lookup"><span data-stu-id="98f5f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPrototype(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *prototypeObject  
);  
```  
  
#### <span data-ttu-id="98f5f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98f5f-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="98f5f-107">プロトタイプを返すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98f5f-107">The object whose prototype is to be returned.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="98f5f-108">オブジェクトのプロトタイプ。</span><span class="sxs-lookup"><span data-stu-id="98f5f-108">The object's prototype.</span></span>  
  
## <span data-ttu-id="98f5f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="98f5f-109">Return Value</span></span>  
 <span data-ttu-id="98f5f-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="98f5f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="98f5f-111">注釈</span><span class="sxs-lookup"><span data-stu-id="98f5f-111">Remarks</span></span>  
 <span data-ttu-id="98f5f-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="98f5f-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="98f5f-113">要件</span><span class="sxs-lookup"><span data-stu-id="98f5f-113">Requirements</span></span>  
 <span data-ttu-id="98f5f-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="98f5f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="98f5f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="98f5f-115">See Also</span></span>  
 [<span data-ttu-id="98f5f-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="98f5f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
