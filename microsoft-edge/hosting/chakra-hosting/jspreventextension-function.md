---
description: オブジェクトを非拡張可能にします。
title: JsPreventExtension 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsPreventExtension
helpviewer_keywords:
- JsPreventExtension function
ms.assetid: 8da07e20-d076-4ae4-9fb0-3f3c141518c2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: baa001b2fd26133ef3a20c88213ac6aaf34a2e0d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570409"
---
# <span data-ttu-id="da500-103">JsPreventExtension 関数</span><span class="sxs-lookup"><span data-stu-id="da500-103">JsPreventExtension Function</span></span>
<span data-ttu-id="da500-104">オブジェクトを非拡張可能にします。</span><span class="sxs-lookup"><span data-stu-id="da500-104">Makes an object non-extensible.</span></span>  
  
## <span data-ttu-id="da500-105">構文</span><span class="sxs-lookup"><span data-stu-id="da500-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPreventExtension(  
   _In_ JsValueRef object  
);  
```  
  
#### <span data-ttu-id="da500-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da500-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="da500-107">非拡張できるようにするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="da500-107">The object to make non-extensible.</span></span>  
  
## <span data-ttu-id="da500-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="da500-108">Return Value</span></span>  
 <span data-ttu-id="da500-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="da500-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="da500-110">注釈</span><span class="sxs-lookup"><span data-stu-id="da500-110">Remarks</span></span>  
 <span data-ttu-id="da500-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="da500-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="da500-112">要件</span><span class="sxs-lookup"><span data-stu-id="da500-112">Requirements</span></span>  
 <span data-ttu-id="da500-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="da500-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="da500-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="da500-114">See Also</span></span>  
 [<span data-ttu-id="da500-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="da500-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)