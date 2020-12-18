---
description: オブジェクトが属しているスクリプト コンテキストを取得します。
title: JsGetContextOfObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9085f9156e4e0ca9e952fe51447185239082f975
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234783"
---
# <span data-ttu-id="6bb9c-103">JsGetContextOfObject 関数</span><span class="sxs-lookup"><span data-stu-id="6bb9c-103">JsGetContextOfObject Function</span></span>

<span data-ttu-id="6bb9c-104">オブジェクトが属しているスクリプト コンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6bb9c-104">Gets the script context that the object belongs to.</span></span>  
  
## <span data-ttu-id="6bb9c-105">構文</span><span class="sxs-lookup"><span data-stu-id="6bb9c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### <span data-ttu-id="6bb9c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bb9c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="6bb9c-107">コンテキストを取得するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6bb9c-107">The object to get the context from.</span></span>  
  
 `context`  
 <span data-ttu-id="6bb9c-108">オブジェクトが属するコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="6bb9c-108">The context the object belongs to.</span></span>  
  
## <span data-ttu-id="6bb9c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6bb9c-109">Return Value</span></span>  
 <span data-ttu-id="6bb9c-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6bb9c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6bb9c-111">注釈</span><span class="sxs-lookup"><span data-stu-id="6bb9c-111">Remarks</span></span>  
 <span data-ttu-id="6bb9c-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="6bb9c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="6bb9c-113">要件</span><span class="sxs-lookup"><span data-stu-id="6bb9c-113">Requirements</span></span>  
 <span data-ttu-id="6bb9c-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6bb9c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6bb9c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bb9c-115">See Also</span></span>  
 [<span data-ttu-id="6bb9c-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="6bb9c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
