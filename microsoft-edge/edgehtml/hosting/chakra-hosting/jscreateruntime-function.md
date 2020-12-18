---
description: 新しいランタイムを作成します。
title: JsCreateRuntime 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3b893bd75725d6d9da56417ba83adfce18d77bac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234747"
---
# <span data-ttu-id="07758-103">JsCreateRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="07758-103">JsCreateRuntime Function</span></span>

<span data-ttu-id="07758-104">新しいランタイムを作成します。</span><span class="sxs-lookup"><span data-stu-id="07758-104">Creates a new runtime.</span></span>
  
## <span data-ttu-id="07758-105">構文</span><span class="sxs-lookup"><span data-stu-id="07758-105">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="07758-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07758-106">Parameters</span></span>  
 `attributes`  
 <span data-ttu-id="07758-107">作成するランタイムの属性。</span><span class="sxs-lookup"><span data-stu-id="07758-107">The attributes of the runtime to be created.</span></span>  
  
 `version`  
 <span data-ttu-id="07758-108">作成するランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="07758-108">The version of the runtime to be created.</span></span>  
  
 `threadService`  
 <span data-ttu-id="07758-109">ランタイムのスレッド サービス。</span><span class="sxs-lookup"><span data-stu-id="07758-109">The thread service for the runtime.</span></span> <span data-ttu-id="07758-110">null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="07758-110">Can be null.</span></span>  
  
 `runtime`  
 <span data-ttu-id="07758-111">作成されたランタイム。</span><span class="sxs-lookup"><span data-stu-id="07758-111">The runtime created.</span></span>  
  
## <span data-ttu-id="07758-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="07758-112">Return Value</span></span>  
 <span data-ttu-id="07758-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="07758-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="07758-114">注釈</span><span class="sxs-lookup"><span data-stu-id="07758-114">Remarks</span></span>  
 <span data-ttu-id="07758-115">この `version` パラメーターは、Microsoft Edge モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07758-115">The `version` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="07758-116">この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07758-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="07758-117">要件</span><span class="sxs-lookup"><span data-stu-id="07758-117">Requirements</span></span>  
 <span data-ttu-id="07758-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="07758-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="07758-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="07758-119">See Also</span></span>  
 [<span data-ttu-id="07758-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="07758-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
