---
description: スクリプトコンテキストへの参照。
title: JsContextRef Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 80e4b5034079f4f0d26da070bd209aa41bf3475f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569390"
---
# <span data-ttu-id="d37eb-103">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="d37eb-103">JsContextRef Typedef</span></span>
<span data-ttu-id="d37eb-104">スクリプトコンテキストへの参照。</span><span class="sxs-lookup"><span data-stu-id="d37eb-104">A reference to a script context.</span></span>  
  
## <span data-ttu-id="d37eb-105">構文</span><span class="sxs-lookup"><span data-stu-id="d37eb-105">Syntax</span></span>  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## <span data-ttu-id="d37eb-106">注釈</span><span class="sxs-lookup"><span data-stu-id="d37eb-106">Remarks</span></span>  
 <span data-ttu-id="d37eb-107">各スクリプトコンテキストには、他のスクリプトコンテキストのグローバルオブジェクトとは異なる、固有のグローバルオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d37eb-107">Each script context contains its own global object, distinct from the global object in other script contexts.</span></span>  
  
 <span data-ttu-id="d37eb-108">多くの Chakra ホスティング Api には、を使って設定できる "アクティブな" スクリプトコンテキストが必要 `JsSetCurrentContext` です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-108">Many Chakra hosting APIs require an "active" script context, which can be set using `JsSetCurrentContext`.</span></span> <span data-ttu-id="d37eb-109">現在のコンテキストを設定する必要がある Chakra ホスティング Api は、ドキュメントに明示的に含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-109">Chakra hosting APIs that require a current context to be set will note that explicitly in their documentation.</span></span>  
  
## <span data-ttu-id="d37eb-110">要件</span><span class="sxs-lookup"><span data-stu-id="d37eb-110">Requirements</span></span>  
 <span data-ttu-id="d37eb-111">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="d37eb-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d37eb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d37eb-112">See Also</span></span>  
 [<span data-ttu-id="d37eb-113">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d37eb-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)