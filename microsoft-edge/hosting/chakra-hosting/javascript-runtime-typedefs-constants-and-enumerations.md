---
description: JavaScript Runtime (JsRT) typedef、定数、および列挙は、Windows で実行されているデスクトップおよびサーバー側アプリケーションへのスクリプト機能の追加をサポートしています。
title: JavaScript ランタイムの Typedefs、定数および列挙
ms.date: 06/08/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 1aa107ed-e144-4947-b5bb-90284a537174
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 20c52c3a958f6ba14fbfbdcdad794747a9c34949
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752263"
---
# <span data-ttu-id="e12a2-103">JavaScript ランタイムの Typedefs、定数および列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-103">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="e12a2-104">JavaScript Runtime (JsRT) typedef、定数、および列挙は、Windows で実行されているデスクトップおよびサーバー側アプリケーションへのスクリプト機能の追加をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e12a2-104">JavaScript Runtime (JsRT) typedefs, constants, and enumerations support adding scripting capabilities to desktop and server-side applications running on Windows.</span></span>  

## <span data-ttu-id="e12a2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e12a2-105">In this section</span></span>  

<span data-ttu-id="e12a2-106">次のグローバル typedef は、JsRT のホストをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e12a2-106">The following global typedefs support JsRT hosting:</span></span>  

*   [<span data-ttu-id="e12a2-107">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-107">JsBackgroundWorkItemCallback Typedef</span></span>](./jsbackgroundworkitemcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-108">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-108">JsBeforeCollectCallback Typedef</span></span>](./jsbeforecollectcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-109">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-109">JsContextRef Typedef</span></span>](./jscontextref-typedef.md)  
*   [<span data-ttu-id="e12a2-110">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-110">JsFinalizeCallback Typedef</span></span>](./jsfinalizecallback-typedef.md)  
*   [<span data-ttu-id="e12a2-111">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-111">JsMemoryAllocationCallback Typedef</span></span>](./jsmemoryallocationcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-112">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-112">JsNativeFunction Typedef</span></span>](./jsnativefunction-typedef.md)  
*   [<span data-ttu-id="e12a2-113">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-113">JsObjectBeforeCollectCallback Typedef</span></span>](./jsobjectbeforecollectcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-114">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-114">JsProjectionCallback Typedef</span></span>](./jsprojectioncallback-typedef.md)  
*   [<span data-ttu-id="e12a2-115">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-115">JsProjectionCallbackContext Typedef</span></span>](./jsprojectioncallbackcontext-typedef.md)  
*   [<span data-ttu-id="e12a2-116">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-116">JsProjectionEnqueueCallback Typedef</span></span>](./jsprojectionenqueuecallback-typedef.md)  
*   [<span data-ttu-id="e12a2-117">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-117">JsPromiseContinuationCallback Typedef</span></span>](./jspromisecontinuationcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-118">JsPropertyIdRef Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-118">JsPropertyIdRef Typedef</span></span>](./jspropertyidref-typedef.md)  
*   [<span data-ttu-id="e12a2-119">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-119">JsRef Typedef</span></span>](./jsref-typedef.md)  
*   [<span data-ttu-id="e12a2-120">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-120">JsRuntimeHandle Typedef</span></span>](./jsruntimehandle-typedef.md)  
*   [<span data-ttu-id="e12a2-121">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-121">JsSerializedScriptLoadSourceCallback Typedef</span></span>](./jsserializedscriptloadsourcecallback-typedef.md)  
*   [<span data-ttu-id="e12a2-122">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-122">JsSerializedScriptUnloadCallback typedef</span></span>](./jsserializedscriptunloadcallback-typedef.md)  
*   [<span data-ttu-id="e12a2-123">JsSourceContext Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-123">JsSourceContext Typedef</span></span>](./jssourcecontext-typedef.md)  
*   [<span data-ttu-id="e12a2-124">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-124">JsThreadServiceCallback Typedef</span></span>](./jsthreadservicecallback-typedef.md)  
*   [<span data-ttu-id="e12a2-125">JsValueRef Typedef</span><span class="sxs-lookup"><span data-stu-id="e12a2-125">JsValueRef Typedef</span></span>](./jsvalueref-typedef.md)  

<span data-ttu-id="e12a2-126">次の定数は、JsRT のホストをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e12a2-126">The following constants support JsRT hosting:</span></span>  

*   [<span data-ttu-id="e12a2-127">JS_INVALID_PROPERTYID 定数</span><span class="sxs-lookup"><span data-stu-id="e12a2-127">JS_INVALID_PROPERTYID Constant</span></span>](./js-invalid-propertyid-constant.md)  
*   [<span data-ttu-id="e12a2-128">JS_INVALID_REFERENCE 定数</span><span class="sxs-lookup"><span data-stu-id="e12a2-128">JS_INVALID_REFERENCE Constant</span></span>](./js-invalid-reference-constant.md)  
*   [<span data-ttu-id="e12a2-129">JS_INVALID_RUNTIME_HANDLE 定数</span><span class="sxs-lookup"><span data-stu-id="e12a2-129">JS_INVALID_RUNTIME_HANDLE Constant</span></span>](./js-invalid-runtime-handle-constant.md)  
*   [<span data-ttu-id="e12a2-130">JS_SOURCE_CONTEXT_NONE 定数</span><span class="sxs-lookup"><span data-stu-id="e12a2-130">JS_SOURCE_CONTEXT_NONE Constant</span></span>](./js-source-context-none-constant.md)  

<span data-ttu-id="e12a2-131">JsRT のホスティングは、次の列挙型でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e12a2-131">The following enumerations support JsRT hosting:</span></span>  

*   [<span data-ttu-id="e12a2-132">JsErrorCode 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-132">JsErrorCode Enumeration</span></span>](./jserrorcode-enumeration.md)  
*   [<span data-ttu-id="e12a2-133">JsMemoryEventType 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-133">JsMemoryEventType Enumeration</span></span>](./jsmemoryeventtype-enumeration.md)  
*   [<span data-ttu-id="e12a2-134">JsPropertyIdType 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-134">JsPropertyIdType Enumeration</span></span>](./jspropertyidtype-enumeration.md)  
*   [<span data-ttu-id="e12a2-135">JsRuntimeAttributes 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-135">JsRuntimeAttributes Enumeration</span></span>](./jsruntimeattributes-enumeration.md)  
*   [<span data-ttu-id="e12a2-136">JsRuntimeVersion 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-136">JsRuntimeVersion Enumeration</span></span>](./jsruntimeversion-enumeration.md)  
*   [<span data-ttu-id="e12a2-137">JsTypedArrayType 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-137">JsTypedArrayType Enumeration</span></span>](./jstypedarraytype-enumeration.md)  
*   [<span data-ttu-id="e12a2-138">JsValueType 列挙</span><span class="sxs-lookup"><span data-stu-id="e12a2-138">JsValueType Enumeration</span></span>](./jsvaluetype-enumeration.md)  

## <span data-ttu-id="e12a2-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12a2-139">See also</span></span>  

*   [<span data-ttu-id="e12a2-140">JavaScript ランタイムのホスティング</span><span class="sxs-lookup"><span data-stu-id="e12a2-140">Hosting the JavaScript Runtime</span></span>](./hosting-the-javascript-runtime.md)  
*   [<span data-ttu-id="e12a2-141">JavaScript ランタイムのホスティング</span><span class="sxs-lookup"><span data-stu-id="e12a2-141">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)  
