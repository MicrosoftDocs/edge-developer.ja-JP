---
description: JsrtContext で設定されている内部データを取得します。
title: JsGetContextData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5d7e446-267a-4a80-a427-6e1b95a3391b
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bd85ccbc4008897643ec3840e8cdeca3611a50c8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569335"
---
# <span data-ttu-id="82925-103">JsGetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="82925-103">JsGetContextData Function</span></span>
<span data-ttu-id="82925-104">JsrtContext で設定されている内部データを取得します。</span><span class="sxs-lookup"><span data-stu-id="82925-104">Gets the internal data set on JsrtContext.</span></span>  
  
## <span data-ttu-id="82925-105">構文</span><span class="sxs-lookup"><span data-stu-id="82925-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextData(  
  _In_ JsContextRef context,  
  _Out_ void **data  
);  
```  
  
#### <span data-ttu-id="82925-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82925-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="82925-107">データを取得するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="82925-107">The context to get the data from.</span></span>  
  
 `data`  
 <span data-ttu-id="82925-108">データが返されるデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="82925-108">The pointer to the data where data will be returned.</span></span>  
  
## <span data-ttu-id="82925-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="82925-109">Return Value</span></span>  
 <span data-ttu-id="82925-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="82925-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="82925-111">注釈</span><span class="sxs-lookup"><span data-stu-id="82925-111">Remarks</span></span>  
 <span data-ttu-id="82925-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="82925-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="82925-113">要件</span><span class="sxs-lookup"><span data-stu-id="82925-113">Requirements</span></span>  
 <span data-ttu-id="82925-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="82925-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="82925-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="82925-115">See Also</span></span>  
 [<span data-ttu-id="82925-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="82925-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)