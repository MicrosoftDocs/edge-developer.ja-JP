---
description: 実行時にスクリプトの実行を中断し、実行中のスクリプトを終了します。
title: JsDisableRuntimeExecution 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 575947d3038eaa136e9d6ae62507501bc768eabe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569339"
---
# <span data-ttu-id="76745-103">JsDisableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="76745-103">JsDisableRuntimeExecution Function</span></span>
<span data-ttu-id="76745-104">実行時にスクリプトの実行を中断し、実行中のスクリプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="76745-104">Suspends script execution and terminates any running scripts in a runtime.</span></span>  
  
## <span data-ttu-id="76745-105">構文</span><span class="sxs-lookup"><span data-stu-id="76745-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="76745-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76745-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="76745-107">中断するランタイム。</span><span class="sxs-lookup"><span data-stu-id="76745-107">The runtime to be suspended.</span></span>  
  
## <span data-ttu-id="76745-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="76745-108">Return Value</span></span>  
 <span data-ttu-id="76745-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="76745-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="76745-110">注釈</span><span class="sxs-lookup"><span data-stu-id="76745-110">Remarks</span></span>  
 <span data-ttu-id="76745-111">中断されたランタイムへの呼び出しは、が呼び出されるまで失敗 `JsEnableRuntimeExecution` します。</span><span class="sxs-lookup"><span data-stu-id="76745-111">Calls to a suspended runtime will fail until `JsEnableRuntimeExecution` is called.</span></span>  
  
 <span data-ttu-id="76745-112">この API は、ランタイムがアクティブになっているスレッドで呼び出される必要はありません。</span><span class="sxs-lookup"><span data-stu-id="76745-112">This API does not have to be called on the thread the runtime is active on.</span></span> <span data-ttu-id="76745-113">ランタイムは中断状態に設定されますが、実行中のスクリプトはすぐに中断されない可能性があります。実行中のスクリプトは、できるだけ早く uncatchable 例外で終了します。</span><span class="sxs-lookup"><span data-stu-id="76745-113">Although the runtime will be set into a suspended state, an executing script may not be suspended immediately; a running script will be terminated with an uncatchable exception as soon as possible.</span></span>  
  
 <span data-ttu-id="76745-114">既に中断されているランタイムで実行を中断することは、何の操作でもありません。</span><span class="sxs-lookup"><span data-stu-id="76745-114">Suspending execution in a runtime that is already suspended is a no-op.</span></span>  
  
## <span data-ttu-id="76745-115">要件</span><span class="sxs-lookup"><span data-stu-id="76745-115">Requirements</span></span>  
 <span data-ttu-id="76745-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="76745-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="76745-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="76745-117">See Also</span></span>  
 [<span data-ttu-id="76745-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="76745-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)