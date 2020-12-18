---
description: 外部データを格納する新しいオブジェクトを作成します。
title: JsCreateExternalObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateExternalObject
helpviewer_keywords:
- JsCreateExternalObject function
ms.assetid: 6bcef506-93fb-429b-b06a-a971ff0b71f3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4d402c3d379a16186daaba601c7f830c53a9a953
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235040"
---
# <span data-ttu-id="ce630-103">JsCreateExternalObject 関数</span><span class="sxs-lookup"><span data-stu-id="ce630-103">JsCreateExternalObject Function</span></span>

<span data-ttu-id="ce630-104">外部データを格納する新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce630-104">Creates a new object that stores some external data.</span></span>
  
## <span data-ttu-id="ce630-105">構文</span><span class="sxs-lookup"><span data-stu-id="ce630-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalObject(  
   _In_opt_ void *data,  
   _In_opt_ JsFinalizeCallback finalizeCallback,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="ce630-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce630-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="ce630-107">オブジェクトが表す外部データ。</span><span class="sxs-lookup"><span data-stu-id="ce630-107">External data that the object will represent.</span></span> <span data-ttu-id="ce630-108">null の場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce630-108">May be null.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="ce630-109">オブジェクトが最終処理される場合のコールバック。</span><span class="sxs-lookup"><span data-stu-id="ce630-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="ce630-110">null の場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce630-110">May be null.</span></span>  
  
 `object`  
 <span data-ttu-id="ce630-111">新しいオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce630-111">The new object.</span></span>  
  
## <span data-ttu-id="ce630-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ce630-112">Return Value</span></span>  
 <span data-ttu-id="ce630-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ce630-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ce630-114">注釈</span><span class="sxs-lookup"><span data-stu-id="ce630-114">Remarks</span></span>  
 <span data-ttu-id="ce630-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce630-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ce630-116">要件</span><span class="sxs-lookup"><span data-stu-id="ce630-116">Requirements</span></span>  
 <span data-ttu-id="ce630-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ce630-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ce630-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce630-118">See Also</span></span>  
 [<span data-ttu-id="ce630-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ce630-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
