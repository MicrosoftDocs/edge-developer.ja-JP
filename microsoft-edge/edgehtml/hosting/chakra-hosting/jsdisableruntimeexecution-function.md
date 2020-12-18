---
description: スクリプトの実行を中断し、実行時に実行中のスクリプトを終了します。
title: JsDisableRuntimeExecution 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a08e6a7f89c724f8cf1a73afd97d2cb23c0334e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234729"
---
# <span data-ttu-id="1f265-103">JsDisableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="1f265-103">JsDisableRuntimeExecution Function</span></span>

<span data-ttu-id="1f265-104">スクリプトの実行を中断し、実行時に実行中のスクリプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="1f265-104">Suspends script execution and terminates any running scripts in a runtime.</span></span>  
  
## <span data-ttu-id="1f265-105">構文</span><span class="sxs-lookup"><span data-stu-id="1f265-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="1f265-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f265-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="1f265-107">中断するランタイム。</span><span class="sxs-lookup"><span data-stu-id="1f265-107">The runtime to be suspended.</span></span>  
  
## <span data-ttu-id="1f265-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f265-108">Return Value</span></span>  
 <span data-ttu-id="1f265-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1f265-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1f265-110">注釈</span><span class="sxs-lookup"><span data-stu-id="1f265-110">Remarks</span></span>  
 <span data-ttu-id="1f265-111">中断されたランタイムの呼び出しは、呼び出 `JsEnableRuntimeExecution` されるまで失敗します。</span><span class="sxs-lookup"><span data-stu-id="1f265-111">Calls to a suspended runtime will fail until `JsEnableRuntimeExecution` is called.</span></span>  
  
 <span data-ttu-id="1f265-112">ランタイムがアクティブなスレッドでこの API を呼び出す必要はない。</span><span class="sxs-lookup"><span data-stu-id="1f265-112">This API does not have to be called on the thread the runtime is active on.</span></span> <span data-ttu-id="1f265-113">ランタイムは中断状態に設定されますが、実行中のスクリプトはすぐには中断されない可能性があります。実行中のスクリプトは、できるだけ早くキャッチできない例外で終了されます。</span><span class="sxs-lookup"><span data-stu-id="1f265-113">Although the runtime will be set into a suspended state, an executing script may not be suspended immediately; a running script will be terminated with an uncatchable exception as soon as possible.</span></span>  
  
 <span data-ttu-id="1f265-114">既に中断されているランタイムでの実行の中断は、実行を中断しません。</span><span class="sxs-lookup"><span data-stu-id="1f265-114">Suspending execution in a runtime that is already suspended is a no-op.</span></span>  
  
## <span data-ttu-id="1f265-115">要件</span><span class="sxs-lookup"><span data-stu-id="1f265-115">Requirements</span></span>  
 <span data-ttu-id="1f265-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="1f265-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1f265-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f265-117">See Also</span></span>  
 [<span data-ttu-id="1f265-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="1f265-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
