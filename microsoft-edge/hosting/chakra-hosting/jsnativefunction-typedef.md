---
description: 関数のコールバック。
title: JsNativeFunction Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c0b73a11d3a0b2ed0867ef001f3c29c5643132a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569287"
---
# <span data-ttu-id="48287-103">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="48287-103">JsNativeFunction Typedef</span></span>
<span data-ttu-id="48287-104">関数のコールバック。</span><span class="sxs-lookup"><span data-stu-id="48287-104">A function callback.</span></span>  
  
## <span data-ttu-id="48287-105">構文</span><span class="sxs-lookup"><span data-stu-id="48287-105">Syntax</span></span>  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <span data-ttu-id="48287-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48287-106">Parameters</span></span>  
 <span data-ttu-id="48287-107">呼び出し先</span><span class="sxs-lookup"><span data-stu-id="48287-107">callee</span></span>  
 <span data-ttu-id="48287-108">`Function`呼び出される関数を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="48287-108">A `Function` object that represents the function being invoked.</span></span>  
  
 <span data-ttu-id="48287-109">Isの Tcall</span><span class="sxs-lookup"><span data-stu-id="48287-109">isConstructCall</span></span>  
 <span data-ttu-id="48287-110">これが通常の通話であるか、"新規" 通話であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="48287-110">Indicates whether this is a regular call or a 'new' call.</span></span>  
  
 <span data-ttu-id="48287-111">arguments</span><span class="sxs-lookup"><span data-stu-id="48287-111">arguments</span></span>  
 <span data-ttu-id="48287-112">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="48287-112">The arguments to the call.</span></span>  
  
 <span data-ttu-id="48287-113">argumentCount</span><span class="sxs-lookup"><span data-stu-id="48287-113">argumentCount</span></span>  
 <span data-ttu-id="48287-114">引数の数。</span><span class="sxs-lookup"><span data-stu-id="48287-114">The number of arguments.</span></span>  
  
## <span data-ttu-id="48287-115">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="48287-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="48287-116">通話の結果 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="48287-116">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="48287-117">要件</span><span class="sxs-lookup"><span data-stu-id="48287-117">Requirements</span></span>  
 <span data-ttu-id="48287-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="48287-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="48287-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="48287-119">See Also</span></span>  
 [<span data-ttu-id="48287-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="48287-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)