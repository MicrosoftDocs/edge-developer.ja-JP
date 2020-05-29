---
description: オブジェクトのプロトタイプを返します。
title: JsGetPrototype 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 12708634fea9e8f9fd1205514845b1cb9760ee9e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569316"
---
# <span data-ttu-id="10a79-103">JsGetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="10a79-103">JsGetPrototype Function</span></span>
<span data-ttu-id="10a79-104">オブジェクトのプロトタイプを返します。</span><span class="sxs-lookup"><span data-stu-id="10a79-104">Returns the prototype of an object.</span></span>  
  
## <span data-ttu-id="10a79-105">構文</span><span class="sxs-lookup"><span data-stu-id="10a79-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPrototype(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *prototypeObject  
);  
```  
  
#### <span data-ttu-id="10a79-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10a79-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="10a79-107">プロトタイプを返す対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10a79-107">The object whose prototype is to be returned.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="10a79-108">オブジェクトのプロトタイプ。</span><span class="sxs-lookup"><span data-stu-id="10a79-108">The object's prototype.</span></span>  
  
## <span data-ttu-id="10a79-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="10a79-109">Return Value</span></span>  
 <span data-ttu-id="10a79-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="10a79-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="10a79-111">注釈</span><span class="sxs-lookup"><span data-stu-id="10a79-111">Remarks</span></span>  
 <span data-ttu-id="10a79-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="10a79-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="10a79-113">要件</span><span class="sxs-lookup"><span data-stu-id="10a79-113">Requirements</span></span>  
 <span data-ttu-id="10a79-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="10a79-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="10a79-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="10a79-115">See Also</span></span>  
 [<span data-ttu-id="10a79-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="10a79-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)