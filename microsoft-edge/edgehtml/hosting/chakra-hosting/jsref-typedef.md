---
description: Chakra ガーベジ コレクターが所有するオブジェクトへの参照。
title: JsRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 69d13472b15b5d448908b5dafb2e3d7dc0ace7e4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234352"
---
# <span data-ttu-id="f4772-103">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="f4772-103">JsRef Typedef</span></span>

<span data-ttu-id="f4772-104">Chakra ガーベジ コレクターが所有するオブジェクトへの参照。</span><span class="sxs-lookup"><span data-stu-id="f4772-104">A reference to an object owned by the Chakra garbage collector.</span></span>  
  
## <span data-ttu-id="f4772-105">構文</span><span class="sxs-lookup"><span data-stu-id="f4772-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRef;  
```  
  
## <span data-ttu-id="f4772-106">注釈</span><span class="sxs-lookup"><span data-stu-id="f4772-106">Remarks</span></span>  
 <span data-ttu-id="f4772-107">Chakra ランタイムは、ローカル変数またはパラメーター (つまりスタック上) に格納されている限り、JsRef 参照を自動的に追跡します。</span><span class="sxs-lookup"><span data-stu-id="f4772-107">A Chakra runtime will automatically track JsRef references as long as they are on stored in local variables or in parameters (i.e. on the stack).</span></span> <span data-ttu-id="f4772-108">スタック以外の場所に JsRef を格納するには、オブジェクトの有効期間を管理するために JsAddRef と JsRelease を呼び出す必要があります。そうしないと、ガベージ コレクターは、オブジェクトがまだ使用されている間、オブジェクトを解放する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4772-108">Storing a JsRef somewhere other than on the stack requires calling JsAddRef and JsRelease to manage the lifetime of the object, otherwise the garbage collector may free the object while it is still in use.</span></span>  
  
## <span data-ttu-id="f4772-109">要件</span><span class="sxs-lookup"><span data-stu-id="f4772-109">Requirements</span></span>  
 <span data-ttu-id="f4772-110">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f4772-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f4772-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4772-111">See Also</span></span>  
 [<span data-ttu-id="f4772-112">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f4772-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
