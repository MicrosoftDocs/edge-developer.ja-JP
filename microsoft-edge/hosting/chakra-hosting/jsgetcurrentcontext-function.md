---
description: スレッド上の現在のスクリプトコンテキストを取得します。
title: JsGetCurrentContext 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetCurrentContext
helpviewer_keywords:
- JsGetCurrentContext function
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 78f04674aab8783c43f22516903669e0f9b7543b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569329"
---
# <span data-ttu-id="5eeb4-103">JsGetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="5eeb4-103">JsGetCurrentContext Function</span></span>
<span data-ttu-id="5eeb4-104">スレッド上の現在のスクリプトコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-104">Gets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="5eeb4-105">構文</span><span class="sxs-lookup"><span data-stu-id="5eeb4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### <span data-ttu-id="5eeb4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5eeb4-106">Parameters</span></span>  
 `currentContext`  
 <span data-ttu-id="5eeb4-107">スレッドの現在のスクリプトコンテキスト。現在のスクリプトコンテキストが存在しない場合は null。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-107">The current script context on the thread, null if there is no current script context.</span></span>  
  
## <span data-ttu-id="5eeb4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5eeb4-108">Return Value</span></span>  
 <span data-ttu-id="5eeb4-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5eeb4-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5eeb4-110">要件</span><span class="sxs-lookup"><span data-stu-id="5eeb4-110">Requirements</span></span>  
 <span data-ttu-id="5eeb4-111">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5eeb4-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5eeb4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5eeb4-112">See Also</span></span>  
 [<span data-ttu-id="5eeb4-113">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5eeb4-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)