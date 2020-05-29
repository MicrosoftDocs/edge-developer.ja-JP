---
description: オブジェクトのガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。
title: JsSetObjectBeforeCollectCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 77a59c6ace96809c0b232c96aa9639555e7badcd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570373"
---
# <span data-ttu-id="80962-103">JsSetObjectBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="80962-103">JsSetObjectBeforeCollectCallback Function</span></span>
<span data-ttu-id="80962-104">オブジェクトのガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="80962-104">Sets a callback function that is called by the runtime before garbage collection of an object.</span></span>  
  
## <span data-ttu-id="80962-105">構文</span><span class="sxs-lookup"><span data-stu-id="80962-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="80962-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80962-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="80962-107">コールバックを登録する対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80962-107">The object for which to register the callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="80962-108">コールバックに戻される、ユーザーが指定した状態。</span><span class="sxs-lookup"><span data-stu-id="80962-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `objectBeforeCollectCallback`  
 <span data-ttu-id="80962-109">設定されているコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="80962-109">The callback function being set.</span></span> <span data-ttu-id="80962-110">以前に登録されたコールバックをクリアするには null を使用します。</span><span class="sxs-lookup"><span data-stu-id="80962-110">Use null to clear previously registered callback.</span></span>  
  
## <span data-ttu-id="80962-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="80962-111">Return Value</span></span>  
 <span data-ttu-id="80962-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="80962-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="80962-113">注釈</span><span class="sxs-lookup"><span data-stu-id="80962-113">Remarks</span></span>  
 <span data-ttu-id="80962-114">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="80962-114">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="80962-115">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="80962-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="80962-116">要件</span><span class="sxs-lookup"><span data-stu-id="80962-116">Requirements</span></span>  
 <span data-ttu-id="80962-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="80962-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="80962-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="80962-118">See Also</span></span>  
 [<span data-ttu-id="80962-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="80962-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)