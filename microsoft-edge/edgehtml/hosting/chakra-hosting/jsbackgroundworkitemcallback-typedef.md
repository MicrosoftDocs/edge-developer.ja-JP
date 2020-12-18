---
description: バックグラウンド作業項目のコールバック。
title: JsBackgroundWorkItemCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d69306b334c2e0c9b27b96a5a417739ffdcd7dd7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234558"
---
# <span data-ttu-id="12a53-103">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="12a53-103">JsBackgroundWorkItemCallback Typedef</span></span>

<span data-ttu-id="12a53-104">バックグラウンド作業項目のコールバック。</span><span class="sxs-lookup"><span data-stu-id="12a53-104">A background work item callback.</span></span>  
  
## <span data-ttu-id="12a53-105">構文</span><span class="sxs-lookup"><span data-stu-id="12a53-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="12a53-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12a53-106">Parameters</span></span>  
 <span data-ttu-id="12a53-107">callbackData</span><span class="sxs-lookup"><span data-stu-id="12a53-107">callbackData</span></span>  
 <span data-ttu-id="12a53-108">スレッド サービスに渡されるデータ引数。</span><span class="sxs-lookup"><span data-stu-id="12a53-108">Data argument passed to the thread service.</span></span>  
  
## <span data-ttu-id="12a53-109">注釈</span><span class="sxs-lookup"><span data-stu-id="12a53-109">Remarks</span></span>  
 <span data-ttu-id="12a53-110">これは、ホストのスレッド サービス (指定されている場合) に渡されます。これにより、ホストは選択したバックグラウンド スレッドで作業項目のコールバックを呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12a53-110">This is passed to the host's thread service (if provided) to allow the host to invoke the work item callback on the background thread of its choice.</span></span>  
  
## <span data-ttu-id="12a53-111">要件</span><span class="sxs-lookup"><span data-stu-id="12a53-111">Requirements</span></span>  
 <span data-ttu-id="12a53-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="12a53-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="12a53-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="12a53-113">See Also</span></span>  
 [<span data-ttu-id="12a53-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="12a53-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
