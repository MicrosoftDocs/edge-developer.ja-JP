---
description: JavaScript Runtime (JsRT) Api を使用すると、Windows で実行されているデスクトップおよびサーバー側アプリケーションにスクリプト機能を追加できます。
title: リファレンス (JavaScript ランタイム)
ms.date: 06/08/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 0bfe50da-fd79-4e00-9458-bc667769b415
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 7166e6cd5d64060c2939d8404e1415dc34fce17b
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752214"
---
# <span data-ttu-id="30cbc-103">リファレンス (JavaScript runtime)</span><span class="sxs-lookup"><span data-stu-id="30cbc-103">Reference (JavaScript runtime)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="30cbc-104">JavaScript Runtime (JsRT) Api を使用すると、Windows で実行されているデスクトップおよびサーバー側アプリケーションにスクリプト機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="30cbc-104">JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.</span></span>  

<span data-ttu-id="30cbc-105">アプリケーションに[ChakraCore](https://github.com/Microsoft/ChakraCore)を埋め込む場合は、代わりに[CHAKRACORE Wiki](https://aka.ms/corejsrtref) for JSRT references を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30cbc-105">If you intend to embed [ChakraCore](https://github.com/Microsoft/ChakraCore) in your application, please refer to [ChakraCore Wiki](https://aka.ms/corejsrtref) for JSRT references instead.</span></span>  

## <span data-ttu-id="30cbc-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="30cbc-106">In this section</span></span>  

<span data-ttu-id="30cbc-107">JsRT のホスティングをサポートする typedef、定数、および列挙型について説明します。</span><span class="sxs-lookup"><span data-stu-id="30cbc-107">Typedefs, constants, and enumerations that support JsRT hosting are described here:</span></span>  
  
*   [<span data-ttu-id="30cbc-108">JavaScript ランタイムの Typedefs、定数および列挙</span><span class="sxs-lookup"><span data-stu-id="30cbc-108">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>](./javascript-runtime-typedefs-constants-and-enumerations.md)  

<span data-ttu-id="30cbc-109">JsRT のホストを有効にするには、次の関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="30cbc-109">The following functions enable JsRT hosting:</span></span>  

*   [<span data-ttu-id="30cbc-110">JsAddRef 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-110">JsAddRef Function</span></span>](./jsaddref-function.md)  
*   [<span data-ttu-id="30cbc-111">JsBooleanToBool 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-111">JsBooleanToBool Function</span></span>](./jsbooleantobool-function.md)  
*   [<span data-ttu-id="30cbc-112">JsBoolToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-112">JsBoolToBoolean Function</span></span>](./jsbooltoboolean-function.md)  
*   [<span data-ttu-id="30cbc-113">JsCallFunction 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-113">JsCallFunction Function</span></span>](./jscallfunction-function.md)  
*   [<span data-ttu-id="30cbc-114">JsCollectGarbage 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-114">JsCollectGarbage Function</span></span>](./jscollectgarbage-function.md)  
*   [<span data-ttu-id="30cbc-115">JsConstructObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-115">JsConstructObject Function</span></span>](./jsconstructobject-function.md)  
*   [<span data-ttu-id="30cbc-116">JsConvertValueToBoolean 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-116">JsConvertValueToBoolean Function</span></span>](./jsconvertvaluetoboolean-function.md)  
*   [<span data-ttu-id="30cbc-117">JsConvertValueToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-117">JsConvertValueToNumber Function</span></span>](./jsconvertvaluetonumber-function.md)  
*   [<span data-ttu-id="30cbc-118">JsConvertValueToObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-118">JsConvertValueToObject Function</span></span>](./jsconvertvaluetoobject-function.md)  
*   [<span data-ttu-id="30cbc-119">JsConvertValueToString 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-119">JsConvertValueToString Function</span></span>](./jsconvertvaluetostring-function.md)  
*   [<span data-ttu-id="30cbc-120">JsCreateArray 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-120">JsCreateArray Function</span></span>](./jscreatearray-function.md)  
*   [<span data-ttu-id="30cbc-121">JsCreateArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-121">JsCreateArrayBuffer Function</span></span>](./jscreatearraybuffer-function.md)  
*   [<span data-ttu-id="30cbc-122">JsCreateContext 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-122">JsCreateContext Function</span></span>](./jscreatecontext-function.md)  
*   [<span data-ttu-id="30cbc-123">JsCreateDataView 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-123">JsCreateDataView Function</span></span>](./jscreatedataview-function.md)  
*   [<span data-ttu-id="30cbc-124">JsCreateError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-124">JsCreateError Function</span></span>](./jscreateerror-function.md)  
*   [<span data-ttu-id="30cbc-125">JsCreateExternalArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-125">JsCreateExternalArrayBuffer Function</span></span>](./jscreateexternalarraybuffer-function.md)  
*   [<span data-ttu-id="30cbc-126">JsCreateExternalObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-126">JsCreateExternalObject Function</span></span>](./jscreateexternalobject-function.md)  
*   [<span data-ttu-id="30cbc-127">JsCreateFunction 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-127">JsCreateFunction Function</span></span>](./jscreatefunction-function.md)  
*   [<span data-ttu-id="30cbc-128">JsCreateNamedFunction 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-128">JsCreateNamedFunction Function</span></span>](./jscreatenamedfunction-function.md)  
*   [<span data-ttu-id="30cbc-129">JsCreateObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-129">JsCreateObject Function</span></span>](./jscreateobject-function.md)  
*   [<span data-ttu-id="30cbc-130">JsCreateRangeError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-130">JsCreateRangeError Function</span></span>](./jscreaterangeerror-function.md)  
*   [<span data-ttu-id="30cbc-131">JsCreateReferenceError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-131">JsCreateReferenceError Function</span></span>](./jscreatereferenceerror-function.md)  
*   [<span data-ttu-id="30cbc-132">JsCreateRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-132">JsCreateRuntime Function</span></span>](./jscreateruntime-function.md)  
*   [<span data-ttu-id="30cbc-133">JsCreateSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-133">JsCreateSymbol Function</span></span>](./jscreatesymbol-function.md)  
*   [<span data-ttu-id="30cbc-134">JsCreateSyntaxError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-134">JsCreateSyntaxError Function</span></span>](./jscreatesyntaxerror-function.md)  
*   [<span data-ttu-id="30cbc-135">JsCreateTypeError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-135">JsCreateTypeError Function</span></span>](./jscreatetypeerror-function.md)  
*   [<span data-ttu-id="30cbc-136">JsCreateTypedArray 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-136">JsCreateTypedArray Function</span></span>](./jscreatetypedarray-function.md)  
*   [<span data-ttu-id="30cbc-137">JsCreateURIError 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-137">JsCreateURIError Function</span></span>](./jscreateurierror-function.md)  
*   [<span data-ttu-id="30cbc-138">JsDefineProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-138">JsDefineProperty Function</span></span>](./jsdefineproperty-function.md)  
*   [<span data-ttu-id="30cbc-139">JsDeleteIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-139">JsDeleteIndexedProperty Function</span></span>](./jsdeleteindexedproperty-function.md)  
*   [<span data-ttu-id="30cbc-140">JsDeleteProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-140">JsDeleteProperty Function</span></span>](./jsdeleteproperty-function.md)  
*   [<span data-ttu-id="30cbc-141">JsDisableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-141">JsDisableRuntimeExecution Function</span></span>](./jsdisableruntimeexecution-function.md)  
*   [<span data-ttu-id="30cbc-142">JsDisposeRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-142">JsDisposeRuntime Function</span></span>](./jsdisposeruntime-function.md)  
*   [<span data-ttu-id="30cbc-143">JsDoubleToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-143">JsDoubleToNumber Function</span></span>](./jsdoubletonumber-function.md)  
*   [<span data-ttu-id="30cbc-144">JsEnableRuntimeExecution 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-144">JsEnableRuntimeExecution Function</span></span>](./jsenableruntimeexecution-function.md)  
*   [<span data-ttu-id="30cbc-145">JsEnumerateHeap 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-145">JsEnumerateHeap Function</span></span>](./jsenumerateheap-function.md)  
*   [<span data-ttu-id="30cbc-146">JsEquals 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-146">JsEquals Function</span></span>](./jsequals-function.md)  
*   [<span data-ttu-id="30cbc-147">JsGetAndClearException 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-147">JsGetAndClearException Function</span></span>](./jsgetandclearexception-function.md)  
*   [<span data-ttu-id="30cbc-148">JsGetArrayBufferStorage 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-148">JsGetArrayBufferStorage Function</span></span>](./jsgetarraybufferstorage-function.md)  
*   [<span data-ttu-id="30cbc-149">JsGetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-149">JsGetContextData Function</span></span>](./jsgetcontextdata-function.md)  
*   [<span data-ttu-id="30cbc-150">JsGetContextOfObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-150">JsGetContextOfObject Function</span></span>](./jsgetcontextofobject-function.md)  
*   [<span data-ttu-id="30cbc-151">JsGetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-151">JsGetCurrentContext Function</span></span>](./jsgetcurrentcontext-function.md)  
*   [<span data-ttu-id="30cbc-152">JsGetDataViewStorage 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-152">JsGetDataViewStorage Function</span></span>](./jsgetdataviewstorage-function.md)  
*   [<span data-ttu-id="30cbc-153">JsGetExtensionAllowed 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-153">JsGetExtensionAllowed Function</span></span>](./jsgetextensionallowed-function.md)  
*   [<span data-ttu-id="30cbc-154">JsGetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-154">JsGetExternalData Function</span></span>](./jsgetexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-155">JsGetFalseValue 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-155">JsGetFalseValue Function</span></span>](./jsgetfalsevalue-function.md)  
*   [<span data-ttu-id="30cbc-156">JsGetGlobalObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-156">JsGetGlobalObject Function</span></span>](./jsgetglobalobject-function.md)  
*   [<span data-ttu-id="30cbc-157">JsGetIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-157">JsGetIndexedPropertiesExternalData Function</span></span>](./jsgetindexedpropertiesexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-158">JsGetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-158">JsGetIndexedProperty Function</span></span>](./jsgetindexedproperty-function.md)  
*   [<span data-ttu-id="30cbc-159">JsGetNullValue 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-159">JsGetNullValue Function</span></span>](./jsgetnullvalue-function.md)  
*   [<span data-ttu-id="30cbc-160">JsGetOwnPropertyDescriptor 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-160">JsGetOwnPropertyDescriptor Function</span></span>](./jsgetownpropertydescriptor-function.md)  
*   [<span data-ttu-id="30cbc-161">JsGetOwnPropertyNames 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-161">JsGetOwnPropertyNames Function</span></span>](./jsgetownpropertynames-function.md)  
*   [<span data-ttu-id="30cbc-162">JsGetOwnPropertySymbols 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-162">JsGetOwnPropertySymbols Function</span></span>](./jsgetownpropertysymbols-function.md)  
*   [<span data-ttu-id="30cbc-163">JsGetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-163">JsGetProperty Function</span></span>](./jsgetproperty-function.md)  
*   [<span data-ttu-id="30cbc-164">JsGetPropertyIdFromName 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-164">JsGetPropertyIdFromName Function</span></span>](./jsgetpropertyidfromname-function.md)  
*   [<span data-ttu-id="30cbc-165">JsGetPropertyIdFromSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-165">JsGetPropertyIdFromSymbol Function</span></span>](./jsgetpropertyidfromsymbol-function.md)  
*   [<span data-ttu-id="30cbc-166">JsGetPropertyIdType 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-166">JsGetPropertyIdType Function</span></span>](./jsgetpropertyidtype-function.md)  
*   [<span data-ttu-id="30cbc-167">JsGetPropertyNameFromId 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-167">JsGetPropertyNameFromId Function</span></span>](./jsgetpropertynamefromid-function.md)  
*   [<span data-ttu-id="30cbc-168">JsGetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-168">JsGetPrototype Function</span></span>](./jsgetprototype-function.md)  
*   [<span data-ttu-id="30cbc-169">JsGetRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-169">JsGetRuntime Function</span></span>](./jsgetruntime-function.md)  
*   [<span data-ttu-id="30cbc-170">JsGetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-170">JsGetRuntimeMemoryLimit Function</span></span>](./jsgetruntimememorylimit-function.md)  
*   [<span data-ttu-id="30cbc-171">JsGetRuntimeMemoryUsage 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-171">JsGetRuntimeMemoryUsage Function</span></span>](./jsgetruntimememoryusage-function.md)  
*   [<span data-ttu-id="30cbc-172">JsGetStringLength 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-172">JsGetStringLength Function</span></span>](./jsgetstringlength-function.md)  
*   [<span data-ttu-id="30cbc-173">JsGetSymbolFromPropertyId 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-173">JsGetSymbolFromPropertyId Function</span></span>](./jsgetsymbolfrompropertyid-function.md)  
*   [<span data-ttu-id="30cbc-174">JsGetTrueValue 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-174">JsGetTrueValue Function</span></span>](./jsgettruevalue-function.md)  
*   [<span data-ttu-id="30cbc-175">JsGetTypedArrayInfo 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-175">JsGetTypedArrayInfo Function</span></span>](./jsgettypedarrayinfo-function.md)  
*   [<span data-ttu-id="30cbc-176">JsGetTypedArrayStorage 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-176">JsGetTypedArrayStorage Function</span></span>](./jsgettypedarraystorage-function.md)  
*   [<span data-ttu-id="30cbc-177">JsGetUndefinedValue 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-177">JsGetUndefinedValue Function</span></span>](./jsgetundefinedvalue-function.md)  
*   [<span data-ttu-id="30cbc-178">JsGetValueType 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-178">JsGetValueType Function</span></span>](./jsgetvaluetype-function.md)  
*   [<span data-ttu-id="30cbc-179">JsHasException 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-179">JsHasException Function</span></span>](./jshasexception-function.md)  
*   [<span data-ttu-id="30cbc-180">JsHasExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-180">JsHasExternalData Function</span></span>](./jshasexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-181">JsHasIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-181">JsHasIndexedPropertiesExternalData Function</span></span>](./jshasindexedpropertiesexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-182">Jshasedproperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-182">JsHasIndexedProperty Function</span></span>](./jshasindexedproperty-function.md)  
*   [<span data-ttu-id="30cbc-183">JsHasProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-183">JsHasProperty Function</span></span>](./jshasproperty-function.md)  
*   [<span data-ttu-id="30cbc-184">JsIdle 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-184">JsIdle Function</span></span>](./jsidle-function.md)  
*   [<span data-ttu-id="30cbc-185">JsInspectableToObject 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-185">JsInspectableToObject Function</span></span>](./jsinspectabletoobject-function.md)  
*   [<span data-ttu-id="30cbc-186">JsInstanceOf 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-186">JsInstanceOf Function</span></span>](./jsinstanceof-function.md)  
*   [<span data-ttu-id="30cbc-187">JsIntToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-187">JsIntToNumber Function</span></span>](./jsinttonumber-function.md)  
*   [<span data-ttu-id="30cbc-188">JsIsEnumeratingHeap 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-188">JsIsEnumeratingHeap Function</span></span>](./jsisenumeratingheap-function.md)  
*   [<span data-ttu-id="30cbc-189">JsIsRuntimeExecutionDisabled 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-189">JsIsRuntimeExecutionDisabled Function</span></span>](./jsisruntimeexecutiondisabled-function.md)  
*   [<span data-ttu-id="30cbc-190">JsNumberToDouble 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-190">JsNumberToDouble Function</span></span>](./jsnumbertodouble-function.md)  
*   [<span data-ttu-id="30cbc-191">JsNumberToInt 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-191">JsNumberToInt Function</span></span>](./jsnumbertoint-function.md)  
*   [<span data-ttu-id="30cbc-192">JsObjectToInspectable 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-192">JsObjectToInspectable Function</span></span>](./jsobjecttoinspectable-function.md)  
*   [<span data-ttu-id="30cbc-193">JsParseScript 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-193">JsParseScript Function</span></span>](./jsparsescript-function.md)  
*   [<span data-ttu-id="30cbc-194">JsParseSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-194">JsParseSerializedScript Function</span></span>](./jsparseserializedscript-function.md)  
*   [<span data-ttu-id="30cbc-195">JsParseSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-195">JsParseSerializedScriptWithCallback Function</span></span>](./jsparseserializedscriptwithcallback-function.md)  
*   [<span data-ttu-id="30cbc-196">JsPointerToString 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-196">JsPointerToString Function</span></span>](./jspointertostring-function.md)  
*   [<span data-ttu-id="30cbc-197">JsPreventExtension 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-197">JsPreventExtension Function</span></span>](./jspreventextension-function.md)  
*   [<span data-ttu-id="30cbc-198">JsProjectWinRTNamespace 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-198">JsProjectWinRTNamespace Function</span></span>](./jsprojectwinrtnamespace-function.md)  
*   [<span data-ttu-id="30cbc-199">JsRelease 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-199">JsRelease Function</span></span>](./jsrelease-function.md)  
*   [<span data-ttu-id="30cbc-200">JsRunScript 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-200">JsRunScript Function</span></span>](./jsrunscript-function.md)  
*   [<span data-ttu-id="30cbc-201">JsRunSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-201">JsRunSerializedScript Function</span></span>](./jsrunserializedscript-function.md)  
*   [<span data-ttu-id="30cbc-202">JsRunSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-202">JsRunSerializedScriptWithCallback Function</span></span>](./jsrunserializedscriptwithcallback-function.md)  
*   [<span data-ttu-id="30cbc-203">JsSerializeScript 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-203">JsSerializeScript Function</span></span>](./jsserializescript-function.md)  
*   [<span data-ttu-id="30cbc-204">JsSetContextData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-204">JsSetContextData Function</span></span>](./jssetcontextdata-function.md)  
*   [<span data-ttu-id="30cbc-205">JsSetCurrentContext 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-205">JsSetCurrentContext Function</span></span>](./jssetcurrentcontext-function.md)  
*   [<span data-ttu-id="30cbc-206">JsSetException 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-206">JsSetException Function</span></span>](./jssetexception-function.md)  
*   [<span data-ttu-id="30cbc-207">JsSetExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-207">JsSetExternalData Function</span></span>](./jssetexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-208">JsSetIndexedPropertiesToExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-208">JsSetIndexedPropertiesToExternalData Function</span></span>](./jssetindexedpropertiestoexternaldata-function.md)  
*   [<span data-ttu-id="30cbc-209">JsSetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-209">JsSetIndexedProperty Function</span></span>](./jssetindexedproperty-function.md)  
*   [<span data-ttu-id="30cbc-210">JsSetObjectBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-210">JsSetObjectBeforeCollectCallback Function</span></span>](./jssetobjectbeforecollectcallback-function.md)  
*   [<span data-ttu-id="30cbc-211">JsSetProjectionEnqueueCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-211">JsSetProjectionEnqueueCallback Function</span></span>](./jssetprojectionenqueuecallback-function.md)  
*   [<span data-ttu-id="30cbc-212">JsSetPromiseContinuationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-212">JsSetPromiseContinuationCallback Function</span></span>](./jssetpromisecontinuationcallback-function.md)  
*   [<span data-ttu-id="30cbc-213">JsSetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-213">JsSetProperty Function</span></span>](./jssetproperty-function.md)  
*   [<span data-ttu-id="30cbc-214">JsSetPrototype 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-214">JsSetPrototype Function</span></span>](./jssetprototype-function.md)  
*   [<span data-ttu-id="30cbc-215">JsSetRuntimeBeforeCollectCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-215">JsSetRuntimeBeforeCollectCallback Function</span></span>](./jssetruntimebeforecollectcallback-function.md)  
*   [<span data-ttu-id="30cbc-216">JsSetRuntimeMemoryAllocationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-216">JsSetRuntimeMemoryAllocationCallback Function</span></span>](./jssetruntimememoryallocationcallback-function.md)  
*   [<span data-ttu-id="30cbc-217">JsSetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-217">JsSetRuntimeMemoryLimit Function</span></span>](./jssetruntimememorylimit-function.md)  
*   [<span data-ttu-id="30cbc-218">JsStartDebugging 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-218">JsStartDebugging Function</span></span>](./jsstartdebugging-function.md)  
*   [<span data-ttu-id="30cbc-219">JsStartProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-219">JsStartProfiling Function</span></span>](./jsstartprofiling-function.md)  
*   [<span data-ttu-id="30cbc-220">JsStopProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-220">JsStopProfiling Function</span></span>](./jsstopprofiling-function.md)  
*   [<span data-ttu-id="30cbc-221">JsStrictEquals 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-221">JsStrictEquals Function</span></span>](./jsstrictequals-function.md)  
*   [<span data-ttu-id="30cbc-222">JsStringToPointer 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-222">JsStringToPointer Function</span></span>](./jsstringtopointer-function.md)  
*   [<span data-ttu-id="30cbc-223">JsValueToVariant 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-223">JsValueToVariant Function</span></span>](./jsvaluetovariant-function.md)  
*   [<span data-ttu-id="30cbc-224">JsVariantToValue 関数</span><span class="sxs-lookup"><span data-stu-id="30cbc-224">JsVariantToValue Function</span></span>](./jsvarianttovalue-function.md)  

## <span data-ttu-id="30cbc-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="30cbc-225">See also</span></span>  

*   [<span data-ttu-id="30cbc-226">JavaScript ランタイムのホスティング</span><span class="sxs-lookup"><span data-stu-id="30cbc-226">Hosting the JavaScript Runtime</span></span>](./hosting-the-javascript-runtime.md)  
*   [<span data-ttu-id="30cbc-227">JavaScript ランタイムのホスティング</span><span class="sxs-lookup"><span data-stu-id="30cbc-227">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)  
