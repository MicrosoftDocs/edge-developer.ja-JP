---
description: 外部オブジェクトからデータを取得します。
title: JsGetExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetExternalData
helpviewer_keywords:
- JsGetExternalData function
ms.assetid: 1919e1da-3ea7-4269-a5fb-a3be06bd029b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 469d28d47f89b06897e4b72d081baad34eb92a6c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569326"
---
# <span data-ttu-id="b92b8-103">JsGetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="b92b8-103">JsGetExternalData Function</span></span>
<span data-ttu-id="b92b8-104">外部オブジェクトからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="b92b8-104">Retrieves the data from an external object.</span></span>  
  
## <span data-ttu-id="b92b8-105">構文</span><span class="sxs-lookup"><span data-stu-id="b92b8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExternalData(  
   _In_ JsValueRef object,  
   _Out_ void **externalData  
);  
```  
  
#### <span data-ttu-id="b92b8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b92b8-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="b92b8-107">外部オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b92b8-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="b92b8-108">オブジェクトに格納されている外部データ。</span><span class="sxs-lookup"><span data-stu-id="b92b8-108">The external data stored in the object.</span></span> <span data-ttu-id="b92b8-109">オブジェクトに外部データが保存されていない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b92b8-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="b92b8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b92b8-110">Return Value</span></span>  
 <span data-ttu-id="b92b8-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="b92b8-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b92b8-112">注釈</span><span class="sxs-lookup"><span data-stu-id="b92b8-112">Remarks</span></span>  
 <span data-ttu-id="b92b8-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b92b8-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b92b8-114">要件</span><span class="sxs-lookup"><span data-stu-id="b92b8-114">Requirements</span></span>  
 <span data-ttu-id="b92b8-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="b92b8-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b92b8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b92b8-116">See Also</span></span>  
 [<span data-ttu-id="b92b8-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b92b8-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)