---
description: JsValueRef の JavaScript の型を取得します。
title: JsGetValueType 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetValueType
helpviewer_keywords:
- JsGetValueType function
ms.assetid: f403cf7c-c8c0-4a17-bfa9-0302d00e760e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 85dc6644e26017c6085ab64d914a86196cca8080
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570432"
---
# <span data-ttu-id="250be-103">JsGetValueType 関数</span><span class="sxs-lookup"><span data-stu-id="250be-103">JsGetValueType Function</span></span>
<span data-ttu-id="250be-104">JsValueRef の JavaScript の型を取得します。</span><span class="sxs-lookup"><span data-stu-id="250be-104">Gets the JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="250be-105">構文</span><span class="sxs-lookup"><span data-stu-id="250be-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetValueType(  
   _In_ JsValueRef value,  
   _Out_ JsValueType *type  
);  
```  
  
#### <span data-ttu-id="250be-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="250be-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="250be-107">返される型の値。</span><span class="sxs-lookup"><span data-stu-id="250be-107">The value whose type is to be returned.</span></span>  
  
 `type`  
 <span data-ttu-id="250be-108">値の型。</span><span class="sxs-lookup"><span data-stu-id="250be-108">The type of the value.</span></span>  
  
## <span data-ttu-id="250be-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="250be-109">Return Value</span></span>  
 <span data-ttu-id="250be-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="250be-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="250be-111">注釈</span><span class="sxs-lookup"><span data-stu-id="250be-111">Remarks</span></span>  
 <span data-ttu-id="250be-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="250be-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="250be-113">要件</span><span class="sxs-lookup"><span data-stu-id="250be-113">Requirements</span></span>  
 <span data-ttu-id="250be-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="250be-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="250be-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="250be-115">See Also</span></span>  
 [<span data-ttu-id="250be-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="250be-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)