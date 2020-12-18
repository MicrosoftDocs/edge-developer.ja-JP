---
description: オブジェクトを拡張不可にする。
title: JsPreventExtension 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsPreventExtension
helpviewer_keywords:
- JsPreventExtension function
ms.assetid: 8da07e20-d076-4ae4-9fb0-3f3c141518c2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1904756a932bd581e05ec474004af7107da3f64b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234856"
---
# <span data-ttu-id="cd156-103">JsPreventExtension 関数</span><span class="sxs-lookup"><span data-stu-id="cd156-103">JsPreventExtension Function</span></span>

<span data-ttu-id="cd156-104">オブジェクトを拡張不可にする。</span><span class="sxs-lookup"><span data-stu-id="cd156-104">Makes an object non-extensible.</span></span>  
  
## <span data-ttu-id="cd156-105">構文</span><span class="sxs-lookup"><span data-stu-id="cd156-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPreventExtension(  
   _In_ JsValueRef object  
);  
```  
  
#### <span data-ttu-id="cd156-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd156-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="cd156-107">拡張不可にするオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd156-107">The object to make non-extensible.</span></span>  
  
## <span data-ttu-id="cd156-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="cd156-108">Return Value</span></span>  
 <span data-ttu-id="cd156-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="cd156-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="cd156-110">注釈</span><span class="sxs-lookup"><span data-stu-id="cd156-110">Remarks</span></span>  
 <span data-ttu-id="cd156-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd156-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="cd156-112">要件</span><span class="sxs-lookup"><span data-stu-id="cd156-112">Requirements</span></span>  
 <span data-ttu-id="cd156-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="cd156-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cd156-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd156-114">See Also</span></span>  
 [<span data-ttu-id="cd156-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="cd156-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
