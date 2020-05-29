---
description: ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。
title: JsIsRuntimeExecutionDisabled 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6968a31c9acab70589fe58c86cc566e631778c3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569290"
---
# <span data-ttu-id="aef81-103">JsIsRuntimeExecutionDisabled 関数</span><span class="sxs-lookup"><span data-stu-id="aef81-103">JsIsRuntimeExecutionDisabled Function</span></span>
<span data-ttu-id="aef81-104">ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="aef81-104">Returns a value that indicates whether script execution is disabled in the runtime.</span></span>  
  
## <span data-ttu-id="aef81-105">構文</span><span class="sxs-lookup"><span data-stu-id="aef81-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <span data-ttu-id="aef81-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aef81-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="aef81-107">実行が無効になっているかどうかを確認するランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="aef81-107">Specifies the runtime to check if execution is disabled.</span></span>  
  
 `isDisabled`  
 `true` <span data-ttu-id="aef81-108">実行され `false` ていない場合は、</span><span class="sxs-lookup"><span data-stu-id="aef81-108">if execution is disabled, `false` otherwise.</span></span>  
  
## <span data-ttu-id="aef81-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="aef81-109">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="aef81-110">操作に成功した場合は、エラーコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="aef81-110">if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="aef81-111">要件</span><span class="sxs-lookup"><span data-stu-id="aef81-111">Requirements</span></span>  
 <span data-ttu-id="aef81-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="aef81-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="aef81-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="aef81-113">See Also</span></span>  
 [<span data-ttu-id="aef81-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="aef81-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)