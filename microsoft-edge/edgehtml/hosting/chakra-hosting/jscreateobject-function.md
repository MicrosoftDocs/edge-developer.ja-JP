---
description: 新しいオブジェクトを作成します。
title: JsCreateObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateObject
helpviewer_keywords:
- JsCreateObject function
ms.assetid: 6c1d01a4-9254-443e-b974-6f0b0c861ca2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d5effe7ade1679392fcad7f2bb5cea880712ef7f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234667"
---
# <span data-ttu-id="db60c-103">JsCreateObject 関数</span><span class="sxs-lookup"><span data-stu-id="db60c-103">JsCreateObject Function</span></span>

<span data-ttu-id="db60c-104">新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db60c-104">Creates a new object.</span></span>
  
## <span data-ttu-id="db60c-105">構文</span><span class="sxs-lookup"><span data-stu-id="db60c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateObject(  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="db60c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db60c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="db60c-107">新しいオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="db60c-107">The new object.</span></span>  
  
## <span data-ttu-id="db60c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="db60c-108">Return Value</span></span>  
 <span data-ttu-id="db60c-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="db60c-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="db60c-110">注釈</span><span class="sxs-lookup"><span data-stu-id="db60c-110">Remarks</span></span>  
 <span data-ttu-id="db60c-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="db60c-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="db60c-112">要件</span><span class="sxs-lookup"><span data-stu-id="db60c-112">Requirements</span></span>  
 <span data-ttu-id="db60c-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="db60c-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="db60c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="db60c-114">See Also</span></span>  
 [<span data-ttu-id="db60c-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="db60c-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
