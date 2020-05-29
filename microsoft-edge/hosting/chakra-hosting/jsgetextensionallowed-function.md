---
description: オブジェクトが拡張可能かどうかを示す値を返します。
title: JsGetExtensionAllowed 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetExtensionAllowed
helpviewer_keywords:
- JsGetExtensionAllowed function
ms.assetid: 839054a1-d643-47d9-89db-6a015bba0d91
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3baa6449294f7b055251d861a32095deb1bdfe9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569325"
---
# <span data-ttu-id="2be04-103">JsGetExtensionAllowed 関数</span><span class="sxs-lookup"><span data-stu-id="2be04-103">JsGetExtensionAllowed Function</span></span>
<span data-ttu-id="2be04-104">オブジェクトが拡張可能かどうかを示す値を返します。</span><span class="sxs-lookup"><span data-stu-id="2be04-104">Returns a value that indicates whether an object is extensible or not.</span></span>  
  
## <span data-ttu-id="2be04-105">構文</span><span class="sxs-lookup"><span data-stu-id="2be04-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExtensionAllowed(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="2be04-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2be04-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="2be04-107">テストするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2be04-107">The object to test.</span></span>  
  
 `value`  
 <span data-ttu-id="2be04-108">オブジェクトが拡張可能であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2be04-108">Whether the object is extensible or not.</span></span>  
  
## <span data-ttu-id="2be04-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2be04-109">Return Value</span></span>  
 <span data-ttu-id="2be04-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="2be04-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2be04-111">注釈</span><span class="sxs-lookup"><span data-stu-id="2be04-111">Remarks</span></span>  
 <span data-ttu-id="2be04-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2be04-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2be04-113">要件</span><span class="sxs-lookup"><span data-stu-id="2be04-113">Requirements</span></span>  
 <span data-ttu-id="2be04-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2be04-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2be04-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2be04-115">See Also</span></span>  
 [<span data-ttu-id="2be04-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2be04-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)