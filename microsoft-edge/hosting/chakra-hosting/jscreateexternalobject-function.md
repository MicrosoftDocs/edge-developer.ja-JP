---
description: 外部データを格納する新しいオブジェクトを作成します。
title: JsCreateExternalObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateExternalObject
helpviewer_keywords:
- JsCreateExternalObject function
ms.assetid: 6bcef506-93fb-429b-b06a-a971ff0b71f3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9a68f4befea7dc7c3369bcade475e29d53342730
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569366"
---
# <span data-ttu-id="4d5cd-103">JsCreateExternalObject 関数</span><span class="sxs-lookup"><span data-stu-id="4d5cd-103">JsCreateExternalObject Function</span></span>
<span data-ttu-id="4d5cd-104">外部データを格納する新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-104">Creates a new object that stores some external data.</span></span>
  
## <span data-ttu-id="4d5cd-105">構文</span><span class="sxs-lookup"><span data-stu-id="4d5cd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalObject(  
   _In_opt_ void *data,  
   _In_opt_ JsFinalizeCallback finalizeCallback,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="4d5cd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d5cd-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="4d5cd-107">オブジェクトが表す外部データ。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-107">External data that the object will represent.</span></span> <span data-ttu-id="4d5cd-108">は null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-108">May be null.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="4d5cd-109">オブジェクトが完了するときのためのコールバック。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="4d5cd-110">は null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-110">May be null.</span></span>  
  
 `object`  
 <span data-ttu-id="4d5cd-111">新しいオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-111">The new object.</span></span>  
  
## <span data-ttu-id="4d5cd-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d5cd-112">Return Value</span></span>  
 <span data-ttu-id="4d5cd-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4d5cd-114">注釈</span><span class="sxs-lookup"><span data-stu-id="4d5cd-114">Remarks</span></span>  
 <span data-ttu-id="4d5cd-115">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d5cd-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4d5cd-116">要件</span><span class="sxs-lookup"><span data-stu-id="4d5cd-116">Requirements</span></span>  
 <span data-ttu-id="4d5cd-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="4d5cd-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4d5cd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d5cd-118">See Also</span></span>  
 [<span data-ttu-id="4d5cd-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4d5cd-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)