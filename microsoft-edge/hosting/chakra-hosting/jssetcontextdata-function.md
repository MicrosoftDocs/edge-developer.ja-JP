---
description: JsrtContext の内部データを設定します。
title: JsSetContextData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be90aa6a-b001-4a6f-90c5-c2135e913be0
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 00521bafdaf6125dd15746de8a1d403eaf03b4a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570385"
---
# <span data-ttu-id="7868f-103">JsSetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="7868f-103">JsSetContextData Function</span></span>
<span data-ttu-id="7868f-104">JsrtContext の内部データを設定します。</span><span class="sxs-lookup"><span data-stu-id="7868f-104">Sets the internal data of JsrtContext.</span></span>  
  
## <span data-ttu-id="7868f-105">構文</span><span class="sxs-lookup"><span data-stu-id="7868f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetContextData(  
  _In_ JsContextRef context,  
  _In_ void *data  
);  
  
```  
  
#### <span data-ttu-id="7868f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7868f-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="7868f-107">データを設定するためのコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="7868f-107">The context to set the data to.</span></span>  
  
 `data`  
 <span data-ttu-id="7868f-108">設定するデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7868f-108">The pointer to the data to be set.</span></span>  
  
## <span data-ttu-id="7868f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7868f-109">Return Value</span></span>  
 <span data-ttu-id="7868f-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="7868f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7868f-111">注釈</span><span class="sxs-lookup"><span data-stu-id="7868f-111">Remarks</span></span>  
 <span data-ttu-id="7868f-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7868f-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7868f-113">要件</span><span class="sxs-lookup"><span data-stu-id="7868f-113">Requirements</span></span>  
 <span data-ttu-id="7868f-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="7868f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7868f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7868f-115">See Also</span></span>  
 [<span data-ttu-id="7868f-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7868f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)