---
description: 新しい JavaScript TypeError エラー オブジェクトを作成します。
title: JsCreateTypeError 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateTypeError
helpviewer_keywords:
- JsCreateTypeError function
ms.assetid: 8ef7bb77-2c98-482a-bccb-1f0fe2b826f5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 627dfdc6f01f0708366720a957b3784fc7bb59a4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234877"
---
# <span data-ttu-id="87f37-103">JsCreateTypeError 関数</span><span class="sxs-lookup"><span data-stu-id="87f37-103">JsCreateTypeError Function</span></span>

<span data-ttu-id="87f37-104">新しい JavaScript TypeError エラー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="87f37-104">Creates a new JavaScript TypeError error object.</span></span>  
  
## <span data-ttu-id="87f37-105">構文</span><span class="sxs-lookup"><span data-stu-id="87f37-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="87f37-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87f37-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="87f37-107">エラー オブジェクトのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="87f37-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="87f37-108">新しいエラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="87f37-108">The new error object.</span></span>  
  
## <span data-ttu-id="87f37-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="87f37-109">Return Value</span></span>  
 <span data-ttu-id="87f37-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="87f37-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="87f37-111">注釈</span><span class="sxs-lookup"><span data-stu-id="87f37-111">Remarks</span></span>  
 <span data-ttu-id="87f37-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="87f37-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="87f37-113">要件</span><span class="sxs-lookup"><span data-stu-id="87f37-113">Requirements</span></span>  
 <span data-ttu-id="87f37-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="87f37-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="87f37-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="87f37-115">See Also</span></span>  
 [<span data-ttu-id="87f37-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="87f37-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
