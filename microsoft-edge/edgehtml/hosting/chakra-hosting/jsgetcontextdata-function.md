---
description: JsrtContext の内部データ セットを取得します。
title: JsGetContextData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: f5d7e446-267a-4a80-a427-6e1b95a3391b
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8f5f70a9c36fea355792050c1a2a810bca2d07b3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234651"
---
# <span data-ttu-id="5ceb2-103">JsGetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="5ceb2-103">JsGetContextData Function</span></span>

<span data-ttu-id="5ceb2-104">JsrtContext の内部データ セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ceb2-104">Gets the internal data set on JsrtContext.</span></span>  
  
## <span data-ttu-id="5ceb2-105">構文</span><span class="sxs-lookup"><span data-stu-id="5ceb2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextData(  
  _In_ JsContextRef context,  
  _Out_ void **data  
);  
```  
  
#### <span data-ttu-id="5ceb2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ceb2-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="5ceb2-107">データを取得するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="5ceb2-107">The context to get the data from.</span></span>  
  
 `data`  
 <span data-ttu-id="5ceb2-108">データが返されるデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5ceb2-108">The pointer to the data where data will be returned.</span></span>  
  
## <span data-ttu-id="5ceb2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5ceb2-109">Return Value</span></span>  
 <span data-ttu-id="5ceb2-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="5ceb2-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5ceb2-111">注釈</span><span class="sxs-lookup"><span data-stu-id="5ceb2-111">Remarks</span></span>  
 <span data-ttu-id="5ceb2-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5ceb2-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5ceb2-113">要件</span><span class="sxs-lookup"><span data-stu-id="5ceb2-113">Requirements</span></span>  
 <span data-ttu-id="5ceb2-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5ceb2-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5ceb2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ceb2-115">See Also</span></span>  
 [<span data-ttu-id="5ceb2-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="5ceb2-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
