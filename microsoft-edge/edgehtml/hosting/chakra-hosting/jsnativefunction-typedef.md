---
description: 関数コールバック。
title: JsNativeFunction Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 891fe55f776e8519a5d3c187104b2bc326336482
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234349"
---
# <span data-ttu-id="f7e9b-103">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="f7e9b-103">JsNativeFunction Typedef</span></span>

<span data-ttu-id="f7e9b-104">関数コールバック。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-104">A function callback.</span></span>  
  
## <span data-ttu-id="f7e9b-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7e9b-105">Syntax</span></span>  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <span data-ttu-id="f7e9b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7e9b-106">Parameters</span></span>  
 <span data-ttu-id="f7e9b-107">呼び出し先</span><span class="sxs-lookup"><span data-stu-id="f7e9b-107">callee</span></span>  
 <span data-ttu-id="f7e9b-108">呼 `Function` び出される関数を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-108">A `Function` object that represents the function being invoked.</span></span>  
  
 <span data-ttu-id="f7e9b-109">isConstructCall</span><span class="sxs-lookup"><span data-stu-id="f7e9b-109">isConstructCall</span></span>  
 <span data-ttu-id="f7e9b-110">これが通常の通話か「新しい」呼び出しかを示します。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-110">Indicates whether this is a regular call or a 'new' call.</span></span>  
  
 <span data-ttu-id="f7e9b-111">arguments</span><span class="sxs-lookup"><span data-stu-id="f7e9b-111">arguments</span></span>  
 <span data-ttu-id="f7e9b-112">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-112">The arguments to the call.</span></span>  
  
 <span data-ttu-id="f7e9b-113">argumentCount</span><span class="sxs-lookup"><span data-stu-id="f7e9b-113">argumentCount</span></span>  
 <span data-ttu-id="f7e9b-114">引数の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-114">The number of arguments.</span></span>  
  
## <span data-ttu-id="f7e9b-115">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="f7e9b-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="f7e9b-116">呼び出しの結果 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f7e9b-116">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="f7e9b-117">要件</span><span class="sxs-lookup"><span data-stu-id="f7e9b-117">Requirements</span></span>  
 <span data-ttu-id="f7e9b-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f7e9b-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f7e9b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7e9b-119">See Also</span></span>  
 [<span data-ttu-id="f7e9b-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f7e9b-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
