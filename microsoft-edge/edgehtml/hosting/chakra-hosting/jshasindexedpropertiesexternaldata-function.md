---
description: オブジェクトが外部データにインデックス付きプロパティを持つかどうかを指定します。
title: JsHasIndexedPropertiesExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c676db20-3ef1-4f84-8b26-3e06fe0ab2bf
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6395bacb15904bc3f2e74d22959844e8e0af373
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235026"
---
# <span data-ttu-id="e2561-103">JsHasIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="e2561-103">JsHasIndexedPropertiesExternalData Function</span></span>

<span data-ttu-id="e2561-104">オブジェクトが外部データにインデックス付きプロパティを持つかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2561-104">Determines whether an object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="e2561-105">構文</span><span class="sxs-lookup"><span data-stu-id="e2561-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool* value  
);  
```  
  
#### <span data-ttu-id="e2561-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2561-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="e2561-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e2561-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="e2561-108">オブジェクトが外部データにインデックス付きプロパティを持つかどうか。</span><span class="sxs-lookup"><span data-stu-id="e2561-108">Whether the object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="e2561-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e2561-109">Return Value</span></span>  
 <span data-ttu-id="e2561-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e2561-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e2561-111">注釈</span><span class="sxs-lookup"><span data-stu-id="e2561-111">Remarks</span></span>  
 <span data-ttu-id="e2561-112">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e2561-112">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="e2561-113">要件</span><span class="sxs-lookup"><span data-stu-id="e2561-113">Requirements</span></span>  
 <span data-ttu-id="e2561-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e2561-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e2561-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2561-115">See Also</span></span>  
 [<span data-ttu-id="e2561-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="e2561-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
