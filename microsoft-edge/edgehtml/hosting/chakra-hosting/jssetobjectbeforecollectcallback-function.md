---
description: オブジェクトのガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。
title: JsSetObjectBeforeCollectCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4689184dccaf6bc9f98eeacda5f5a4b91a927d40
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234513"
---
# <span data-ttu-id="3af00-103">JsSetObjectBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="3af00-103">JsSetObjectBeforeCollectCallback Function</span></span>

<span data-ttu-id="3af00-104">オブジェクトのガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3af00-104">Sets a callback function that is called by the runtime before garbage collection of an object.</span></span>  
  
## <span data-ttu-id="3af00-105">構文</span><span class="sxs-lookup"><span data-stu-id="3af00-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="3af00-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3af00-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="3af00-107">コールバックを登録するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3af00-107">The object for which to register the callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="3af00-108">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="3af00-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `objectBeforeCollectCallback`  
 <span data-ttu-id="3af00-109">設定するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="3af00-109">The callback function being set.</span></span> <span data-ttu-id="3af00-110">以前に登録したコールバックをクリアするには、null を使用します。</span><span class="sxs-lookup"><span data-stu-id="3af00-110">Use null to clear previously registered callback.</span></span>  
  
## <span data-ttu-id="3af00-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3af00-111">Return Value</span></span>  
 <span data-ttu-id="3af00-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="3af00-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3af00-113">注釈</span><span class="sxs-lookup"><span data-stu-id="3af00-113">Remarks</span></span>  
 <span data-ttu-id="3af00-114">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3af00-114">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="3af00-115">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3af00-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="3af00-116">要件</span><span class="sxs-lookup"><span data-stu-id="3af00-116">Requirements</span></span>  
 <span data-ttu-id="3af00-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3af00-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3af00-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3af00-118">See Also</span></span>  
 [<span data-ttu-id="3af00-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="3af00-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
