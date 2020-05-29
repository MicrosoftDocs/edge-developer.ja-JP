---
description: スクリプトを実行するためのスクリプトコンテキストを作成します。
title: JsCreateContext 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 06bd4c4780a8c7610ebc95cfc0da058306ce5b78
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569376"
---
# <span data-ttu-id="b8312-103">JsCreateContext 関数</span><span class="sxs-lookup"><span data-stu-id="b8312-103">JsCreateContext Function</span></span>
<span data-ttu-id="b8312-104">スクリプトを実行するためのスクリプトコンテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8312-104">Creates a script context for running scripts.</span></span>  
  
## <span data-ttu-id="b8312-105">構文</span><span class="sxs-lookup"><span data-stu-id="b8312-105">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="b8312-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8312-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="b8312-107">スクリプトコンテキストが作成されているランタイム。</span><span class="sxs-lookup"><span data-stu-id="b8312-107">The runtime the script context is being created in.</span></span>  
  
 `debugApplication`  
 <span data-ttu-id="b8312-108">デバッグに使用するデバッグアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b8312-108">The debug application to use for debugging.</span></span> <span data-ttu-id="b8312-109">このパラメーターは null でもかまいません。この場合、コンテキストに対してデバッグが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="b8312-109">This parameter can be null, in which case debugging is not enabled for the context.</span></span>  
  
 `newContext`  
 <span data-ttu-id="b8312-110">作成されたスクリプトコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="b8312-110">The created script context.</span></span>  
  
## <span data-ttu-id="b8312-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b8312-111">Return Value</span></span>  
 <span data-ttu-id="b8312-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="b8312-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b8312-113">注釈</span><span class="sxs-lookup"><span data-stu-id="b8312-113">Remarks</span></span>  
 <span data-ttu-id="b8312-114">各スクリプトコンテキストには、他のすべてのスクリプトコンテキストから分離された独自のグローバルオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="b8312-114">Each script context has its own global object that is isolated from all other script contexts.</span></span>  
  
 <span data-ttu-id="b8312-115">この `debugApplication` パラメーターは Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b8312-115">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="b8312-116">Microsoft Edge モードでのこの API の使用について詳しくは、「 [Microsoft edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8312-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="b8312-117">要件</span><span class="sxs-lookup"><span data-stu-id="b8312-117">Requirements</span></span>  
 <span data-ttu-id="b8312-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="b8312-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b8312-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8312-119">See Also</span></span>  
 [<span data-ttu-id="b8312-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b8312-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)