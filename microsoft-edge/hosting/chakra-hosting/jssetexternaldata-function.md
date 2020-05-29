---
description: 外部オブジェクトの外部データを設定します。
title: JsSetExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetExternalData
helpviewer_keywords:
- JsSetExternalData function
ms.assetid: 94e0ad34-67d7-4f7f-88a3-3b057ef5e4b9
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cc638905786a1baa0a3d5f79bfa3792a764f358f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570379"
---
# <span data-ttu-id="ef548-103">JsSetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ef548-103">JsSetExternalData Function</span></span>
<span data-ttu-id="ef548-104">外部オブジェクトの外部データを設定します。</span><span class="sxs-lookup"><span data-stu-id="ef548-104">Sets the external data on an external object.</span></span>  
  
## <span data-ttu-id="ef548-105">構文</span><span class="sxs-lookup"><span data-stu-id="ef548-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetExternalData(  
   _In_ JsValueRef object,  
   _In_opt_ void *externalData  
);  
```  
  
#### <span data-ttu-id="ef548-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef548-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ef548-107">外部オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ef548-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="ef548-108">オブジェクトに格納されている外部データ。</span><span class="sxs-lookup"><span data-stu-id="ef548-108">The external data stored in the object.</span></span> <span data-ttu-id="ef548-109">オブジェクトに外部データが保存されていない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ef548-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="ef548-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ef548-110">Return Value</span></span>  
 <span data-ttu-id="ef548-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="ef548-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ef548-112">注釈</span><span class="sxs-lookup"><span data-stu-id="ef548-112">Remarks</span></span>  
 <span data-ttu-id="ef548-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef548-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ef548-114">要件</span><span class="sxs-lookup"><span data-stu-id="ef548-114">Requirements</span></span>  
 <span data-ttu-id="ef548-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="ef548-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ef548-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef548-116">See Also</span></span>  
 [<span data-ttu-id="ef548-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ef548-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)