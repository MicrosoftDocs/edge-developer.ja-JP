---
description: JsrtContext の内部データを設定します。
title: JsSetContextData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: be90aa6a-b001-4a6f-90c5-c2135e913be0
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cac404b9e79bafb5a8eafb47e893dbdf38a02405
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234847"
---
# <span data-ttu-id="4b564-103">JsSetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="4b564-103">JsSetContextData Function</span></span>

<span data-ttu-id="4b564-104">JsrtContext の内部データを設定します。</span><span class="sxs-lookup"><span data-stu-id="4b564-104">Sets the internal data of JsrtContext.</span></span>  
  
## <span data-ttu-id="4b564-105">構文</span><span class="sxs-lookup"><span data-stu-id="4b564-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetContextData(  
  _In_ JsContextRef context,  
  _In_ void *data  
);  
  
```  
  
#### <span data-ttu-id="4b564-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b564-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="4b564-107">データを設定するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="4b564-107">The context to set the data to.</span></span>  
  
 `data`  
 <span data-ttu-id="4b564-108">設定するデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4b564-108">The pointer to the data to be set.</span></span>  
  
## <span data-ttu-id="4b564-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4b564-109">Return Value</span></span>  
 <span data-ttu-id="4b564-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4b564-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4b564-111">注釈</span><span class="sxs-lookup"><span data-stu-id="4b564-111">Remarks</span></span>  
 <span data-ttu-id="4b564-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4b564-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4b564-113">要件</span><span class="sxs-lookup"><span data-stu-id="4b564-113">Requirements</span></span>  
 <span data-ttu-id="4b564-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4b564-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4b564-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b564-115">See Also</span></span>  
 [<span data-ttu-id="4b564-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="4b564-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
