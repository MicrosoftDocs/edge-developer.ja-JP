---
description: 'ガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。 '
title: JsSetRuntimeBeforeCollectCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 94ad29fcfb778fc630d70664f917c6b5c2637dde
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234514"
---
# <span data-ttu-id="d0ab2-103">JsSetRuntimeBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="d0ab2-103">JsSetRuntimeBeforeCollectCallback Function</span></span>

<span data-ttu-id="d0ab2-104">ガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-104">Sets a callback function that is called by the runtime before garbage collection.</span></span>  
  
## <span data-ttu-id="d0ab2-105">構文</span><span class="sxs-lookup"><span data-stu-id="d0ab2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="d0ab2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0ab2-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="d0ab2-107">割り当てコールバックを登録するランタイム。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="d0ab2-108">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-108">User provided state that will be passed back to the callback.</span></span>  
  
 `beforeCollectCallback`  
 <span data-ttu-id="d0ab2-109">設定するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-109">The callback function being set.</span></span>  
  
## <span data-ttu-id="d0ab2-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d0ab2-110">Return Value</span></span>  
 <span data-ttu-id="d0ab2-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d0ab2-112">注釈</span><span class="sxs-lookup"><span data-stu-id="d0ab2-112">Remarks</span></span>  
 <span data-ttu-id="d0ab2-113">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-113">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="d0ab2-114">コールバックは、ホストがガベージ コレクションを準備するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-114">The callback can be used by hosts to prepare for garbage collection.</span></span> <span data-ttu-id="d0ab2-115">たとえば、Chakra オブジェクトに対する不要な参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="d0ab2-115">For example, by releasing unnecessary references on Chakra objects.</span></span>  
  
## <span data-ttu-id="d0ab2-116">要件</span><span class="sxs-lookup"><span data-stu-id="d0ab2-116">Requirements</span></span>  
 <span data-ttu-id="d0ab2-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d0ab2-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d0ab2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0ab2-118">See Also</span></span>  
 [<span data-ttu-id="d0ab2-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="d0ab2-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
