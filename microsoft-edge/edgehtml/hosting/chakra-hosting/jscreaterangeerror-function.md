---
description: 新しい JavaScript RangeError エラー オブジェクトを作成します。
title: JsCreateRangeError 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRangeError
helpviewer_keywords:
- JsCreateRangeError function
ms.assetid: 0ab05de7-57af-4cfd-9aa5-0a69a893cc97
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 72cf882d5f9517f0f05d9e3367283f5f531dbdb3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234692"
---
# <span data-ttu-id="1961b-103">JsCreateRangeError 関数</span><span class="sxs-lookup"><span data-stu-id="1961b-103">JsCreateRangeError Function</span></span>

<span data-ttu-id="1961b-104">新しい JavaScript RangeError エラー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1961b-104">Creates a new JavaScript RangeError error object.</span></span>
  
## <span data-ttu-id="1961b-105">構文</span><span class="sxs-lookup"><span data-stu-id="1961b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateRangeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="1961b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1961b-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="1961b-107">エラー オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="1961b-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="1961b-108">新しいエラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1961b-108">The new error object.</span></span>  
  
## <span data-ttu-id="1961b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1961b-109">Return Value</span></span>  
 <span data-ttu-id="1961b-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1961b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1961b-111">注釈</span><span class="sxs-lookup"><span data-stu-id="1961b-111">Remarks</span></span>  
 <span data-ttu-id="1961b-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1961b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1961b-113">要件</span><span class="sxs-lookup"><span data-stu-id="1961b-113">Requirements</span></span>  
 <span data-ttu-id="1961b-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="1961b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1961b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1961b-115">See Also</span></span>  
 [<span data-ttu-id="1961b-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="1961b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
