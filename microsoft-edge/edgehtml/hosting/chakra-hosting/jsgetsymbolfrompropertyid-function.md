---
description: プロパティ ID に関連付けられているシンボルを取得します。
title: JsGetSymbolFromPropertyId 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0e822cb4-ba9e-44df-bf3a-fae97c354daa
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472253aea228ca0374c42d99710a7a7ab528184c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235095"
---
# <span data-ttu-id="f5403-103">JsGetSymbolFromPropertyId 関数</span><span class="sxs-lookup"><span data-stu-id="f5403-103">JsGetSymbolFromPropertyId Function</span></span>

<span data-ttu-id="f5403-104">プロパティ ID に関連付けられているシンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5403-104">Gets the symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="f5403-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5403-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetSymbolFromPropertyId(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *symbol  
);  
```  
  
#### <span data-ttu-id="f5403-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5403-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="f5403-107">シンボルを取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="f5403-107">The property ID to get the symbol of.</span></span>  
  
 `symbol`  
 <span data-ttu-id="f5403-108">プロパティ ID に関連付けられている記号。</span><span class="sxs-lookup"><span data-stu-id="f5403-108">The symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="f5403-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5403-109">Return Value</span></span>  
 <span data-ttu-id="f5403-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f5403-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f5403-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f5403-111">Remarks</span></span>  
 <span data-ttu-id="f5403-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f5403-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="f5403-113">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5403-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="f5403-114">要件</span><span class="sxs-lookup"><span data-stu-id="f5403-114">Requirements</span></span>  
 <span data-ttu-id="f5403-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f5403-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f5403-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5403-116">See Also</span></span>  
 [<span data-ttu-id="f5403-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f5403-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
