---
description: 'ランタイムでのスクリプトの実行を有効にします。 '
title: JsEnableRuntimeExecution 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd8071fd3c120d1c2029a3c7a3d9c39e68c4cfd2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570474"
---
# <span data-ttu-id="056d5-103">JsEnableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="056d5-103">JsEnableRuntimeExecution Function</span></span>
<span data-ttu-id="056d5-104">ランタイムでのスクリプトの実行を有効にします。</span><span class="sxs-lookup"><span data-stu-id="056d5-104">Enables script execution in a runtime.</span></span>  
  
## <span data-ttu-id="056d5-105">構文</span><span class="sxs-lookup"><span data-stu-id="056d5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="056d5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="056d5-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="056d5-107">有効にするランタイム。</span><span class="sxs-lookup"><span data-stu-id="056d5-107">The runtime to be enabled.</span></span>  
  
## <span data-ttu-id="056d5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="056d5-108">Return Value</span></span>  
 <span data-ttu-id="056d5-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="056d5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="056d5-110">注釈</span><span class="sxs-lookup"><span data-stu-id="056d5-110">Remarks</span></span>  
 <span data-ttu-id="056d5-111">スクリプト実行が既に有効になっているランタイムでスクリプトの実行を有効にすることは、何の操作でもありません。</span><span class="sxs-lookup"><span data-stu-id="056d5-111">Enabling script execution in a runtime that already has script execution enabled is a no-op.</span></span>  
  
## <span data-ttu-id="056d5-112">要件</span><span class="sxs-lookup"><span data-stu-id="056d5-112">Requirements</span></span>  
 <span data-ttu-id="056d5-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="056d5-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="056d5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="056d5-114">See Also</span></span>  
 [<span data-ttu-id="056d5-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="056d5-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)