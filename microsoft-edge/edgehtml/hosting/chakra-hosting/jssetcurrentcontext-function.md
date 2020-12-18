---
description: スレッドの現在のスクリプト コンテキストを設定します。
title: JsSetCurrentContext 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60ec1760c582f1f6771a5af64f59c4a77b1a43f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234686"
---
# <span data-ttu-id="1dc2e-103">JsSetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="1dc2e-103">JsSetCurrentContext Function</span></span>

<span data-ttu-id="1dc2e-104">スレッドの現在のスクリプト コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="1dc2e-104">Sets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="1dc2e-105">構文</span><span class="sxs-lookup"><span data-stu-id="1dc2e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### <span data-ttu-id="1dc2e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1dc2e-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="1dc2e-107">最新にするスクリプト コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="1dc2e-107">The script context to make current.</span></span>  
  
## <span data-ttu-id="1dc2e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1dc2e-108">Return Value</span></span>  
 <span data-ttu-id="1dc2e-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1dc2e-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  

## <span data-ttu-id="1dc2e-110">例</span><span class="sxs-lookup"><span data-stu-id="1dc2e-110">Example</span></span>

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

## <span data-ttu-id="1dc2e-111">要件</span><span class="sxs-lookup"><span data-stu-id="1dc2e-111">Requirements</span></span>  
 <span data-ttu-id="1dc2e-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="1dc2e-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1dc2e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dc2e-113">See Also</span></span>  
 [<span data-ttu-id="1dc2e-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="1dc2e-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
