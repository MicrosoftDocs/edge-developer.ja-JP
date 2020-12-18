---
description: オブジェクトのプロトタイプを設定します。
title: JsSetPrototype 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 88e1e421-4ae5-4e3b-b377-19256cc80e9f
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 860a7b8d85e043c87d554e09de50d0cb642b273a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234510"
---
# <span data-ttu-id="40f33-103">JsSetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="40f33-103">JsSetPrototype Function</span></span>

<span data-ttu-id="40f33-104">オブジェクトのプロトタイプを設定します。</span><span class="sxs-lookup"><span data-stu-id="40f33-104">Sets the prototype of an object.</span></span>  
  
## <span data-ttu-id="40f33-105">構文</span><span class="sxs-lookup"><span data-stu-id="40f33-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPrototype(  
   _In_ JsValueRef object,  
   _In_ JsValueRef prototypeObject  
);  
```  
  
#### <span data-ttu-id="40f33-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40f33-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="40f33-107">プロトタイプを変更するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="40f33-107">The object whose prototype is to be changed.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="40f33-108">オブジェクトの新しいプロトタイプ。</span><span class="sxs-lookup"><span data-stu-id="40f33-108">The object's new prototype.</span></span>  
  
## <span data-ttu-id="40f33-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="40f33-109">Return Value</span></span>  
 <span data-ttu-id="40f33-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="40f33-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="40f33-111">注釈</span><span class="sxs-lookup"><span data-stu-id="40f33-111">Remarks</span></span>  
 <span data-ttu-id="40f33-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="40f33-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="40f33-113">要件</span><span class="sxs-lookup"><span data-stu-id="40f33-113">Requirements</span></span>  
 <span data-ttu-id="40f33-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="40f33-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="40f33-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="40f33-115">See Also</span></span>  
 [<span data-ttu-id="40f33-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="40f33-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
