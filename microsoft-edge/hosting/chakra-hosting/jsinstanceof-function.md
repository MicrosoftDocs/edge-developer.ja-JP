---
description: JavaScript `instanceof` 演算子のテストを実行します。
title: JsInstanceOf 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4d9bf2e4c3da9f83fdf7c0ef4e2c31df04670420
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751976"
---
# <span data-ttu-id="0d3e3-103">JsInstanceOf 関数</span><span class="sxs-lookup"><span data-stu-id="0d3e3-103">JsInstanceOf Function</span></span>
<span data-ttu-id="0d3e3-104">JavaScript `instanceof` 演算子のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-104">Performs JavaScript `instanceof` operator test.</span></span>  
  
## <span data-ttu-id="0d3e3-105">構文</span><span class="sxs-lookup"><span data-stu-id="0d3e3-105">Syntax</span></span>  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### <span data-ttu-id="0d3e3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d3e3-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0d3e3-107">テストするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-107">The object to test.</span></span>  
  
 `constructor`  
 <span data-ttu-id="0d3e3-108">テストするコンストラクター関数。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-108">The constructor function to test against.</span></span>  
  
 `result`  
 <span data-ttu-id="0d3e3-109">"Object でコンストラクター" が true であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-109">Whether the "object instanceof constructor" is true.</span></span>  
  
## <span data-ttu-id="0d3e3-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="0d3e3-110">Return Value</span></span>  
 <span data-ttu-id="0d3e3-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d3e3-112">注釈</span><span class="sxs-lookup"><span data-stu-id="0d3e3-112">Remarks</span></span>  
 <span data-ttu-id="0d3e3-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d3e3-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0d3e3-114">要件</span><span class="sxs-lookup"><span data-stu-id="0d3e3-114">Requirements</span></span>  
 <span data-ttu-id="0d3e3-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0d3e3-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d3e3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d3e3-116">See Also</span></span>  
 [<span data-ttu-id="0d3e3-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="0d3e3-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)