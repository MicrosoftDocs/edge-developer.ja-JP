---
description: 渡された値のプロジェクションである JavaScript 値を作成し `VARIANT` ます。
title: JsVariantToValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 01796bc38548cf56b500731d899541ef214ec4e3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569258"
---
# <span data-ttu-id="480b6-103">JsVariantToValue 関数</span><span class="sxs-lookup"><span data-stu-id="480b6-103">JsVariantToValue Function</span></span>
<span data-ttu-id="480b6-104">渡された値のプロジェクションである JavaScript 値を作成し `VARIANT` ます。</span><span class="sxs-lookup"><span data-stu-id="480b6-104">Creates a JavaScript value that is a projection of the passed in `VARIANT`.</span></span>  
  
## <span data-ttu-id="480b6-105">構文</span><span class="sxs-lookup"><span data-stu-id="480b6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="480b6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="480b6-106">Parameters</span></span>  
 `variant`  
 <span data-ttu-id="480b6-107">`VARIANT`を投影します。</span><span class="sxs-lookup"><span data-stu-id="480b6-107">A `VARIANT` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="480b6-108">のプロジェクションである JavaScript 値 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="480b6-108">A JavaScript value that is a projection of the `VARIANT`.</span></span>  
  
## <span data-ttu-id="480b6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="480b6-109">Return Value</span></span>  
 <span data-ttu-id="480b6-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="480b6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="480b6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="480b6-111">Remarks</span></span>  
 <span data-ttu-id="480b6-112">射影された値をスクリプトで使って、スクリプトから COM オートメーションオブジェクトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="480b6-112">The projected value can be used by script to call a COM automation object from script.</span></span> <span data-ttu-id="480b6-113">ホストは、COM スレッドルールの強制を行います。</span><span class="sxs-lookup"><span data-stu-id="480b6-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="480b6-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="480b6-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="480b6-115">要件</span><span class="sxs-lookup"><span data-stu-id="480b6-115">Requirements</span></span>  
 <span data-ttu-id="480b6-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="480b6-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="480b6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="480b6-117">See Also</span></span>  
 [<span data-ttu-id="480b6-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="480b6-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)