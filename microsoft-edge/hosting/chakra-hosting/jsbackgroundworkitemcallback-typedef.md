---
description: バックグラウンド作業項目のコールバック。
title: JsBackgroundWorkItemCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9bc1e5687d92d7286e1e6d4387bd6b69d95ceb68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569403"
---
# <span data-ttu-id="3c46d-103">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="3c46d-103">JsBackgroundWorkItemCallback Typedef</span></span>
<span data-ttu-id="3c46d-104">バックグラウンド作業項目のコールバック。</span><span class="sxs-lookup"><span data-stu-id="3c46d-104">A background work item callback.</span></span>  
  
## <span data-ttu-id="3c46d-105">構文</span><span class="sxs-lookup"><span data-stu-id="3c46d-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="3c46d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c46d-106">Parameters</span></span>  
 <span data-ttu-id="3c46d-107">"いいね" データ</span><span class="sxs-lookup"><span data-stu-id="3c46d-107">callbackData</span></span>  
 <span data-ttu-id="3c46d-108">スレッドサービスに渡されるデータ引数。</span><span class="sxs-lookup"><span data-stu-id="3c46d-108">Data argument passed to the thread service.</span></span>  
  
## <span data-ttu-id="3c46d-109">注釈</span><span class="sxs-lookup"><span data-stu-id="3c46d-109">Remarks</span></span>  
 <span data-ttu-id="3c46d-110">これは、ホストのスレッドサービス (提供されている場合) に渡されます。これは、選択したバックグラウンドスレッドでホストが作業項目のコールバックを呼び出すことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="3c46d-110">This is passed to the host's thread service (if provided) to allow the host to invoke the work item callback on the background thread of its choice.</span></span>  
  
## <span data-ttu-id="3c46d-111">要件</span><span class="sxs-lookup"><span data-stu-id="3c46d-111">Requirements</span></span>  
 <span data-ttu-id="3c46d-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="3c46d-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3c46d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c46d-113">See Also</span></span>  
 [<span data-ttu-id="3c46d-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="3c46d-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)