---
description: Chakra ガーベジコレクターによって所有されているオブジェクトへの参照。
title: JsRef Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f5ce1ada67a4530ba57345b90c0b7deba6954c7c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570407"
---
# <span data-ttu-id="6e55a-103">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="6e55a-103">JsRef Typedef</span></span>
<span data-ttu-id="6e55a-104">Chakra ガーベジコレクターによって所有されているオブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="6e55a-104">A reference to an object owned by the Chakra garbage collector.</span></span>  
  
## <span data-ttu-id="6e55a-105">構文</span><span class="sxs-lookup"><span data-stu-id="6e55a-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRef;  
```  
  
## <span data-ttu-id="6e55a-106">注釈</span><span class="sxs-lookup"><span data-stu-id="6e55a-106">Remarks</span></span>  
 <span data-ttu-id="6e55a-107">Chakra ランタイムは、ローカル変数またはパラメーター (スタック上) に保存されている限り、JsRef 参照を自動的に追跡します。</span><span class="sxs-lookup"><span data-stu-id="6e55a-107">A Chakra runtime will automatically track JsRef references as long as they are on stored in local variables or in parameters (i.e. on the stack).</span></span> <span data-ttu-id="6e55a-108">スタック以外の場所に JsRef を保存するには、JsAddRef と JsRelease を呼び出してオブジェクトの有効期間を管理する必要があります。そうでない場合、ガベージコレクターは、まだ使用中にオブジェクトを解放できます。</span><span class="sxs-lookup"><span data-stu-id="6e55a-108">Storing a JsRef somewhere other than on the stack requires calling JsAddRef and JsRelease to manage the lifetime of the object, otherwise the garbage collector may free the object while it is still in use.</span></span>  
  
## <span data-ttu-id="6e55a-109">要件</span><span class="sxs-lookup"><span data-stu-id="6e55a-109">Requirements</span></span>  
 <span data-ttu-id="6e55a-110">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="6e55a-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6e55a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e55a-111">See Also</span></span>  
 [<span data-ttu-id="6e55a-112">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6e55a-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)