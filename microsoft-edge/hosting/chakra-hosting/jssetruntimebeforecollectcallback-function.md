---
description: 'ガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。 '
title: JsSetRuntimeBeforeCollectCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 31aefd28698c14a6fe17421a990a7c8b120876bf
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570276"
---
# <span data-ttu-id="721f5-103">JsSetRuntimeBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="721f5-103">JsSetRuntimeBeforeCollectCallback Function</span></span>
<span data-ttu-id="721f5-104">ガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="721f5-104">Sets a callback function that is called by the runtime before garbage collection.</span></span>  
  
## <span data-ttu-id="721f5-105">構文</span><span class="sxs-lookup"><span data-stu-id="721f5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="721f5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="721f5-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="721f5-107">割り当てのコールバックを登録するランタイム。</span><span class="sxs-lookup"><span data-stu-id="721f5-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="721f5-108">コールバックに戻される、ユーザーによって指定された状態。</span><span class="sxs-lookup"><span data-stu-id="721f5-108">User provided state that will be passed back to the callback.</span></span>  
  
 `beforeCollectCallback`  
 <span data-ttu-id="721f5-109">設定されているコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="721f5-109">The callback function being set.</span></span>  
  
## <span data-ttu-id="721f5-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="721f5-110">Return Value</span></span>  
 <span data-ttu-id="721f5-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="721f5-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="721f5-112">注釈</span><span class="sxs-lookup"><span data-stu-id="721f5-112">Remarks</span></span>  
 <span data-ttu-id="721f5-113">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="721f5-113">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="721f5-114">このコールバックは、ホストがガベージコレクションを準備するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="721f5-114">The callback can be used by hosts to prepare for garbage collection.</span></span> <span data-ttu-id="721f5-115">たとえば、Chakra オブジェクトの不要な参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="721f5-115">For example, by releasing unnecessary references on Chakra objects.</span></span>  
  
## <span data-ttu-id="721f5-116">要件</span><span class="sxs-lookup"><span data-stu-id="721f5-116">Requirements</span></span>  
 <span data-ttu-id="721f5-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="721f5-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="721f5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="721f5-118">See Also</span></span>  
 [<span data-ttu-id="721f5-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="721f5-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)