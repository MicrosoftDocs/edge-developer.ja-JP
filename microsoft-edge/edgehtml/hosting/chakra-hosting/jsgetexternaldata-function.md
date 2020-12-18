---
description: 外部オブジェクトからデータを取得します。
title: JsGetExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetExternalData
helpviewer_keywords:
- JsGetExternalData function
ms.assetid: 1919e1da-3ea7-4269-a5fb-a3be06bd029b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d046b5c515b1a688cd527fdc0eb9cd173eb47570
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234772"
---
# <span data-ttu-id="aa7d2-103">JsGetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="aa7d2-103">JsGetExternalData Function</span></span>

<span data-ttu-id="aa7d2-104">外部オブジェクトからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-104">Retrieves the data from an external object.</span></span>  
  
## <span data-ttu-id="aa7d2-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa7d2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExternalData(  
   _In_ JsValueRef object,  
   _Out_ void **externalData  
);  
```  
  
#### <span data-ttu-id="aa7d2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa7d2-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="aa7d2-107">外部オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="aa7d2-108">オブジェクトに格納されている外部データ。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-108">The external data stored in the object.</span></span> <span data-ttu-id="aa7d2-109">オブジェクトに外部データが格納されな場合は null になります。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="aa7d2-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa7d2-110">Return Value</span></span>  
 <span data-ttu-id="aa7d2-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="aa7d2-112">注釈</span><span class="sxs-lookup"><span data-stu-id="aa7d2-112">Remarks</span></span>  
 <span data-ttu-id="aa7d2-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa7d2-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="aa7d2-114">要件</span><span class="sxs-lookup"><span data-stu-id="aa7d2-114">Requirements</span></span>  
 <span data-ttu-id="aa7d2-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="aa7d2-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="aa7d2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa7d2-116">See Also</span></span>  
 [<span data-ttu-id="aa7d2-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="aa7d2-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
