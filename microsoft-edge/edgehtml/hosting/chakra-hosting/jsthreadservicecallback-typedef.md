---
description: スレッド サービスコールバック。
title: JsThreadServiceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5f1fe416e158e9524bdd1caab847977a5dd21b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234680"
---
# <span data-ttu-id="f6d07-103">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="f6d07-103">JsThreadServiceCallback Typedef</span></span>

<span data-ttu-id="f6d07-104">スレッド サービスコールバック。</span><span class="sxs-lookup"><span data-stu-id="f6d07-104">A thread service callback.</span></span>  
  
## <span data-ttu-id="f6d07-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6d07-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="f6d07-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6d07-106">Parameters</span></span>  
 <span data-ttu-id="f6d07-107">callback</span><span class="sxs-lookup"><span data-stu-id="f6d07-107">callback</span></span>  
 <span data-ttu-id="f6d07-108">バックグラウンド作業項目のコールバック。</span><span class="sxs-lookup"><span data-stu-id="f6d07-108">The callback for the background work item.</span></span>  
  
 <span data-ttu-id="f6d07-109">callbackData</span><span class="sxs-lookup"><span data-stu-id="f6d07-109">callbackData</span></span>  
 <span data-ttu-id="f6d07-110">コールバックに渡されるデータ引数。</span><span class="sxs-lookup"><span data-stu-id="f6d07-110">The data argument to be passed to the callback.</span></span>  
  
## <span data-ttu-id="f6d07-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f6d07-111">Remarks</span></span>  
 <span data-ttu-id="f6d07-112">ホストは、JsCreateRuntime を呼び出す際にバックグラウンド スレッド サービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6d07-112">The host can specify a background thread service when calling JsCreateRuntime.</span></span> <span data-ttu-id="f6d07-113">指定した場合、バックグラウンド作業項目は、このコールバックを使用してホストに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f6d07-113">If specified, then background work items will be passed to the host using this callback.</span></span> <span data-ttu-id="f6d07-114">ホストは、バックグラウンド作業項目の実行を直ちに開始し、true を返す、または false を返す必要があります。ランタイムは作業項目をスレッド内で処理します。</span><span class="sxs-lookup"><span data-stu-id="f6d07-114">The host is expected to either begin executing the background work item immediately and return true or return false and the runtime will handle the work item in-thread.</span></span>  
  
## <span data-ttu-id="f6d07-115">要件</span><span class="sxs-lookup"><span data-stu-id="f6d07-115">Requirements</span></span>  
 <span data-ttu-id="f6d07-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f6d07-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f6d07-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6d07-117">See Also</span></span>  
 [<span data-ttu-id="f6d07-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f6d07-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
