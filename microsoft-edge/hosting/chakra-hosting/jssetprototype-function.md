---
description: オブジェクトのプロトタイプを設定します。
title: JsSetPrototype 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88e1e421-4ae5-4e3b-b377-19256cc80e9f
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 625269c5f9f459a5c7eecb6cfc31cb85fc24214b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570288"
---
# <span data-ttu-id="10ef5-103">JsSetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="10ef5-103">JsSetPrototype Function</span></span>
<span data-ttu-id="10ef5-104">オブジェクトのプロトタイプを設定します。</span><span class="sxs-lookup"><span data-stu-id="10ef5-104">Sets the prototype of an object.</span></span>  
  
## <span data-ttu-id="10ef5-105">構文</span><span class="sxs-lookup"><span data-stu-id="10ef5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPrototype(  
   _In_ JsValueRef object,  
   _In_ JsValueRef prototypeObject  
);  
```  
  
#### <span data-ttu-id="10ef5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10ef5-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="10ef5-107">プロトタイプを変更するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10ef5-107">The object whose prototype is to be changed.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="10ef5-108">オブジェクトの新しいプロトタイプ。</span><span class="sxs-lookup"><span data-stu-id="10ef5-108">The object's new prototype.</span></span>  
  
## <span data-ttu-id="10ef5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="10ef5-109">Return Value</span></span>  
 <span data-ttu-id="10ef5-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="10ef5-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="10ef5-111">注釈</span><span class="sxs-lookup"><span data-stu-id="10ef5-111">Remarks</span></span>  
 <span data-ttu-id="10ef5-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="10ef5-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="10ef5-113">要件</span><span class="sxs-lookup"><span data-stu-id="10ef5-113">Requirements</span></span>  
 <span data-ttu-id="10ef5-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="10ef5-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="10ef5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="10ef5-115">See Also</span></span>  
 [<span data-ttu-id="10ef5-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="10ef5-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)