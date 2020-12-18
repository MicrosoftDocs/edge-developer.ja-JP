---
description: JavaScript 記号を作成します。
title: JsCreateSymbol 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2fccc5d9-f857-46cd-9aeb-f0a2e7cdee6b
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a2f77f477aeebac150635d93cbd0cd043357256
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234743"
---
# <span data-ttu-id="03d52-103">JsCreateSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="03d52-103">JsCreateSymbol Function</span></span>

<span data-ttu-id="03d52-104">JavaScript 記号を作成します。</span><span class="sxs-lookup"><span data-stu-id="03d52-104">Creates a JavaScript symbol.</span></span>
  
## <span data-ttu-id="03d52-105">構文</span><span class="sxs-lookup"><span data-stu-id="03d52-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSymbol(  
   _In_ JsValueRef description,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="03d52-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03d52-106">Parameters</span></span>  
 `description`  
 <span data-ttu-id="03d52-107">記号の文字列の説明。</span><span class="sxs-lookup"><span data-stu-id="03d52-107">The string description of the symbol.</span></span> <span data-ttu-id="03d52-108">null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="03d52-108">Can be null.</span></span>  
  
 `result`  
 <span data-ttu-id="03d52-109">新しい記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="03d52-109">The new symbol.</span></span>  
  
## <span data-ttu-id="03d52-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="03d52-110">Return Value</span></span>  
 <span data-ttu-id="03d52-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="03d52-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="03d52-112">注釈</span><span class="sxs-lookup"><span data-stu-id="03d52-112">Remarks</span></span>  
 <span data-ttu-id="03d52-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="03d52-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="03d52-114">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="03d52-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="03d52-115">要件</span><span class="sxs-lookup"><span data-stu-id="03d52-115">Requirements</span></span>  
 <span data-ttu-id="03d52-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="03d52-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="03d52-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="03d52-117">See Also</span></span>  
 [<span data-ttu-id="03d52-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="03d52-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
