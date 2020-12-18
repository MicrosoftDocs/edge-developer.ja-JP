---
description: 渡されるプロジェクションである JavaScript 値を作成します `VARIANT` 。
title: JsVariantToValue 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 58c928b519b5a9a678b6cd6ad367e1db2332f021
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234675"
---
# <span data-ttu-id="a4a62-103">JsVariantToValue 関数</span><span class="sxs-lookup"><span data-stu-id="a4a62-103">JsVariantToValue Function</span></span>

<span data-ttu-id="a4a62-104">渡されるプロジェクションである JavaScript 値を作成します `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="a4a62-104">Creates a JavaScript value that is a projection of the passed in `VARIANT`.</span></span>  
  
## <span data-ttu-id="a4a62-105">構文</span><span class="sxs-lookup"><span data-stu-id="a4a62-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="a4a62-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4a62-106">Parameters</span></span>  
 `variant`  
 <span data-ttu-id="a4a62-107">投影 `VARIANT` される A。</span><span class="sxs-lookup"><span data-stu-id="a4a62-107">A `VARIANT` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="a4a62-108">のプロジェクションである JavaScript 値 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="a4a62-108">A JavaScript value that is a projection of the `VARIANT`.</span></span>  
  
## <span data-ttu-id="a4a62-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a4a62-109">Return Value</span></span>  
 <span data-ttu-id="a4a62-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a4a62-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a4a62-111">注釈</span><span class="sxs-lookup"><span data-stu-id="a4a62-111">Remarks</span></span>  
 <span data-ttu-id="a4a62-112">投影された値は、スクリプトから COM オートメーション オブジェクトを呼び出すスクリプトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4a62-112">The projected value can be used by script to call a COM automation object from script.</span></span> <span data-ttu-id="a4a62-113">ホストは COM スレッド ルールを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a62-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="a4a62-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4a62-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a4a62-115">要件</span><span class="sxs-lookup"><span data-stu-id="a4a62-115">Requirements</span></span>  
 <span data-ttu-id="a4a62-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a4a62-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a4a62-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4a62-117">See Also</span></span>  
 [<span data-ttu-id="a4a62-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="a4a62-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
