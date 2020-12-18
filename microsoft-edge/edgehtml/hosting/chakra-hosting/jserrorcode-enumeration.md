---
description: チャクラ ホスティング API から返されたエラー コード。
title: JsErrorCode 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b0a4aa7b47070bd5c8c7fe48cdbecf0dbefa9aa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234664"
---
# <span data-ttu-id="bba85-103">JsErrorCode 列挙</span><span class="sxs-lookup"><span data-stu-id="bba85-103">JsErrorCode Enumeration</span></span>

<span data-ttu-id="bba85-104">チャクラ ホスティング API から返されたエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bba85-104">An error code returned from a Chakra hosting API.</span></span>  
  
## <span data-ttu-id="bba85-105">構文</span><span class="sxs-lookup"><span data-stu-id="bba85-105">Syntax</span></span>  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## <span data-ttu-id="bba85-106">Members</span><span class="sxs-lookup"><span data-stu-id="bba85-106">Members</span></span>  
  
### <span data-ttu-id="bba85-107">値</span><span class="sxs-lookup"><span data-stu-id="bba85-107">Values</span></span>  
  
|<span data-ttu-id="bba85-108">名前</span><span class="sxs-lookup"><span data-stu-id="bba85-108">Name</span></span>|<span data-ttu-id="bba85-109">説明</span><span class="sxs-lookup"><span data-stu-id="bba85-109">Description</span></span>|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|<span data-ttu-id="bba85-110">コンテキストは既にデバッグ状態なので、デバッグ状態にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bba85-110">The context cannot be put into a debug state because it is already in a debug state.</span></span>|  
|`JsErrorAlreadyProfilingContext`|<span data-ttu-id="bba85-111">コンテキストは既にプロファイリングを行っているので、プロファイリングを開始できません。</span><span class="sxs-lookup"><span data-stu-id="bba85-111">The context cannot start profiling because it is already profiling.</span></span>|  
|`JsErrorArgumentNotObject`|<span data-ttu-id="bba85-112">オブジェクト値を操作するホスティング API が、オブジェクト以外の値で呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="bba85-112">A hosting API that operates on object values was called with a non-object value.</span></span>|  
|`JsErrorBadSerializedScript`|<span data-ttu-id="bba85-113">シリアル化されたスクリプトが使用されていないか、シリアル化されたスクリプトが別のバージョンのチャクラ エンジンによってシリアル化されました。</span><span class="sxs-lookup"><span data-stu-id="bba85-113">A bad serialized script was used, or the serialized script was serialized by a different version of the Chakra engine.</span></span>|  
|`JsErrorCannotDisableExecution`|<span data-ttu-id="bba85-114">ランタイムは、信頼性の高いスクリプト中断をサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="bba85-114">Runtime does not support reliable script interruption.</span></span>|  
|`JsErrorCannotSerializeDebugScript`|<span data-ttu-id="bba85-115">スクリプトはデバッグ コンテキストではシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="bba85-115">Scripts cannot be serialized in debug contexts.</span></span>|  
|`JsErrorCategoryEngine`|<span data-ttu-id="bba85-116">エンジン自体で発生するエラーに関連するエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="bba85-116">Category of errors that relates to errors occurring within the engine itself.</span></span>|  
|`JsErrorCategoryFatal`|<span data-ttu-id="bba85-117">致命的で、エンジンのエラーを示すエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="bba85-117">Category of errors that are fatal and signify failure of the engine.</span></span>|  
|`JsErrorCategoryScript`|<span data-ttu-id="bba85-118">スクリプト内のエラーに関連するエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="bba85-118">Category of errors that relates to errors in a script.</span></span>|  
|`JsErrorCategoryUsage`|<span data-ttu-id="bba85-119">API 自体の不適切な使用に関連するエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="bba85-119">Category of errors that relates to incorrect usage of the API itself.</span></span>|  
|`JsErrorFatal`|<span data-ttu-id="bba85-120">エンジンで致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bba85-120">A fatal error in the engine has occurred.</span></span>|  
|`JsErrorHeapEnumInProgress`|<span data-ttu-id="bba85-121">現在、スクリプト コンテキストでヒープ列挙が進行中です。</span><span class="sxs-lookup"><span data-stu-id="bba85-121">A heap enumeration is currently underway in the script context.</span></span>|  
|`JsErrorIdleNotEnabled`|<span data-ttu-id="bba85-122">ホストがアイドル処理を有効にしなかったときに発生するアイドル通知。</span><span class="sxs-lookup"><span data-stu-id="bba85-122">Idle notification given when the host did not enable idle processing.</span></span>|  
|`JsErrorInDisabledState`|<span data-ttu-id="bba85-123">ランタイムは無効な状態です。</span><span class="sxs-lookup"><span data-stu-id="bba85-123">The runtime is in a disabled state.</span></span>|  
|`JsErrorInExceptionState`|<span data-ttu-id="bba85-124">エンジンは例外状態であり、例外がクリアされるまで API は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="bba85-124">The engine is in an exception state and no APIs can be called until the exception is cleared.</span></span>|  
|`JsErrorInObjectBeforeCollectCallback`|<span data-ttu-id="bba85-125">この操作は、コールバックを収集する前のオブジェクトではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bba85-125">The operation is not supported in an object before collect callback.</span></span><br /><br /> <span data-ttu-id="bba85-126">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bba85-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorInProfileCallback`|<span data-ttu-id="bba85-127">スクリプト コンテキストは、プロファイル コールバックの途中です。</span><span class="sxs-lookup"><span data-stu-id="bba85-127">A script context is in the middle of a profile callback.</span></span>|  
|`JsErrorInThreadServiceCallback`|<span data-ttu-id="bba85-128">スレッド サービスコールバックは現在進行中です。</span><span class="sxs-lookup"><span data-stu-id="bba85-128">A thread service callback is currently underway.</span></span>|  
|`JsErrorInvalidArgument`|<span data-ttu-id="bba85-129">ホスティング API に対する引数が無効です。</span><span class="sxs-lookup"><span data-stu-id="bba85-129">An argument to a hosting API was invalid.</span></span>|  
|`JsErrorNoCurrentContext`|<span data-ttu-id="bba85-130">ホスティング API では、コンテキストが最新である必要がありますが、現在のコンテキストはありません。</span><span class="sxs-lookup"><span data-stu-id="bba85-130">The hosting API requires that a context be current, but there is no current context.</span></span>|  
|`JsErrorNotImplemented`|<span data-ttu-id="bba85-131">ホスティング API はまだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="bba85-131">A hosting API is not yet implemented.</span></span>|  
|`JsErrorNullArgument`|<span data-ttu-id="bba85-132">ホスティング API に対する引数は、null が許可されていないコンテキストでは null でした。</span><span class="sxs-lookup"><span data-stu-id="bba85-132">An argument to a hosting API was null in a context where null is not allowed.</span></span>|  
|`JsErrorObjectNotInspectable`|<span data-ttu-id="bba85-133">オブジェクトをポインターに対して折り返 `IInspectable` し解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="bba85-133">Object cannot be unwrapped to `IInspectable` pointer.</span></span><br /><br /> <span data-ttu-id="bba85-134">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bba85-134">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorOutOfMemory`|<span data-ttu-id="bba85-135">チャクラ エンジンのメモリが使い切った。</span><span class="sxs-lookup"><span data-stu-id="bba85-135">The Chakra engine has run out of memory.</span></span>|  
|`JsErrorPropertyNotSymbol`|<span data-ttu-id="bba85-136">シンボル プロパティ ID で動作するが、シンボル以外のプロパティ ID で呼び出されたホスティング API。シンボル以外のプロパティ ID で関数が呼び出された場合、エラー `JsGetSymbolFromPropertyId` コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="bba85-136">A hosting API that operates on symbol property ids but was called with a non-symbol property id. The error code is returned by `JsGetSymbolFromPropertyId` if the function is called with non-symbol property id.</span></span><br /><br /> <span data-ttu-id="bba85-137">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bba85-137">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorPropertyNotString`|<span data-ttu-id="bba85-138">文字列プロパティ ID を操作するが、文字列以外のプロパティ ID で呼び出されたホスティング API。文字列以外のプロパティ ID で関数が呼び出された場合は、既存のエラー `JsGetPropertyNamefromId` コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="bba85-138">A hosting API that operates on string property ids but was called with a non-string property id. The error code is returned by existing `JsGetPropertyNamefromId` if the function is called with non-string property id.</span></span><br /><br /> <span data-ttu-id="bba85-139">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bba85-139">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorRuntimeInUse`|<span data-ttu-id="bba85-140">まだ使用されているランタイムは破棄できません。</span><span class="sxs-lookup"><span data-stu-id="bba85-140">A runtime that is still in use cannot be disposed.</span></span>|  
|`JsErrorScriptCompile`|<span data-ttu-id="bba85-141">JavaScript のコンパイルに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bba85-141">JavaScript failed to compile.</span></span>|  
|`JsErrorScriptEvalDisabled`|<span data-ttu-id="bba85-142">スクリプトが使用しようとしたか、または無効にされたため `eval` 、 `function` スクリプトは終了されました。</span><span class="sxs-lookup"><span data-stu-id="bba85-142">A script was terminated because it tried to use `eval` or `function` and eval was disabled.</span></span>|  
|`JsErrorScriptException`|<span data-ttu-id="bba85-143">スクリプトの実行中に JavaScript 例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="bba85-143">A JavaScript exception occurred while running a script.</span></span>|  
|`JsErrorScriptTerminated`|<span data-ttu-id="bba85-144">ランタイムを中断する要求が原因でスクリプトが終了しました。</span><span class="sxs-lookup"><span data-stu-id="bba85-144">A script was terminated due to a request to suspend a runtime.</span></span>|  
|`JsErrorWrongRuntime`|<span data-ttu-id="bba85-145">異なる JavaScript ランタイムで作成されたオブジェクトを使用して、ホスティング API が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="bba85-145">A hosting API was called with object created on different JavaScript runtime.</span></span>|  
|`JsErrorWrongThread`|<span data-ttu-id="bba85-146">ホスティング API が間違ったスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="bba85-146">A hosting API was called on the wrong thread.</span></span>|  
|`JsNoError`|<span data-ttu-id="bba85-147">成功エラー コード。</span><span class="sxs-lookup"><span data-stu-id="bba85-147">Success error code.</span></span>|  
  
## <span data-ttu-id="bba85-148">要件</span><span class="sxs-lookup"><span data-stu-id="bba85-148">Requirements</span></span>  
 <span data-ttu-id="bba85-149">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bba85-149">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bba85-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="bba85-150">See Also</span></span>  
 [<span data-ttu-id="bba85-151">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bba85-151">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
