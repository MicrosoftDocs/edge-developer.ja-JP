---
description: スクリプトを実行するためのスクリプト コンテキストを作成します。
title: JsCreateContext 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5d6c8149b8a5e5fee7cbc8dac821713b1d9649ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234528"
---
# <span data-ttu-id="96e8f-103">JsCreateContext 関数</span><span class="sxs-lookup"><span data-stu-id="96e8f-103">JsCreateContext Function</span></span>

<span data-ttu-id="96e8f-104">スクリプトを実行するためのスクリプト コンテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="96e8f-104">Creates a script context for running scripts.</span></span>  
  
## <span data-ttu-id="96e8f-105">構文</span><span class="sxs-lookup"><span data-stu-id="96e8f-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### <span data-ttu-id="96e8f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96e8f-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="96e8f-107">スクリプト コンテキストの作成中のランタイム。</span><span class="sxs-lookup"><span data-stu-id="96e8f-107">The runtime the script context is being created in.</span></span>  
  
 `debugApplication`  
 <span data-ttu-id="96e8f-108">デバッグに使用するデバッグ アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="96e8f-108">The debug application to use for debugging.</span></span> <span data-ttu-id="96e8f-109">このパラメーターは null に設定できます。この場合、コンテキストに対してデバッグが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="96e8f-109">This parameter can be null, in which case debugging is not enabled for the context.</span></span>  
  
 `newContext`  
 <span data-ttu-id="96e8f-110">作成されたスクリプト コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="96e8f-110">The created script context.</span></span>  
  
## <span data-ttu-id="96e8f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="96e8f-111">Return Value</span></span>  
 <span data-ttu-id="96e8f-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="96e8f-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="96e8f-113">注釈</span><span class="sxs-lookup"><span data-stu-id="96e8f-113">Remarks</span></span>  
 <span data-ttu-id="96e8f-114">各スクリプト コンテキストには、他のすべてのスクリプト コンテキストから分離された独自のグローバル オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="96e8f-114">Each script context has its own global object that is isolated from all other script contexts.</span></span>  
  
 <span data-ttu-id="96e8f-115">この `debugApplication` パラメーターは、Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96e8f-115">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="96e8f-116">この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96e8f-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="96e8f-117">要件</span><span class="sxs-lookup"><span data-stu-id="96e8f-117">Requirements</span></span>  
 <span data-ttu-id="96e8f-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="96e8f-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="96e8f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="96e8f-119">See Also</span></span>  
 [<span data-ttu-id="96e8f-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="96e8f-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
