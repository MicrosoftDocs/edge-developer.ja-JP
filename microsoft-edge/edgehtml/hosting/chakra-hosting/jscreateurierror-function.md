---
description: 新しい JavaScript URIError エラー オブジェクトを作成します。
title: JsCreateURIError 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateURIError
helpviewer_keywords:
- JsCreateURIError function
ms.assetid: 711fd237-12a2-4ff0-b58a-ad74c91e79fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 88e6c1fc04607b3be088e297d1fa86f9374bcb03
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234665"
---
# <span data-ttu-id="7d886-103">JsCreateURIError 関数</span><span class="sxs-lookup"><span data-stu-id="7d886-103">JsCreateURIError Function</span></span>

<span data-ttu-id="7d886-104">新しい JavaScript URIError エラー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d886-104">Creates a new JavaScript URIError error object.</span></span>  
  
## <span data-ttu-id="7d886-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d886-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateURIError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="7d886-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d886-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="7d886-107">エラー オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="7d886-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="7d886-108">新しいエラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7d886-108">The new error object.</span></span>  
  
## <span data-ttu-id="7d886-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7d886-109">Return Value</span></span>  
 <span data-ttu-id="7d886-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7d886-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7d886-111">注釈</span><span class="sxs-lookup"><span data-stu-id="7d886-111">Remarks</span></span>  
 <span data-ttu-id="7d886-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d886-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7d886-113">要件</span><span class="sxs-lookup"><span data-stu-id="7d886-113">Requirements</span></span>  
 <span data-ttu-id="7d886-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7d886-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7d886-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d886-115">See Also</span></span>  
 [<span data-ttu-id="7d886-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="7d886-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
