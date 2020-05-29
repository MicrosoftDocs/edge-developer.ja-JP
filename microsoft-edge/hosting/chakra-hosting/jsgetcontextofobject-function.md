---
description: オブジェクトが属しているスクリプトコンテキストを取得します。
title: JsGetContextOfObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4f1b996954e877d9c98ac0caf06f255af629a386
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569333"
---
# <span data-ttu-id="c815d-103">JsGetContextOfObject 関数</span><span class="sxs-lookup"><span data-stu-id="c815d-103">JsGetContextOfObject Function</span></span>
<span data-ttu-id="c815d-104">オブジェクトが属しているスクリプトコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="c815d-104">Gets the script context that the object belongs to.</span></span>  
  
## <span data-ttu-id="c815d-105">構文</span><span class="sxs-lookup"><span data-stu-id="c815d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### <span data-ttu-id="c815d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c815d-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="c815d-107">コンテキストの取得元のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c815d-107">The object to get the context from.</span></span>  
  
 `context`  
 <span data-ttu-id="c815d-108">オブジェクトが属しているコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="c815d-108">The context the object belongs to.</span></span>  
  
## <span data-ttu-id="c815d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c815d-109">Return Value</span></span>  
 <span data-ttu-id="c815d-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="c815d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c815d-111">注釈</span><span class="sxs-lookup"><span data-stu-id="c815d-111">Remarks</span></span>  
 <span data-ttu-id="c815d-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c815d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c815d-113">要件</span><span class="sxs-lookup"><span data-stu-id="c815d-113">Requirements</span></span>  
 <span data-ttu-id="c815d-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="c815d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c815d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c815d-115">See Also</span></span>  
 [<span data-ttu-id="c815d-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c815d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)