---
description: スレッドサービスのコールバック。
title: JsThreadServiceCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5eb9f2986c79db024f01f4d22050f79c9689400c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569269"
---
# <span data-ttu-id="9d8bc-103">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="9d8bc-103">JsThreadServiceCallback Typedef</span></span>
<span data-ttu-id="9d8bc-104">スレッドサービスのコールバック。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-104">A thread service callback.</span></span>  
  
## <span data-ttu-id="9d8bc-105">構文</span><span class="sxs-lookup"><span data-stu-id="9d8bc-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="9d8bc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d8bc-106">Parameters</span></span>  
 <span data-ttu-id="9d8bc-107">callback</span><span class="sxs-lookup"><span data-stu-id="9d8bc-107">callback</span></span>  
 <span data-ttu-id="9d8bc-108">バックグラウンド作業項目のコールバック。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-108">The callback for the background work item.</span></span>  
  
 <span data-ttu-id="9d8bc-109">"いいね" データ</span><span class="sxs-lookup"><span data-stu-id="9d8bc-109">callbackData</span></span>  
 <span data-ttu-id="9d8bc-110">コールバックに渡されるデータ引数。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-110">The data argument to be passed to the callback.</span></span>  
  
## <span data-ttu-id="9d8bc-111">注釈</span><span class="sxs-lookup"><span data-stu-id="9d8bc-111">Remarks</span></span>  
 <span data-ttu-id="9d8bc-112">ホストでは、JsCreateRuntime を呼び出すときにバックグラウンドスレッドサービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-112">The host can specify a background thread service when calling JsCreateRuntime.</span></span> <span data-ttu-id="9d8bc-113">指定すると、このコールバックを使用して、バックグラウンド作業項目がホストに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-113">If specified, then background work items will be passed to the host using this callback.</span></span> <span data-ttu-id="9d8bc-114">ホストは、バックグラウンド作業項目の実行を直ちに開始し、true を返すか false を返し、ランタイムがスレッド内の作業項目を処理することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9d8bc-114">The host is expected to either begin executing the background work item immediately and return true or return false and the runtime will handle the work item in-thread.</span></span>  
  
## <span data-ttu-id="9d8bc-115">要件</span><span class="sxs-lookup"><span data-stu-id="9d8bc-115">Requirements</span></span>  
 <span data-ttu-id="9d8bc-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="9d8bc-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9d8bc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d8bc-117">See Also</span></span>  
 [<span data-ttu-id="9d8bc-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9d8bc-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)