---
description: スレッドの現在のスクリプトコンテキストを設定します。
title: JsSetCurrentContext 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57620ad0e986034791ec07765d7cc115b958d661
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570384"
---
# <span data-ttu-id="aa8c4-103">JsSetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="aa8c4-103">JsSetCurrentContext Function</span></span>
<span data-ttu-id="aa8c4-104">スレッドの現在のスクリプトコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa8c4-104">Sets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="aa8c4-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa8c4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### <span data-ttu-id="aa8c4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa8c4-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="aa8c4-107">現在のスクリプトコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="aa8c4-107">The script context to make current.</span></span>  
  
## <span data-ttu-id="aa8c4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa8c4-108">Return Value</span></span>  
 <span data-ttu-id="aa8c4-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="aa8c4-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  

## <span data-ttu-id="aa8c4-110">例</span><span class="sxs-lookup"><span data-stu-id="aa8c4-110">Example</span></span>

```cpp
JsRuntimeHandle runtime;
JsContextRef context;

// Create a runtime.
JsCreateRuntime(JsRuntimeAttributeNone, nullptr, &runtime);

// Create an execution context.
JsCreateContext(runtime, &context);

// Now set the current execution context.
JsSetCurrentContext(context);
```

## <span data-ttu-id="aa8c4-111">要件</span><span class="sxs-lookup"><span data-stu-id="aa8c4-111">Requirements</span></span>  
 <span data-ttu-id="aa8c4-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="aa8c4-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="aa8c4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa8c4-113">See Also</span></span>  
 [<span data-ttu-id="aa8c4-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="aa8c4-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)