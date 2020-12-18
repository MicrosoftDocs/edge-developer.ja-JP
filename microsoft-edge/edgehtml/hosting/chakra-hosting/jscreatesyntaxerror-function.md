---
description: 新しい JavaScript SyntaxError エラー オブジェクトを作成します。
title: JsCreateSyntaxError 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateSyntaxError
helpviewer_keywords:
- JsCreateSyntaxError function
ms.assetid: 839845fc-60c4-4ffc-bfcc-fd7a8f06126f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7d6534bfa2b59cb2f6ab68c231d7a97c84876d62
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234881"
---
# <span data-ttu-id="f3c1d-103">JsCreateSyntaxError 関数</span><span class="sxs-lookup"><span data-stu-id="f3c1d-103">JsCreateSyntaxError Function</span></span>

<span data-ttu-id="f3c1d-104">新しい JavaScript SyntaxError エラー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3c1d-104">Creates a new JavaScript SyntaxError error object.</span></span>  
  
## <span data-ttu-id="f3c1d-105">構文</span><span class="sxs-lookup"><span data-stu-id="f3c1d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSyntaxError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="f3c1d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3c1d-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="f3c1d-107">エラー オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="f3c1d-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="f3c1d-108">新しいエラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f3c1d-108">The new error object.</span></span>  
  
## <span data-ttu-id="f3c1d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f3c1d-109">Return Value</span></span>  
 <span data-ttu-id="f3c1d-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f3c1d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f3c1d-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f3c1d-111">Remarks</span></span>  
 <span data-ttu-id="f3c1d-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3c1d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f3c1d-113">要件</span><span class="sxs-lookup"><span data-stu-id="f3c1d-113">Requirements</span></span>  
 <span data-ttu-id="f3c1d-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f3c1d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f3c1d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3c1d-115">See Also</span></span>  
 [<span data-ttu-id="f3c1d-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f3c1d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
