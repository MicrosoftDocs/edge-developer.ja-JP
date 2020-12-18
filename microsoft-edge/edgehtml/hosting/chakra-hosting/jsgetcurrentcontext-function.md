---
description: スレッドの現在のスクリプト コンテキストを取得します。
title: JsGetCurrentContext 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetCurrentContext
helpviewer_keywords:
- JsGetCurrentContext function
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a43b9a6d4413ef1dc1b66321d6078aef84a0645f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234778"
---
# <span data-ttu-id="6865b-103">JsGetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="6865b-103">JsGetCurrentContext Function</span></span>

<span data-ttu-id="6865b-104">スレッドの現在のスクリプト コンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6865b-104">Gets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="6865b-105">構文</span><span class="sxs-lookup"><span data-stu-id="6865b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### <span data-ttu-id="6865b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6865b-106">Parameters</span></span>  
 `currentContext`  
 <span data-ttu-id="6865b-107">スレッド上の現在のスクリプト コンテキスト。現在のスクリプト コンテキストがない場合は null。</span><span class="sxs-lookup"><span data-stu-id="6865b-107">The current script context on the thread, null if there is no current script context.</span></span>  
  
## <span data-ttu-id="6865b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6865b-108">Return Value</span></span>  
 <span data-ttu-id="6865b-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6865b-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6865b-110">要件</span><span class="sxs-lookup"><span data-stu-id="6865b-110">Requirements</span></span>  
 <span data-ttu-id="6865b-111">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6865b-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6865b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6865b-112">See Also</span></span>  
 [<span data-ttu-id="6865b-113">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="6865b-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
