---
description: オブジェクトの指定したインデックスにある値を削除します。
title: JsDeleteIndexedProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteIndexedProperty
helpviewer_keywords:
- JsDeleteIndexedProperty function
ms.assetid: cc876839-2ecd-41a8-82d0-c19b3de944e3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1340b0204d3845d4a9bd3f18a58ec125a82d2bc0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234873"
---
# <span data-ttu-id="378d8-103">JsDeleteIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="378d8-103">JsDeleteIndexedProperty Function</span></span>

<span data-ttu-id="378d8-104">オブジェクトの指定したインデックスにある値を削除します。</span><span class="sxs-lookup"><span data-stu-id="378d8-104">Delete the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="378d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="378d8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index  
);  
```  
  
#### <span data-ttu-id="378d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="378d8-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="378d8-107">操作対象のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="378d8-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="378d8-108">削除するインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="378d8-108">The index to delete.</span></span>  
  
## <span data-ttu-id="378d8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="378d8-109">Return Value</span></span>  
 <span data-ttu-id="378d8-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="378d8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="378d8-111">注釈</span><span class="sxs-lookup"><span data-stu-id="378d8-111">Remarks</span></span>  
 <span data-ttu-id="378d8-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="378d8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="378d8-113">要件</span><span class="sxs-lookup"><span data-stu-id="378d8-113">Requirements</span></span>  
 <span data-ttu-id="378d8-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="378d8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="378d8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="378d8-115">See Also</span></span>  
 [<span data-ttu-id="378d8-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="378d8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
