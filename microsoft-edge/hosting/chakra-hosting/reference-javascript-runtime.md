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
# リファレンス (JavaScript runtime)  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

JavaScript Runtime (JsRT) Api を使用すると、Windows で実行されているデスクトップおよびサーバー側アプリケーションにスクリプト機能を追加できます。  

アプリケーションに[ChakraCore](https://github.com/Microsoft/ChakraCore)を埋め込む場合は、代わりに[CHAKRACORE Wiki](https://aka.ms/corejsrtref) for JSRT references を参照してください。  

## このセクションの内容  

JsRT のホスティングをサポートする typedef、定数、および列挙型について説明します。  
  
*   [JavaScript ランタイムの Typedefs、定数および列挙](./javascript-runtime-typedefs-constants-and-enumerations.md)  

JsRT のホストを有効にするには、次の関数を使用します。  

*   [JsAddRef 関数](./jsaddref-function.md)  
*   [JsBooleanToBool 関数](./jsbooleantobool-function.md)  
*   [JsBoolToBoolean 関数](./jsbooltoboolean-function.md)  
*   [JsCallFunction 関数](./jscallfunction-function.md)  
*   [JsCollectGarbage 関数](./jscollectgarbage-function.md)  
*   [JsConstructObject 関数](./jsconstructobject-function.md)  
*   [JsConvertValueToBoolean 関数](./jsconvertvaluetoboolean-function.md)  
*   [JsConvertValueToNumber 関数](./jsconvertvaluetonumber-function.md)  
*   [JsConvertValueToObject 関数](./jsconvertvaluetoobject-function.md)  
*   [JsConvertValueToString 関数](./jsconvertvaluetostring-function.md)  
*   [JsCreateArray 関数](./jscreatearray-function.md)  
*   [JsCreateArrayBuffer 関数](./jscreatearraybuffer-function.md)  
*   [JsCreateContext 関数](./jscreatecontext-function.md)  
*   [JsCreateDataView 関数](./jscreatedataview-function.md)  
*   [JsCreateError 関数](./jscreateerror-function.md)  
*   [JsCreateExternalArrayBuffer 関数](./jscreateexternalarraybuffer-function.md)  
*   [JsCreateExternalObject 関数](./jscreateexternalobject-function.md)  
*   [JsCreateFunction 関数](./jscreatefunction-function.md)  
*   [JsCreateNamedFunction 関数](./jscreatenamedfunction-function.md)  
*   [JsCreateObject 関数](./jscreateobject-function.md)  
*   [JsCreateRangeError 関数](./jscreaterangeerror-function.md)  
*   [JsCreateReferenceError 関数](./jscreatereferenceerror-function.md)  
*   [JsCreateRuntime 関数](./jscreateruntime-function.md)  
*   [JsCreateSymbol 関数](./jscreatesymbol-function.md)  
*   [JsCreateSyntaxError 関数](./jscreatesyntaxerror-function.md)  
*   [JsCreateTypeError 関数](./jscreatetypeerror-function.md)  
*   [JsCreateTypedArray 関数](./jscreatetypedarray-function.md)  
*   [JsCreateURIError 関数](./jscreateurierror-function.md)  
*   [JsDefineProperty 関数](./jsdefineproperty-function.md)  
*   [JsDeleteIndexedProperty 関数](./jsdeleteindexedproperty-function.md)  
*   [JsDeleteProperty 関数](./jsdeleteproperty-function.md)  
*   [JsDisableRuntimeExecution 関数](./jsdisableruntimeexecution-function.md)  
*   [JsDisposeRuntime 関数](./jsdisposeruntime-function.md)  
*   [JsDoubleToNumber 関数](./jsdoubletonumber-function.md)  
*   [JsEnableRuntimeExecution 関数](./jsenableruntimeexecution-function.md)  
*   [JsEnumerateHeap 関数](./jsenumerateheap-function.md)  
*   [JsEquals 関数](./jsequals-function.md)  
*   [JsGetAndClearException 関数](./jsgetandclearexception-function.md)  
*   [JsGetArrayBufferStorage 関数](./jsgetarraybufferstorage-function.md)  
*   [JsGetContextData 関数](./jsgetcontextdata-function.md)  
*   [JsGetContextOfObject 関数](./jsgetcontextofobject-function.md)  
*   [JsGetCurrentContext 関数](./jsgetcurrentcontext-function.md)  
*   [JsGetDataViewStorage 関数](./jsgetdataviewstorage-function.md)  
*   [JsGetExtensionAllowed 関数](./jsgetextensionallowed-function.md)  
*   [JsGetExternalData 関数](./jsgetexternaldata-function.md)  
*   [JsGetFalseValue 関数](./jsgetfalsevalue-function.md)  
*   [JsGetGlobalObject 関数](./jsgetglobalobject-function.md)  
*   [JsGetIndexedPropertiesExternalData 関数](./jsgetindexedpropertiesexternaldata-function.md)  
*   [JsGetIndexedProperty 関数](./jsgetindexedproperty-function.md)  
*   [JsGetNullValue 関数](./jsgetnullvalue-function.md)  
*   [JsGetOwnPropertyDescriptor 関数](./jsgetownpropertydescriptor-function.md)  
*   [JsGetOwnPropertyNames 関数](./jsgetownpropertynames-function.md)  
*   [JsGetOwnPropertySymbols 関数](./jsgetownpropertysymbols-function.md)  
*   [JsGetProperty 関数](./jsgetproperty-function.md)  
*   [JsGetPropertyIdFromName 関数](./jsgetpropertyidfromname-function.md)  
*   [JsGetPropertyIdFromSymbol 関数](./jsgetpropertyidfromsymbol-function.md)  
*   [JsGetPropertyIdType 関数](./jsgetpropertyidtype-function.md)  
*   [JsGetPropertyNameFromId 関数](./jsgetpropertynamefromid-function.md)  
*   [JsGetPrototype 関数](./jsgetprototype-function.md)  
*   [JsGetRuntime 関数](./jsgetruntime-function.md)  
*   [JsGetRuntimeMemoryLimit 関数](./jsgetruntimememorylimit-function.md)  
*   [JsGetRuntimeMemoryUsage 関数](./jsgetruntimememoryusage-function.md)  
*   [JsGetStringLength 関数](./jsgetstringlength-function.md)  
*   [JsGetSymbolFromPropertyId 関数](./jsgetsymbolfrompropertyid-function.md)  
*   [JsGetTrueValue 関数](./jsgettruevalue-function.md)  
*   [JsGetTypedArrayInfo 関数](./jsgettypedarrayinfo-function.md)  
*   [JsGetTypedArrayStorage 関数](./jsgettypedarraystorage-function.md)  
*   [JsGetUndefinedValue 関数](./jsgetundefinedvalue-function.md)  
*   [JsGetValueType 関数](./jsgetvaluetype-function.md)  
*   [JsHasException 関数](./jshasexception-function.md)  
*   [JsHasExternalData 関数](./jshasexternaldata-function.md)  
*   [JsHasIndexedPropertiesExternalData 関数](./jshasindexedpropertiesexternaldata-function.md)  
*   [Jshasedproperty 関数](./jshasindexedproperty-function.md)  
*   [JsHasProperty 関数](./jshasproperty-function.md)  
*   [JsIdle 関数](./jsidle-function.md)  
*   [JsInspectableToObject 関数](./jsinspectabletoobject-function.md)  
*   [JsInstanceOf 関数](./jsinstanceof-function.md)  
*   [JsIntToNumber 関数](./jsinttonumber-function.md)  
*   [JsIsEnumeratingHeap 関数](./jsisenumeratingheap-function.md)  
*   [JsIsRuntimeExecutionDisabled 関数](./jsisruntimeexecutiondisabled-function.md)  
*   [JsNumberToDouble 関数](./jsnumbertodouble-function.md)  
*   [JsNumberToInt 関数](./jsnumbertoint-function.md)  
*   [JsObjectToInspectable 関数](./jsobjecttoinspectable-function.md)  
*   [JsParseScript 関数](./jsparsescript-function.md)  
*   [JsParseSerializedScript 関数](./jsparseserializedscript-function.md)  
*   [JsParseSerializedScriptWithCallback 関数](./jsparseserializedscriptwithcallback-function.md)  
*   [JsPointerToString 関数](./jspointertostring-function.md)  
*   [JsPreventExtension 関数](./jspreventextension-function.md)  
*   [JsProjectWinRTNamespace 関数](./jsprojectwinrtnamespace-function.md)  
*   [JsRelease 関数](./jsrelease-function.md)  
*   [JsRunScript 関数](./jsrunscript-function.md)  
*   [JsRunSerializedScript 関数](./jsrunserializedscript-function.md)  
*   [JsRunSerializedScriptWithCallback 関数](./jsrunserializedscriptwithcallback-function.md)  
*   [JsSerializeScript 関数](./jsserializescript-function.md)  
*   [JsSetContextData 関数](./jssetcontextdata-function.md)  
*   [JsSetCurrentContext 関数](./jssetcurrentcontext-function.md)  
*   [JsSetException 関数](./jssetexception-function.md)  
*   [JsSetExternalData 関数](./jssetexternaldata-function.md)  
*   [JsSetIndexedPropertiesToExternalData 関数](./jssetindexedpropertiestoexternaldata-function.md)  
*   [JsSetIndexedProperty 関数](./jssetindexedproperty-function.md)  
*   [JsSetObjectBeforeCollectCallback 関数](./jssetobjectbeforecollectcallback-function.md)  
*   [JsSetProjectionEnqueueCallback 関数](./jssetprojectionenqueuecallback-function.md)  
*   [JsSetPromiseContinuationCallback 関数](./jssetpromisecontinuationcallback-function.md)  
*   [JsSetProperty 関数](./jssetproperty-function.md)  
*   [JsSetPrototype 関数](./jssetprototype-function.md)  
*   [JsSetRuntimeBeforeCollectCallback 関数](./jssetruntimebeforecollectcallback-function.md)  
*   [JsSetRuntimeMemoryAllocationCallback 関数](./jssetruntimememoryallocationcallback-function.md)  
*   [JsSetRuntimeMemoryLimit 関数](./jssetruntimememorylimit-function.md)  
*   [JsStartDebugging 関数](./jsstartdebugging-function.md)  
*   [JsStartProfiling 関数](./jsstartprofiling-function.md)  
*   [JsStopProfiling 関数](./jsstopprofiling-function.md)  
*   [JsStrictEquals 関数](./jsstrictequals-function.md)  
*   [JsStringToPointer 関数](./jsstringtopointer-function.md)  
*   [JsValueToVariant 関数](./jsvaluetovariant-function.md)  
*   [JsVariantToValue 関数](./jsvarianttovalue-function.md)  

## 関連項目  

*   [JavaScript ランタイムのホスティング](./hosting-the-javascript-runtime.md)  
*   [JavaScript ランタイムのホスティング](../javascript-runtime-hosting.md)  
