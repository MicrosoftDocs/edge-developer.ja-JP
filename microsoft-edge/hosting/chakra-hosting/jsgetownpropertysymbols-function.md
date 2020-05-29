---
description: オブジェクトのすべての symbol プロパティの一覧を取得します。
title: JsGetOwnPropertySymbols 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 57c431e3-de0b-4ed0-b750-87a86448daff
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7a7f4e88986a45fbccfae0c53e92ff2e5313991
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570451"
---
# <span data-ttu-id="0675f-103">JsGetOwnPropertySymbols 関数</span><span class="sxs-lookup"><span data-stu-id="0675f-103">JsGetOwnPropertySymbols Function</span></span>
<span data-ttu-id="0675f-104">オブジェクトのすべての symbol プロパティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="0675f-104">Gets the list of all symbol properties on the object.</span></span>  
  
## <span data-ttu-id="0675f-105">構文</span><span class="sxs-lookup"><span data-stu-id="0675f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertySymbols(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertySymbols  
);  
```  
  
#### <span data-ttu-id="0675f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0675f-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0675f-107">プロパティシンボルの取得元のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0675f-107">The object from which to get the property symbols.</span></span>  
  
 `propertySymbols`  
 <span data-ttu-id="0675f-108">プロパティシンボルの配列。</span><span class="sxs-lookup"><span data-stu-id="0675f-108">An array of property symbols.</span></span>  
  
## <span data-ttu-id="0675f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0675f-109">Return Value</span></span>  
 <span data-ttu-id="0675f-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0675f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0675f-111">注釈</span><span class="sxs-lookup"><span data-stu-id="0675f-111">Remarks</span></span>  
 <span data-ttu-id="0675f-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0675f-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0675f-113">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0675f-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0675f-114">要件</span><span class="sxs-lookup"><span data-stu-id="0675f-114">Requirements</span></span>  
 <span data-ttu-id="0675f-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0675f-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0675f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0675f-116">See Also</span></span>  
 [<span data-ttu-id="0675f-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0675f-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)