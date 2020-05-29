---
description: JavaScript のシンボルを作成します。
title: JsCreateSymbol 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2fccc5d9-f857-46cd-9aeb-f0a2e7cdee6b
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a4e634e6f0726ca32ad1056129186ce941edb77b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569352"
---
# <span data-ttu-id="0f849-103">JsCreateSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="0f849-103">JsCreateSymbol Function</span></span>
<span data-ttu-id="0f849-104">JavaScript のシンボルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f849-104">Creates a JavaScript symbol.</span></span>
  
## <span data-ttu-id="0f849-105">構文</span><span class="sxs-lookup"><span data-stu-id="0f849-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSymbol(  
   _In_ JsValueRef description,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0f849-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f849-106">Parameters</span></span>  
 `description`  
 <span data-ttu-id="0f849-107">記号の文字列の説明。</span><span class="sxs-lookup"><span data-stu-id="0f849-107">The string description of the symbol.</span></span> <span data-ttu-id="0f849-108">Null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f849-108">Can be null.</span></span>  
  
 `result`  
 <span data-ttu-id="0f849-109">新しい記号。</span><span class="sxs-lookup"><span data-stu-id="0f849-109">The new symbol.</span></span>  
  
## <span data-ttu-id="0f849-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f849-110">Return Value</span></span>  
 <span data-ttu-id="0f849-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0f849-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0f849-112">注釈</span><span class="sxs-lookup"><span data-stu-id="0f849-112">Remarks</span></span>  
 <span data-ttu-id="0f849-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f849-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0f849-114">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0f849-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0f849-115">要件</span><span class="sxs-lookup"><span data-stu-id="0f849-115">Requirements</span></span>  
 <span data-ttu-id="0f849-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0f849-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0f849-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f849-117">See Also</span></span>  
 [<span data-ttu-id="0f849-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0f849-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)