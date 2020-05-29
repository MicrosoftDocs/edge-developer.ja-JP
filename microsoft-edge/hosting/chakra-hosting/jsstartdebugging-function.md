---
description: 現在のコンテキストでデバッグを開始します。
title: JsStartDebugging 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 2c94a6f36ad72bfb9354c85d98ae0b5b4e9c77fb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570273"
---
# <span data-ttu-id="d529a-103">JsStartDebugging 関数</span><span class="sxs-lookup"><span data-stu-id="d529a-103">JsStartDebugging Function</span></span>
<span data-ttu-id="d529a-104">現在のコンテキストでデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="d529a-104">Starts debugging in the current context.</span></span>  
  
## <span data-ttu-id="d529a-105">構文</span><span class="sxs-lookup"><span data-stu-id="d529a-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### <span data-ttu-id="d529a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d529a-106">Parameters</span></span>  
 `debugApplication`  
 <span data-ttu-id="d529a-107">デバッグに使用するデバッグアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d529a-107">The debug application to use for debugging.</span></span>  
  
## <span data-ttu-id="d529a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d529a-108">Return Value</span></span>  
 <span data-ttu-id="d529a-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="d529a-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d529a-110">注釈</span><span class="sxs-lookup"><span data-stu-id="d529a-110">Remarks</span></span>  
 <span data-ttu-id="d529a-111">`CoInitializeEx` `COINIT_MULTITHREADED` `COINIT_APARTMENTTHREADED` この API を使用するには、ホストが、または少なくとも1回呼び出されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d529a-111">The host should make sure that `CoInitializeEx` is called with `COINIT_MULTITHREADED` or `COINIT_APARTMENTTHREADED` at least once before using this API</span></span>  
  
 <span data-ttu-id="d529a-112">この `debugApplication` パラメーターは Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d529a-112">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="d529a-113">Microsoft Edge モードでのこの API の使用について詳しくは、「 [Microsoft edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d529a-113">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="d529a-114">要件</span><span class="sxs-lookup"><span data-stu-id="d529a-114">Requirements</span></span>  
 <span data-ttu-id="d529a-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="d529a-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d529a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d529a-116">See Also</span></span>  
 [<span data-ttu-id="d529a-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d529a-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)