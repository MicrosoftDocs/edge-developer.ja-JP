---
description: プロパティ ID に関連付けられているシンボルを取得します。
title: JsGetSymbolFromPropertyId 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0e822cb4-ba9e-44df-bf3a-fae97c354daa
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6902384772f29f80751660ce2d4a295d2ea620ab
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569305"
---
# <span data-ttu-id="8849b-103">JsGetSymbolFromPropertyId 関数</span><span class="sxs-lookup"><span data-stu-id="8849b-103">JsGetSymbolFromPropertyId Function</span></span>
<span data-ttu-id="8849b-104">プロパティ ID に関連付けられているシンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8849b-104">Gets the symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="8849b-105">構文</span><span class="sxs-lookup"><span data-stu-id="8849b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetSymbolFromPropertyId(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *symbol  
);  
```  
  
#### <span data-ttu-id="8849b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8849b-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="8849b-107">記号を取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="8849b-107">The property ID to get the symbol of.</span></span>  
  
 `symbol`  
 <span data-ttu-id="8849b-108">プロパティ ID に関連付けられているシンボル。</span><span class="sxs-lookup"><span data-stu-id="8849b-108">The symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="8849b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8849b-109">Return Value</span></span>  
 <span data-ttu-id="8849b-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="8849b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8849b-111">注釈</span><span class="sxs-lookup"><span data-stu-id="8849b-111">Remarks</span></span>  
 <span data-ttu-id="8849b-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8849b-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="8849b-113">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8849b-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="8849b-114">要件</span><span class="sxs-lookup"><span data-stu-id="8849b-114">Requirements</span></span>  
 <span data-ttu-id="8849b-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="8849b-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8849b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8849b-116">See Also</span></span>  
 [<span data-ttu-id="8849b-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="8849b-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)