---
description: 'ランタイムでのスクリプトの実行を有効にします。 '
title: JsEnableRuntimeExecution 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e87191197f70898b2f69d138026edd4e75cd5114
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234726"
---
# <span data-ttu-id="2e71e-103">JsEnableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="2e71e-103">JsEnableRuntimeExecution Function</span></span>

<span data-ttu-id="2e71e-104">ランタイムでのスクリプトの実行を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e71e-104">Enables script execution in a runtime.</span></span>  
  
## <span data-ttu-id="2e71e-105">構文</span><span class="sxs-lookup"><span data-stu-id="2e71e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="2e71e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e71e-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="2e71e-107">有効にするランタイム。</span><span class="sxs-lookup"><span data-stu-id="2e71e-107">The runtime to be enabled.</span></span>  
  
## <span data-ttu-id="2e71e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2e71e-108">Return Value</span></span>  
 <span data-ttu-id="2e71e-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="2e71e-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2e71e-110">注釈</span><span class="sxs-lookup"><span data-stu-id="2e71e-110">Remarks</span></span>  
 <span data-ttu-id="2e71e-111">既にスクリプト実行が有効になっているランタイムでスクリプト実行を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e71e-111">Enabling script execution in a runtime that already has script execution enabled is a no-op.</span></span>  
  
## <span data-ttu-id="2e71e-112">要件</span><span class="sxs-lookup"><span data-stu-id="2e71e-112">Requirements</span></span>  
 <span data-ttu-id="2e71e-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2e71e-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2e71e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e71e-114">See Also</span></span>  
 [<span data-ttu-id="2e71e-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="2e71e-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
