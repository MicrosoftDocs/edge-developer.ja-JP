---
description: 新しいランタイムを作成します。
title: JsCreateRuntime 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d25c1b46354be1fda0ce906dc68c3643989fe2c6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569356"
---
# <span data-ttu-id="a239a-103">JsCreateRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="a239a-103">JsCreateRuntime Function</span></span>
<span data-ttu-id="a239a-104">新しいランタイムを作成します。</span><span class="sxs-lookup"><span data-stu-id="a239a-104">Creates a new runtime.</span></span>
  
## <span data-ttu-id="a239a-105">構文</span><span class="sxs-lookup"><span data-stu-id="a239a-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_ JsRuntimeVersion version,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="a239a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a239a-106">Parameters</span></span>  
 `attributes`  
 <span data-ttu-id="a239a-107">作成するランタイムの属性。</span><span class="sxs-lookup"><span data-stu-id="a239a-107">The attributes of the runtime to be created.</span></span>  
  
 `version`  
 <span data-ttu-id="a239a-108">作成するランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="a239a-108">The version of the runtime to be created.</span></span>  
  
 `threadService`  
 <span data-ttu-id="a239a-109">ランタイムのスレッドサービス。</span><span class="sxs-lookup"><span data-stu-id="a239a-109">The thread service for the runtime.</span></span> <span data-ttu-id="a239a-110">Null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a239a-110">Can be null.</span></span>  
  
 `runtime`  
 <span data-ttu-id="a239a-111">ランタイムが作成されました。</span><span class="sxs-lookup"><span data-stu-id="a239a-111">The runtime created.</span></span>  
  
## <span data-ttu-id="a239a-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="a239a-112">Return Value</span></span>  
 <span data-ttu-id="a239a-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="a239a-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a239a-114">注釈</span><span class="sxs-lookup"><span data-stu-id="a239a-114">Remarks</span></span>  
 <span data-ttu-id="a239a-115">この `version` パラメーターは Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a239a-115">The `version` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="a239a-116">Microsoft Edge モードでのこの API の使用について詳しくは、「 [Microsoft edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a239a-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="a239a-117">要件</span><span class="sxs-lookup"><span data-stu-id="a239a-117">Requirements</span></span>  
 <span data-ttu-id="a239a-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="a239a-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a239a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a239a-119">See Also</span></span>  
 [<span data-ttu-id="a239a-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a239a-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)