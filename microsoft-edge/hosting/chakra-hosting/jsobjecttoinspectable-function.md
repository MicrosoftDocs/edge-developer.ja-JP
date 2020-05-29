---
description: JavaScript オブジェクトからポインターへのラップを解除 `IInspectable` します。
title: JsObjectToInspectable 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7127e1cf1372020e0df00b81ed172739379426f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570422"
---
# <span data-ttu-id="2b21c-103">JsObjectToInspectable 関数</span><span class="sxs-lookup"><span data-stu-id="2b21c-103">JsObjectToInspectable Function</span></span>
<span data-ttu-id="2b21c-104">JavaScript オブジェクトからポインターへのラップを解除 `IInspectable` します。</span><span class="sxs-lookup"><span data-stu-id="2b21c-104">Unwraps a JavaScript object to an `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="2b21c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2b21c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### <span data-ttu-id="2b21c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b21c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2b21c-107">プロジェクションの対象となる JavaScript 値 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="2b21c-107">A JavaScript value that should be projected to `IInspectable`.</span></span>  
  
 `inspectable`  
 <span data-ttu-id="2b21c-108">`IInspectable`オブジェクトの値。</span><span class="sxs-lookup"><span data-stu-id="2b21c-108">An `IInspectable` value of the object.</span></span>  
  
## <span data-ttu-id="2b21c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2b21c-109">Return Value</span></span>  
 <span data-ttu-id="2b21c-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="2b21c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2b21c-111">注釈</span><span class="sxs-lookup"><span data-stu-id="2b21c-111">Remarks</span></span>  
 <span data-ttu-id="2b21c-112">ホストは、COM スレッドルールの強制を行います。</span><span class="sxs-lookup"><span data-stu-id="2b21c-112">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="2b21c-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b21c-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="2b21c-114">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2b21c-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="2b21c-115">要件</span><span class="sxs-lookup"><span data-stu-id="2b21c-115">Requirements</span></span>  
 <span data-ttu-id="2b21c-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2b21c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2b21c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b21c-117">See Also</span></span>  
 [<span data-ttu-id="2b21c-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2b21c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)