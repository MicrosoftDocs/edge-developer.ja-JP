---
description: JavaScript Runtime (JsRT) Api を使用すると、Windows で実行されているデスクトップおよびサーバー側アプリケーションにスクリプト機能を追加できます。
title: リファレンス (JavaScript ランタイム) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/15/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0bfe50da-fd79-4e00-9458-bc667769b415
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d1215d84daa31f2338b8c7e237625d0129026bea
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569256"
---
# <span data-ttu-id="ea2e2-103">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ea2e2-103">Reference (JavaScript Runtime)</span></span>
<span data-ttu-id="ea2e2-104">JavaScript Runtime (JsRT) Api を使用すると、Windows で実行されているデスクトップおよびサーバー側アプリケーションにスクリプト機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="ea2e2-104">JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.</span></span>  
  
 <span data-ttu-id="ea2e2-105">アプリケーションに[ChakraCore](https://github.com/Microsoft/ChakraCore)を埋め込む場合は、代わりに[CHAKRACORE Wiki](https://aka.ms/corejsrtref) for JSRT references を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea2e2-105">If you intend to embed [ChakraCore](https://github.com/Microsoft/ChakraCore) in your application, please refer to [ChakraCore Wiki](https://aka.ms/corejsrtref) for JSRT references instead.</span></span>  
  
## <span data-ttu-id="ea2e2-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ea2e2-106">In This Section</span></span>  
 <span data-ttu-id="ea2e2-107">JsRT のホスティングをサポートする typedef、定数、および列挙型について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea2e2-107">Typedefs, constants, and enumerations that support JsRT hosting are described here:</span></span>  
  
-   [<span data-ttu-id="ea2e2-108">JavaScript ランタイム Typedef、定数、および列挙</span><span class="sxs-lookup"><span data-stu-id="ea2e2-108">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>](../chakra-hosting/javascript-runtime-typedefs-constants-and-enumerations.md)  
  
 <span data-ttu-id="ea2e2-109">JsRT のホストを有効にするには、次の関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea2e2-109">The following functions enable JsRT hosting:</span></span>  
  
-   [<span data-ttu-id="ea2e2-110">JsAddRef 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-110">JsAddRef Function</span></span>](../chakra-hosting/jsaddref-function.md)  
  
-   [<span data-ttu-id="ea2e2-111">JsBooleanToBool 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-111">JsBooleanToBool Function</span></span>](../chakra-hosting/jsbooleantobool-function.md)  
  
-   [<span data-ttu-id="ea2e2-112">JsBoolToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-112">JsBoolToBoolean Function</span></span>](../chakra-hosting/jsbooltoboolean-function.md)  
  
-   [<span data-ttu-id="ea2e2-113">JsCallFunction 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-113">JsCallFunction Function</span></span>](../chakra-hosting/jscallfunction-function.md)  
  
-   [<span data-ttu-id="ea2e2-114">JsCollectGarbage 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-114">JsCollectGarbage Function</span></span>](../chakra-hosting/jscollectgarbage-function.md)  
  
-   [<span data-ttu-id="ea2e2-115">JsConstructObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-115">JsConstructObject Function</span></span>](../chakra-hosting/jsconstructobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-116">JsConvertValueToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-116">JsConvertValueToBoolean Function</span></span>](../chakra-hosting/jsconvertvaluetoboolean-function.md)  
  
-   [<span data-ttu-id="ea2e2-117">JsConvertValueToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-117">JsConvertValueToNumber Function</span></span>](../chakra-hosting/jsconvertvaluetonumber-function.md)  
  
-   [<span data-ttu-id="ea2e2-118">JsConvertValueToObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-118">JsConvertValueToObject Function</span></span>](../chakra-hosting/jsconvertvaluetoobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-119">JsConvertValueToString 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-119">JsConvertValueToString Function</span></span>](../chakra-hosting/jsconvertvaluetostring-function.md)  
  
-   [<span data-ttu-id="ea2e2-120">JsCreateArray 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-120">JsCreateArray Function</span></span>](../chakra-hosting/jscreatearray-function.md)  
  
-   [<span data-ttu-id="ea2e2-121">JsCreateArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-121">JsCreateArrayBuffer Function</span></span>](../chakra-hosting/jscreatearraybuffer-function.md)  
  
-   [<span data-ttu-id="ea2e2-122">JsCreateContext 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-122">JsCreateContext Function</span></span>](../chakra-hosting/jscreatecontext-function.md)  
  
-   [<span data-ttu-id="ea2e2-123">JsCreateDataView 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-123">JsCreateDataView Function</span></span>](../chakra-hosting/jscreatedataview-function.md)  
  
-   [<span data-ttu-id="ea2e2-124">JsCreateError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-124">JsCreateError Function</span></span>](../chakra-hosting/jscreateerror-function.md)  
  
-   [<span data-ttu-id="ea2e2-125">JsCreateExternalArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-125">JsCreateExternalArrayBuffer Function</span></span>](../chakra-hosting/jscreateexternalarraybuffer-function.md)  
  
-   [<span data-ttu-id="ea2e2-126">JsCreateExternalObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-126">JsCreateExternalObject Function</span></span>](../chakra-hosting/jscreateexternalobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-127">JsCreateFunction 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-127">JsCreateFunction Function</span></span>](../chakra-hosting/jscreatefunction-function.md)  
  
-   [<span data-ttu-id="ea2e2-128">JsCreateNamedFunction 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-128">JsCreateNamedFunction Function</span></span>](../chakra-hosting/jscreatenamedfunction-function.md)  
  
-   [<span data-ttu-id="ea2e2-129">JsCreateObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-129">JsCreateObject Function</span></span>](../chakra-hosting/jscreateobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-130">JsCreateRangeError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-130">JsCreateRangeError Function</span></span>](../chakra-hosting/jscreaterangeerror-function.md)  
  
-   [<span data-ttu-id="ea2e2-131">JsCreateReferenceError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-131">JsCreateReferenceError Function</span></span>](../chakra-hosting/jscreatereferenceerror-function.md)  
  
-   [<span data-ttu-id="ea2e2-132">JsCreateRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-132">JsCreateRuntime Function</span></span>](../chakra-hosting/jscreateruntime-function.md)  
  
-   [<span data-ttu-id="ea2e2-133">JsCreateSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-133">JsCreateSymbol Function</span></span>](../chakra-hosting/jscreatesymbol-function.md)  
  
-   [<span data-ttu-id="ea2e2-134">JsCreateSyntaxError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-134">JsCreateSyntaxError Function</span></span>](../chakra-hosting/jscreatesyntaxerror-function.md)  
  
-   [<span data-ttu-id="ea2e2-135">JsCreateTypeError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-135">JsCreateTypeError Function</span></span>](../chakra-hosting/jscreatetypeerror-function.md)  
  
-   [<span data-ttu-id="ea2e2-136">JsCreateTypedArray 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-136">JsCreateTypedArray Function</span></span>](../chakra-hosting/jscreatetypedarray-function.md)  
  
-   [<span data-ttu-id="ea2e2-137">JsCreateURIError 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-137">JsCreateURIError Function</span></span>](../chakra-hosting/jscreateurierror-function.md)  
  
-   [<span data-ttu-id="ea2e2-138">JsDefineProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-138">JsDefineProperty Function</span></span>](../chakra-hosting/jsdefineproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-139">JsDeleteIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-139">JsDeleteIndexedProperty Function</span></span>](../chakra-hosting/jsdeleteindexedproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-140">JsDeleteProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-140">JsDeleteProperty Function</span></span>](../chakra-hosting/jsdeleteproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-141">JsDisableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-141">JsDisableRuntimeExecution Function</span></span>](../chakra-hosting/jsdisableruntimeexecution-function.md)  
  
-   [<span data-ttu-id="ea2e2-142">JsDisposeRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-142">JsDisposeRuntime Function</span></span>](../chakra-hosting/jsdisposeruntime-function.md)  
  
-   [<span data-ttu-id="ea2e2-143">JsDoubleToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-143">JsDoubleToNumber Function</span></span>](../chakra-hosting/jsdoubletonumber-function.md)  
  
-   [<span data-ttu-id="ea2e2-144">JsEnableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-144">JsEnableRuntimeExecution Function</span></span>](../chakra-hosting/jsenableruntimeexecution-function.md)  
  
-   [<span data-ttu-id="ea2e2-145">JsEnumerateHeap 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-145">JsEnumerateHeap Function</span></span>](../chakra-hosting/jsenumerateheap-function.md)  
  
-   [<span data-ttu-id="ea2e2-146">JsEquals 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-146">JsEquals Function</span></span>](../chakra-hosting/jsequals-function.md)  
  
-   [<span data-ttu-id="ea2e2-147">JsGetAndClearException 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-147">JsGetAndClearException Function</span></span>](../chakra-hosting/jsgetandclearexception-function.md)  
  
-   [<span data-ttu-id="ea2e2-148">JsGetArrayBufferStorage 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-148">JsGetArrayBufferStorage Function</span></span>](../chakra-hosting/jsgetarraybufferstorage-function.md)  
  
-   [<span data-ttu-id="ea2e2-149">JsGetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-149">JsGetContextData Function</span></span>](../chakra-hosting/jsgetcontextdata-function.md)  
  
-   [<span data-ttu-id="ea2e2-150">JsGetContextOfObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-150">JsGetContextOfObject Function</span></span>](../chakra-hosting/jsgetcontextofobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-151">JsGetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-151">JsGetCurrentContext Function</span></span>](../chakra-hosting/jsgetcurrentcontext-function.md)  
  
-   [<span data-ttu-id="ea2e2-152">JsGetDataViewStorage 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-152">JsGetDataViewStorage Function</span></span>](../chakra-hosting/jsgetdataviewstorage-function.md)  
  
-   [<span data-ttu-id="ea2e2-153">JsGetExtensionAllowed 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-153">JsGetExtensionAllowed Function</span></span>](../chakra-hosting/jsgetextensionallowed-function.md)  
  
-   [<span data-ttu-id="ea2e2-154">JsGetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-154">JsGetExternalData Function</span></span>](../chakra-hosting/jsgetexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-155">JsGetFalseValue 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-155">JsGetFalseValue Function</span></span>](../chakra-hosting/jsgetfalsevalue-function.md)  
  
-   [<span data-ttu-id="ea2e2-156">JsGetGlobalObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-156">JsGetGlobalObject Function</span></span>](../chakra-hosting/jsgetglobalobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-157">JsGetIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-157">JsGetIndexedPropertiesExternalData Function</span></span>](../chakra-hosting/jsgetindexedpropertiesexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-158">JsGetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-158">JsGetIndexedProperty Function</span></span>](../chakra-hosting/jsgetindexedproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-159">JsGetNullValue 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-159">JsGetNullValue Function</span></span>](../chakra-hosting/jsgetnullvalue-function.md)  
  
-   [<span data-ttu-id="ea2e2-160">JsGetOwnPropertyDescriptor 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-160">JsGetOwnPropertyDescriptor Function</span></span>](../chakra-hosting/jsgetownpropertydescriptor-function.md)  
  
-   [<span data-ttu-id="ea2e2-161">JsGetOwnPropertyNames 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-161">JsGetOwnPropertyNames Function</span></span>](../chakra-hosting/jsgetownpropertynames-function.md)  
  
-   [<span data-ttu-id="ea2e2-162">JsGetOwnPropertySymbols 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-162">JsGetOwnPropertySymbols Function</span></span>](../chakra-hosting/jsgetownpropertysymbols-function.md)  
  
-   [<span data-ttu-id="ea2e2-163">JsGetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-163">JsGetProperty Function</span></span>](../chakra-hosting/jsgetproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-164">JsGetPropertyIdFromName 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-164">JsGetPropertyIdFromName Function</span></span>](../chakra-hosting/jsgetpropertyidfromname-function.md)  
  
-   [<span data-ttu-id="ea2e2-165">JsGetPropertyIdFromSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-165">JsGetPropertyIdFromSymbol Function</span></span>](../chakra-hosting/jsgetpropertyidfromsymbol-function.md)  
  
-   [<span data-ttu-id="ea2e2-166">JsGetPropertyIdType 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-166">JsGetPropertyIdType Function</span></span>](../chakra-hosting/jsgetpropertyidtype-function.md)  
  
-   [<span data-ttu-id="ea2e2-167">JsGetPropertyNameFromId 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-167">JsGetPropertyNameFromId Function</span></span>](../chakra-hosting/jsgetpropertynamefromid-function.md)  
  
-   [<span data-ttu-id="ea2e2-168">JsGetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-168">JsGetPrototype Function</span></span>](../chakra-hosting/jsgetprototype-function.md)  
  
-   [<span data-ttu-id="ea2e2-169">JsGetRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-169">JsGetRuntime Function</span></span>](../chakra-hosting/jsgetruntime-function.md)  
  
-   [<span data-ttu-id="ea2e2-170">JsGetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-170">JsGetRuntimeMemoryLimit Function</span></span>](../chakra-hosting/jsgetruntimememorylimit-function.md)  
  
-   [<span data-ttu-id="ea2e2-171">JsGetRuntimeMemoryUsage 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-171">JsGetRuntimeMemoryUsage Function</span></span>](../chakra-hosting/jsgetruntimememoryusage-function.md)  
  
-   [<span data-ttu-id="ea2e2-172">JsGetStringLength 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-172">JsGetStringLength Function</span></span>](../chakra-hosting/jsgetstringlength-function.md)  
  
-   [<span data-ttu-id="ea2e2-173">JsGetSymbolFromPropertyId 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-173">JsGetSymbolFromPropertyId Function</span></span>](../chakra-hosting/jsgetsymbolfrompropertyid-function.md)  
  
-   [<span data-ttu-id="ea2e2-174">JsGetTrueValue 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-174">JsGetTrueValue Function</span></span>](../chakra-hosting/jsgettruevalue-function.md)  
  
-   [<span data-ttu-id="ea2e2-175">JsGetTypedArrayInfo 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-175">JsGetTypedArrayInfo Function</span></span>](../chakra-hosting/jsgettypedarrayinfo-function.md)  
  
-   [<span data-ttu-id="ea2e2-176">JsGetTypedArrayStorage 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-176">JsGetTypedArrayStorage Function</span></span>](../chakra-hosting/jsgettypedarraystorage-function.md)  
  
-   [<span data-ttu-id="ea2e2-177">JsGetUndefinedValue 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-177">JsGetUndefinedValue Function</span></span>](../chakra-hosting/jsgetundefinedvalue-function.md)  
  
-   [<span data-ttu-id="ea2e2-178">JsGetValueType 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-178">JsGetValueType Function</span></span>](../chakra-hosting/jsgetvaluetype-function.md)  
  
-   [<span data-ttu-id="ea2e2-179">JsHasException 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-179">JsHasException Function</span></span>](../chakra-hosting/jshasexception-function.md)  
  
-   [<span data-ttu-id="ea2e2-180">JsHasExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-180">JsHasExternalData Function</span></span>](../chakra-hosting/jshasexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-181">JsHasIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-181">JsHasIndexedPropertiesExternalData Function</span></span>](../chakra-hosting/jshasindexedpropertiesexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-182">JsHasIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-182">JsHasIndexedProperty Function</span></span>](../chakra-hosting/jshasindexedproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-183">JsHasProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-183">JsHasProperty Function</span></span>](../chakra-hosting/jshasproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-184">JsIdle 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-184">JsIdle Function</span></span>](../chakra-hosting/jsidle-function.md)  
  
-   [<span data-ttu-id="ea2e2-185">JsInspectableToObject 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-185">JsInspectableToObject Function</span></span>](../chakra-hosting/jsinspectabletoobject-function.md)  
  
-   [<span data-ttu-id="ea2e2-186">JsInstanceOf 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-186">JsInstanceOf Function</span></span>](../chakra-hosting/jsinstanceof-function.md)  
  
-   [<span data-ttu-id="ea2e2-187">JsIntToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-187">JsIntToNumber Function</span></span>](../chakra-hosting/jsinttonumber-function.md)  
  
-   [<span data-ttu-id="ea2e2-188">JsIsEnumeratingHeap 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-188">JsIsEnumeratingHeap Function</span></span>](../chakra-hosting/jsisenumeratingheap-function.md)  
  
-   [<span data-ttu-id="ea2e2-189">JsIsRuntimeExecutionDisabled 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-189">JsIsRuntimeExecutionDisabled Function</span></span>](../chakra-hosting/jsisruntimeexecutiondisabled-function.md)  
  
-   [<span data-ttu-id="ea2e2-190">JsNumberToDouble 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-190">JsNumberToDouble Function</span></span>](../chakra-hosting/jsnumbertodouble-function.md)  
  
-   [<span data-ttu-id="ea2e2-191">JsNumberToInt 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-191">JsNumberToInt Function</span></span>](../chakra-hosting/jsnumbertoint-function.md)  
  
-   [<span data-ttu-id="ea2e2-192">JsObjectToInspectable 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-192">JsObjectToInspectable Function</span></span>](../chakra-hosting/jsobjecttoinspectable-function.md)  
  
-   [<span data-ttu-id="ea2e2-193">Jsparc Sescript 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-193">JsParseScript Function</span></span>](../chakra-hosting/jsparsescript-function.md)  
  
-   [<span data-ttu-id="ea2e2-194">JsParseSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-194">JsParseSerializedScript Function</span></span>](../chakra-hosting/jsparseserializedscript-function.md)  
  
-   [<span data-ttu-id="ea2e2-195">JsParseSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-195">JsParseSerializedScriptWithCallback Function</span></span>](../chakra-hosting/jsparseserializedscriptwithcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-196">JsPointerToString 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-196">JsPointerToString Function</span></span>](../chakra-hosting/jspointertostring-function.md)  
  
-   [<span data-ttu-id="ea2e2-197">JsPreventExtension 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-197">JsPreventExtension Function</span></span>](../chakra-hosting/jspreventextension-function.md)  
  
-   [<span data-ttu-id="ea2e2-198">JsProjectWinRTNamespace 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-198">JsProjectWinRTNamespace Function</span></span>](../chakra-hosting/jsprojectwinrtnamespace-function.md)  
  
-   [<span data-ttu-id="ea2e2-199">JsRelease 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-199">JsRelease Function</span></span>](../chakra-hosting/jsrelease-function.md)  
  
-   [<span data-ttu-id="ea2e2-200">JsRunScript 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-200">JsRunScript Function</span></span>](../chakra-hosting/jsrunscript-function.md)  
  
-   [<span data-ttu-id="ea2e2-201">JsRunSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-201">JsRunSerializedScript Function</span></span>](../chakra-hosting/jsrunserializedscript-function.md)  
  
-   [<span data-ttu-id="ea2e2-202">JsRunSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-202">JsRunSerializedScriptWithCallback Function</span></span>](../chakra-hosting/jsrunserializedscriptwithcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-203">JsSerializeScript 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-203">JsSerializeScript Function</span></span>](../chakra-hosting/jsserializescript-function.md)  
  
-   [<span data-ttu-id="ea2e2-204">JsSetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-204">JsSetContextData Function</span></span>](../chakra-hosting/jssetcontextdata-function.md)  
  
-   [<span data-ttu-id="ea2e2-205">JsSetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-205">JsSetCurrentContext Function</span></span>](../chakra-hosting/jssetcurrentcontext-function.md)  
  
-   [<span data-ttu-id="ea2e2-206">JsSetException 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-206">JsSetException Function</span></span>](../chakra-hosting/jssetexception-function.md)  
  
-   [<span data-ttu-id="ea2e2-207">JsSetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-207">JsSetExternalData Function</span></span>](../chakra-hosting/jssetexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-208">JsSetIndexedPropertiesToExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-208">JsSetIndexedPropertiesToExternalData Function</span></span>](../chakra-hosting/jssetindexedpropertiestoexternaldata-function.md)  
  
-   [<span data-ttu-id="ea2e2-209">JsSetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-209">JsSetIndexedProperty Function</span></span>](../chakra-hosting/jssetindexedproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-210">JsSetObjectBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-210">JsSetObjectBeforeCollectCallback Function</span></span>](../chakra-hosting/jssetobjectbeforecollectcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-211">JsSetProjectionEnqueueCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-211">JsSetProjectionEnqueueCallback Function</span></span>](../chakra-hosting/jssetprojectionenqueuecallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-212">JsSetPromiseContinuationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-212">JsSetPromiseContinuationCallback Function</span></span>](../chakra-hosting/jssetpromisecontinuationcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-213">JsSetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-213">JsSetProperty Function</span></span>](../chakra-hosting/jssetproperty-function.md)  
  
-   [<span data-ttu-id="ea2e2-214">JsSetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-214">JsSetPrototype Function</span></span>](../chakra-hosting/jssetprototype-function.md)  
  
-   [<span data-ttu-id="ea2e2-215">JsSetRuntimeBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-215">JsSetRuntimeBeforeCollectCallback Function</span></span>](../chakra-hosting/jssetruntimebeforecollectcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-216">JsSetRuntimeMemoryAllocationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-216">JsSetRuntimeMemoryAllocationCallback Function</span></span>](../chakra-hosting/jssetruntimememoryallocationcallback-function.md)  
  
-   [<span data-ttu-id="ea2e2-217">JsSetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-217">JsSetRuntimeMemoryLimit Function</span></span>](../chakra-hosting/jssetruntimememorylimit-function.md)  
  
-   [<span data-ttu-id="ea2e2-218">JsStartDebugging 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-218">JsStartDebugging Function</span></span>](../chakra-hosting/jsstartdebugging-function.md)  
  
-   [<span data-ttu-id="ea2e2-219">JsStartProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-219">JsStartProfiling Function</span></span>](../chakra-hosting/jsstartprofiling-function.md)  
  
-   [<span data-ttu-id="ea2e2-220">JsStopProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-220">JsStopProfiling Function</span></span>](../chakra-hosting/jsstopprofiling-function.md)  
  
-   [<span data-ttu-id="ea2e2-221">JsStrictEquals 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-221">JsStrictEquals Function</span></span>](../chakra-hosting/jsstrictequals-function.md)  
  
-   [<span data-ttu-id="ea2e2-222">JsStringToPointer 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-222">JsStringToPointer Function</span></span>](../chakra-hosting/jsstringtopointer-function.md)  
  
-   [<span data-ttu-id="ea2e2-223">JsValueToVariant 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-223">JsValueToVariant Function</span></span>](../chakra-hosting/jsvaluetovariant-function.md)  
  
-   [<span data-ttu-id="ea2e2-224">JsVariantToValue 関数</span><span class="sxs-lookup"><span data-stu-id="ea2e2-224">JsVariantToValue Function</span></span>](../chakra-hosting/jsvarianttovalue-function.md)  
  
## <span data-ttu-id="ea2e2-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea2e2-225">See Also</span></span>  
 [<span data-ttu-id="ea2e2-226">JavaScript ランタイムのホスト</span><span class="sxs-lookup"><span data-stu-id="ea2e2-226">Hosting the JavaScript Runtime</span></span>](../chakra-hosting/hosting-the-javascript-runtime.md)   
 [<span data-ttu-id="ea2e2-227">JavaScript ランタイムホスティング</span><span class="sxs-lookup"><span data-stu-id="ea2e2-227">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)