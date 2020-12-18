---
description: ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。
title: JsIsRuntimeExecutionDisabled 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ce59c77525abdb2dd6cac71dde1378264395e79
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234350"
---
# <span data-ttu-id="fb96a-103">JsIsRuntimeExecutionDisabled 関数</span><span class="sxs-lookup"><span data-stu-id="fb96a-103">JsIsRuntimeExecutionDisabled Function</span></span>

<span data-ttu-id="fb96a-104">ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="fb96a-104">Returns a value that indicates whether script execution is disabled in the runtime.</span></span>  
  
## <span data-ttu-id="fb96a-105">構文</span><span class="sxs-lookup"><span data-stu-id="fb96a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <span data-ttu-id="fb96a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb96a-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="fb96a-107">実行が無効になっているか確認するランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb96a-107">Specifies the runtime to check if execution is disabled.</span></span>  
  
 `isDisabled`  
 `true` <span data-ttu-id="fb96a-108">実行が無効な場合、 `false` それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="fb96a-108">if execution is disabled, `false` otherwise.</span></span>  
  
## <span data-ttu-id="fb96a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fb96a-109">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="fb96a-110">操作が成功した場合は失敗コード。</span><span class="sxs-lookup"><span data-stu-id="fb96a-110">if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fb96a-111">要件</span><span class="sxs-lookup"><span data-stu-id="fb96a-111">Requirements</span></span>  
 <span data-ttu-id="fb96a-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="fb96a-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fb96a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb96a-113">See Also</span></span>  
 [<span data-ttu-id="fb96a-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="fb96a-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
