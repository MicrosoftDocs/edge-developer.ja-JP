---
description: 現在のコンテキストのランタイムを例外の状態に設定します。
title: JsSetException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 75d2895a725c622a0b46887d10154c3a0c56c7e9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570382"
---
# <span data-ttu-id="0611c-103">JsSetException 関数</span><span class="sxs-lookup"><span data-stu-id="0611c-103">JsSetException Function</span></span>
<span data-ttu-id="0611c-104">現在のコンテキストのランタイムを例外の状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="0611c-104">Sets the runtime of the current context to an exception state.</span></span>  
  
## <span data-ttu-id="0611c-105">構文</span><span class="sxs-lookup"><span data-stu-id="0611c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <span data-ttu-id="0611c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0611c-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="0611c-107">現在のコンテキストの実行時に設定する JavaScript 例外。</span><span class="sxs-lookup"><span data-stu-id="0611c-107">The JavaScript exception to set for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="0611c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0611c-108">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="0611c-109">エンジンが例外状態に設定されていた場合は、エラーコードがありません。</span><span class="sxs-lookup"><span data-stu-id="0611c-109">if the engine was set into an exception state, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0611c-110">注釈</span><span class="sxs-lookup"><span data-stu-id="0611c-110">Remarks</span></span>  
 <span data-ttu-id="0611c-111">現在のコンテキストの実行時に既に例外状態になっている場合は、この API から戻り `JsErrorInExceptionState` ます。</span><span class="sxs-lookup"><span data-stu-id="0611c-111">If the runtime of the current context is already in an exception state, this API will return `JsErrorInExceptionState`.</span></span>  
  
 <span data-ttu-id="0611c-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0611c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0611c-113">要件</span><span class="sxs-lookup"><span data-stu-id="0611c-113">Requirements</span></span>  
 <span data-ttu-id="0611c-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0611c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0611c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0611c-115">See Also</span></span>  
 [<span data-ttu-id="0611c-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0611c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)