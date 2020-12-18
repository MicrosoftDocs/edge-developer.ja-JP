---
description: 新しい JavaScript ReferenceError エラー オブジェクトを作成します。
title: JsCreateReferenceError 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateReferenceError
helpviewer_keywords:
- JsCreateReferenceError function
ms.assetid: 1d0b2339-4bea-4dd0-a46a-4dcbf0be3bd8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fc8f10c443d6ca019c1460c84344bf04513e44b9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234748"
---
# <span data-ttu-id="cdc08-103">JsCreateReferenceError 関数</span><span class="sxs-lookup"><span data-stu-id="cdc08-103">JsCreateReferenceError Function</span></span>

<span data-ttu-id="cdc08-104">新しい JavaScript ReferenceError エラー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cdc08-104">Creates a new JavaScript ReferenceError error object.</span></span>
  
## <span data-ttu-id="cdc08-105">構文</span><span class="sxs-lookup"><span data-stu-id="cdc08-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateReferenceError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="cdc08-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cdc08-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="cdc08-107">エラー オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="cdc08-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="cdc08-108">新しいエラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cdc08-108">The new error object.</span></span>  
  
## <span data-ttu-id="cdc08-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="cdc08-109">Return Value</span></span>  
 <span data-ttu-id="cdc08-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="cdc08-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="cdc08-111">注釈</span><span class="sxs-lookup"><span data-stu-id="cdc08-111">Remarks</span></span>  
 <span data-ttu-id="cdc08-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="cdc08-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="cdc08-113">要件</span><span class="sxs-lookup"><span data-stu-id="cdc08-113">Requirements</span></span>  
 <span data-ttu-id="cdc08-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="cdc08-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cdc08-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdc08-115">See Also</span></span>  
 [<span data-ttu-id="cdc08-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="cdc08-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
