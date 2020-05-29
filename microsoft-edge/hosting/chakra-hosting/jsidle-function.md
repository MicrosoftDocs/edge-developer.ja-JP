---
description: 実行する必要があるアイドル処理をランタイムに指示します。
title: JsIdle 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4da7148bf7daa3db983ab8f5bba622bfe0b19466
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570425"
---
# <span data-ttu-id="91d85-103">JsIdle 関数</span><span class="sxs-lookup"><span data-stu-id="91d85-103">JsIdle Function</span></span>
<span data-ttu-id="91d85-104">実行する必要があるアイドル処理をランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="91d85-104">Tells the runtime to do any idle processing it need to do.</span></span>  
  
## <span data-ttu-id="91d85-105">構文</span><span class="sxs-lookup"><span data-stu-id="91d85-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <span data-ttu-id="91d85-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91d85-106">Parameters</span></span>  
 `nextIdleTick`  
 <span data-ttu-id="91d85-107">次のシステムでは、アイドル作業がより多く発生する場合にオンになります。</span><span class="sxs-lookup"><span data-stu-id="91d85-107">The next system tick when there will be more idle work to do.</span></span> <span data-ttu-id="91d85-108">Null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="91d85-108">Can be null.</span></span> <span data-ttu-id="91d85-109">次のアイドル作業が存在しない場合は、タイマー刻みの最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="91d85-109">Returns the maximum number of ticks if there no upcoming idle work to do.</span></span>  
  
## <span data-ttu-id="91d85-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="91d85-110">Return Value</span></span>  
 <span data-ttu-id="91d85-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="91d85-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="91d85-112">注釈</span><span class="sxs-lookup"><span data-stu-id="91d85-112">Remarks</span></span>  
 <span data-ttu-id="91d85-113">現在のランタイムでアイドル処理が有効になっている場合、呼び出し `JsIdle` は、ホストがアイドル状態であり、ランタイムがメモリクリーンアップタスクを実行できることを現在のランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="91d85-113">If idle processing has been enabled for the current runtime, calling `JsIdle` will inform the current runtime that the host is idle and that the runtime can perform memory cleanup tasks.</span></span>  
  
 `JsIdle` <span data-ttu-id="91d85-114">また、ランタイムが実行できるアイドル作業が増加するまで、システムのタイマー刻みの数を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="91d85-114">can also return the number of system ticks until there will be more idle work for the runtime to do.</span></span> <span data-ttu-id="91d85-115">`JsIdle`この数のタイマー刻みより前に通話を発信しても、動作はありません。</span><span class="sxs-lookup"><span data-stu-id="91d85-115">Calling `JsIdle` before this number of ticks has passed will do no work.</span></span>  
  
 <span data-ttu-id="91d85-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="91d85-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="91d85-117">要件</span><span class="sxs-lookup"><span data-stu-id="91d85-117">Requirements</span></span>  
 <span data-ttu-id="91d85-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="91d85-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="91d85-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="91d85-119">See Also</span></span>  
 [<span data-ttu-id="91d85-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="91d85-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)