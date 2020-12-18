---
description: Javascript 配列オブジェクトを作成します。
title: JsCreateArray 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateArray
helpviewer_keywords:
- JsCreateArray function
ms.assetid: a119949a-e427-4349-9d00-5ec20fb9319c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 34ce07055fa3d4d24188d7edbcedc3f08973e233
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234529"
---
# <span data-ttu-id="df843-103">JsCreateArray 関数</span><span class="sxs-lookup"><span data-stu-id="df843-103">JsCreateArray Function</span></span>

<span data-ttu-id="df843-104">Javascript 配列オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="df843-104">Creates a Javascript array object.</span></span>  
  
## <span data-ttu-id="df843-105">構文</span><span class="sxs-lookup"><span data-stu-id="df843-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArray(  
   _In_ unsigned int length,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="df843-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df843-106">Parameters</span></span>  
 `length`  
 <span data-ttu-id="df843-107">配列の初期の長さ。</span><span class="sxs-lookup"><span data-stu-id="df843-107">The initial length of the array.</span></span>  
  
 `result`  
 <span data-ttu-id="df843-108">新しい配列オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="df843-108">The new array object.</span></span>  
  
## <span data-ttu-id="df843-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="df843-109">Return Value</span></span>  
 <span data-ttu-id="df843-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="df843-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="df843-111">注釈</span><span class="sxs-lookup"><span data-stu-id="df843-111">Remarks</span></span>  
 <span data-ttu-id="df843-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="df843-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="df843-113">要件</span><span class="sxs-lookup"><span data-stu-id="df843-113">Requirements</span></span>  
 <span data-ttu-id="df843-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="df843-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="df843-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="df843-115">See Also</span></span>  
 [<span data-ttu-id="df843-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="df843-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
