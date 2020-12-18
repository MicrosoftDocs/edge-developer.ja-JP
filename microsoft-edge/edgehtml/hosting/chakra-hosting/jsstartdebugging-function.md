---
description: 現在のコンテキストでデバッグを開始します。
title: JsStartDebugging 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9685779911db8e3045986682b66d13e38c70fe8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235021"
---
# <span data-ttu-id="14c2d-103">JsStartDebugging 関数</span><span class="sxs-lookup"><span data-stu-id="14c2d-103">JsStartDebugging Function</span></span>

<span data-ttu-id="14c2d-104">現在のコンテキストでデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="14c2d-104">Starts debugging in the current context.</span></span>  
  
## <span data-ttu-id="14c2d-105">構文</span><span class="sxs-lookup"><span data-stu-id="14c2d-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### <span data-ttu-id="14c2d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14c2d-106">Parameters</span></span>  
 `debugApplication`  
 <span data-ttu-id="14c2d-107">デバッグに使用するデバッグ アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="14c2d-107">The debug application to use for debugging.</span></span>  
  
## <span data-ttu-id="14c2d-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="14c2d-108">Return Value</span></span>  
 <span data-ttu-id="14c2d-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="14c2d-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="14c2d-110">注釈</span><span class="sxs-lookup"><span data-stu-id="14c2d-110">Remarks</span></span>  
 <span data-ttu-id="14c2d-111">ホストは、この API を使用する前に、この API で呼び出されるのか、少なくとも `CoInitializeEx` `COINIT_MULTITHREADED` 1 回は呼 `COINIT_APARTMENTTHREADED` び出される必要があります。</span><span class="sxs-lookup"><span data-stu-id="14c2d-111">The host should make sure that `CoInitializeEx` is called with `COINIT_MULTITHREADED` or `COINIT_APARTMENTTHREADED` at least once before using this API</span></span>  
  
 <span data-ttu-id="14c2d-112">この `debugApplication` パラメーターは、Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="14c2d-112">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="14c2d-113">この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14c2d-113">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="14c2d-114">要件</span><span class="sxs-lookup"><span data-stu-id="14c2d-114">Requirements</span></span>  
 <span data-ttu-id="14c2d-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="14c2d-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="14c2d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="14c2d-116">See Also</span></span>  
 [<span data-ttu-id="14c2d-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="14c2d-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
