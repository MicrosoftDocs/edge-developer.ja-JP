---
description: JavaScript 演算子テスト `instanceof` を実行します。
title: JsInstanceOf 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d8aec1d4512fe937d1fd48aa6f3e88294bf9850c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234908"
---
# <span data-ttu-id="124a9-103">JsInstanceOf 関数</span><span class="sxs-lookup"><span data-stu-id="124a9-103">JsInstanceOf Function</span></span>

<span data-ttu-id="124a9-104">JavaScript 演算子テスト `instanceof` を実行します。</span><span class="sxs-lookup"><span data-stu-id="124a9-104">Performs JavaScript `instanceof` operator test.</span></span>  
  
## <span data-ttu-id="124a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="124a9-105">Syntax</span></span>  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### <span data-ttu-id="124a9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="124a9-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="124a9-107">テストするオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="124a9-107">The object to test.</span></span>  
  
 `constructor`  
 <span data-ttu-id="124a9-108">テストするコンストラクター関数。</span><span class="sxs-lookup"><span data-stu-id="124a9-108">The constructor function to test against.</span></span>  
  
 `result`  
 <span data-ttu-id="124a9-109">"コンストラクターの object instance" が true かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="124a9-109">Whether the "object instanceof constructor" is true.</span></span>  
  
## <span data-ttu-id="124a9-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="124a9-110">Return Value</span></span>  
 <span data-ttu-id="124a9-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="124a9-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="124a9-112">注釈</span><span class="sxs-lookup"><span data-stu-id="124a9-112">Remarks</span></span>  
 <span data-ttu-id="124a9-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="124a9-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="124a9-114">要件</span><span class="sxs-lookup"><span data-stu-id="124a9-114">Requirements</span></span>  
 <span data-ttu-id="124a9-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="124a9-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="124a9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="124a9-116">See Also</span></span>  
 [<span data-ttu-id="124a9-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="124a9-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
