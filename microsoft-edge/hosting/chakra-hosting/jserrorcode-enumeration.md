---
description: Chakra ホスティング API から返されるエラーコード。
title: JsErrorCode 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3d1a319872ac69b2acaf19997f3c38f9c04597b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570467"
---
# <span data-ttu-id="1f40c-103">JsErrorCode 列挙</span><span class="sxs-lookup"><span data-stu-id="1f40c-103">JsErrorCode Enumeration</span></span>
<span data-ttu-id="1f40c-104">Chakra ホスティング API から返されるエラーコード。</span><span class="sxs-lookup"><span data-stu-id="1f40c-104">An error code returned from a Chakra hosting API.</span></span>  
  
## <span data-ttu-id="1f40c-105">構文</span><span class="sxs-lookup"><span data-stu-id="1f40c-105">Syntax</span></span>  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## <span data-ttu-id="1f40c-106">Members</span><span class="sxs-lookup"><span data-stu-id="1f40c-106">Members</span></span>  
  
### <span data-ttu-id="1f40c-107">値</span><span class="sxs-lookup"><span data-stu-id="1f40c-107">Values</span></span>  
  
|<span data-ttu-id="1f40c-108">名前</span><span class="sxs-lookup"><span data-stu-id="1f40c-108">Name</span></span>|<span data-ttu-id="1f40c-109">説明</span><span class="sxs-lookup"><span data-stu-id="1f40c-109">Description</span></span>|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|<span data-ttu-id="1f40c-110">コンテキストは既にデバッグ状態であるため、デバッグ状態にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-110">The context cannot be put into a debug state because it is already in a debug state.</span></span>|  
|`JsErrorAlreadyProfilingContext`|<span data-ttu-id="1f40c-111">コンテキストは既にプロファイリングされているため、プロファイリングを開始できません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-111">The context cannot start profiling because it is already profiling.</span></span>|  
|`JsErrorArgumentNotObject`|<span data-ttu-id="1f40c-112">オブジェクト値を操作するホスティング API が、オブジェクト以外の値で呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-112">A hosting API that operates on object values was called with a non-object value.</span></span>|  
|`JsErrorBadSerializedScript`|<span data-ttu-id="1f40c-113">シリアル化されたスクリプトが無効になったか、シリアル化されたスクリプトが別のバージョンの Chakra エンジンによってシリアル化されました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-113">A bad serialized script was used, or the serialized script was serialized by a different version of the Chakra engine.</span></span>|  
|`JsErrorCannotDisableExecution`|<span data-ttu-id="1f40c-114">ランタイムは、信頼性の高いスクリプトの中断をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-114">Runtime does not support reliable script interruption.</span></span>|  
|`JsErrorCannotSerializeDebugScript`|<span data-ttu-id="1f40c-115">スクリプトは、デバッグコンテキストでシリアル化することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-115">Scripts cannot be serialized in debug contexts.</span></span>|  
|`JsErrorCategoryEngine`|<span data-ttu-id="1f40c-116">エンジン自体で発生するエラーに関連するエラーのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="1f40c-116">Category of errors that relates to errors occurring within the engine itself.</span></span>|  
|`JsErrorCategoryFatal`|<span data-ttu-id="1f40c-117">致命的で、エンジンの障害を示すエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1f40c-117">Category of errors that are fatal and signify failure of the engine.</span></span>|  
|`JsErrorCategoryScript`|<span data-ttu-id="1f40c-118">スクリプトのエラーに関連するエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1f40c-118">Category of errors that relates to errors in a script.</span></span>|  
|`JsErrorCategoryUsage`|<span data-ttu-id="1f40c-119">API 自体の不適切な使用に関連するエラーのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1f40c-119">Category of errors that relates to incorrect usage of the API itself.</span></span>|  
|`JsErrorFatal`|<span data-ttu-id="1f40c-120">エンジンの致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-120">A fatal error in the engine has occurred.</span></span>|  
|`JsErrorHeapEnumInProgress`|<span data-ttu-id="1f40c-121">ヒープ列挙は、現在スクリプトコンテキストで進行中です。</span><span class="sxs-lookup"><span data-stu-id="1f40c-121">A heap enumeration is currently underway in the script context.</span></span>|  
|`JsErrorIdleNotEnabled`|<span data-ttu-id="1f40c-122">ホストがアイドル処理を有効にしなかったときに表示されるアイドル通知。</span><span class="sxs-lookup"><span data-stu-id="1f40c-122">Idle notification given when the host did not enable idle processing.</span></span>|  
|`JsErrorInDisabledState`|<span data-ttu-id="1f40c-123">ランタイムが無効な状態になっています。</span><span class="sxs-lookup"><span data-stu-id="1f40c-123">The runtime is in a disabled state.</span></span>|  
|`JsErrorInExceptionState`|<span data-ttu-id="1f40c-124">エンジンは例外状態であり、例外が消去されるまで Api を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-124">The engine is in an exception state and no APIs can be called until the exception is cleared.</span></span>|  
|`JsErrorInObjectBeforeCollectCallback`|<span data-ttu-id="1f40c-125">この操作は、コールバックを収集する前にオブジェクトでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-125">The operation is not supported in an object before collect callback.</span></span><br /><br /> <span data-ttu-id="1f40c-126">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1f40c-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorInProfileCallback`|<span data-ttu-id="1f40c-127">スクリプトコンテキストは、プロファイルコールバックの途中にあります。</span><span class="sxs-lookup"><span data-stu-id="1f40c-127">A script context is in the middle of a profile callback.</span></span>|  
|`JsErrorInThreadServiceCallback`|<span data-ttu-id="1f40c-128">スレッドサービスのコールバックは現在進行中です。</span><span class="sxs-lookup"><span data-stu-id="1f40c-128">A thread service callback is currently underway.</span></span>|  
|`JsErrorInvalidArgument`|<span data-ttu-id="1f40c-129">ホスティング API の引数が無効でした。</span><span class="sxs-lookup"><span data-stu-id="1f40c-129">An argument to a hosting API was invalid.</span></span>|  
|`JsErrorNoCurrentContext`|<span data-ttu-id="1f40c-130">ホスティング API では、コンテキストが最新である必要がありますが、現在のコンテキストは存在しません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-130">The hosting API requires that a context be current, but there is no current context.</span></span>|  
|`JsErrorNotImplemented`|<span data-ttu-id="1f40c-131">ホスティング API はまだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-131">A hosting API is not yet implemented.</span></span>|  
|`JsErrorNullArgument`|<span data-ttu-id="1f40c-132">Null が許可されていないコンテキストでホスティング API の引数が null でした。</span><span class="sxs-lookup"><span data-stu-id="1f40c-132">An argument to a hosting API was null in a context where null is not allowed.</span></span>|  
|`JsErrorObjectNotInspectable`|<span data-ttu-id="1f40c-133">オブジェクトをポインターにラップ解除することはできません `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="1f40c-133">Object cannot be unwrapped to `IInspectable` pointer.</span></span><br /><br /> <span data-ttu-id="1f40c-134">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1f40c-134">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorOutOfMemory`|<span data-ttu-id="1f40c-135">Chakra エンジンでメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="1f40c-135">The Chakra engine has run out of memory.</span></span>|  
|`JsErrorPropertyNotSymbol`|<span data-ttu-id="1f40c-136">シンボルプロパティ id に対して動作するが、シンボル以外のプロパティ id で呼び出されたホスト API。このエラーコードは、 `JsGetSymbolFromPropertyId` 関数がシンボル以外のプロパティ id で呼び出された場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="1f40c-136">A hosting API that operates on symbol property ids but was called with a non-symbol property id. The error code is returned by `JsGetSymbolFromPropertyId` if the function is called with non-symbol property id.</span></span><br /><br /> <span data-ttu-id="1f40c-137">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1f40c-137">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorPropertyNotString`|<span data-ttu-id="1f40c-138">文字列プロパティ id に対して動作するが、文字列以外のプロパティ id を使って呼び出されたホスト API。このエラーコードは、 `JsGetPropertyNamefromId` 関数が文字列以外のプロパティ id で呼び出された場合に、既存のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="1f40c-138">A hosting API that operates on string property ids but was called with a non-string property id. The error code is returned by existing `JsGetPropertyNamefromId` if the function is called with non-string property id.</span></span><br /><br /> <span data-ttu-id="1f40c-139">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1f40c-139">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorRuntimeInUse`|<span data-ttu-id="1f40c-140">まだ使用されているランタイムを破棄することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f40c-140">A runtime that is still in use cannot be disposed.</span></span>|  
|`JsErrorScriptCompile`|<span data-ttu-id="1f40c-141">JavaScript のコンパイルに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-141">JavaScript failed to compile.</span></span>|  
|`JsErrorScriptEvalDisabled`|<span data-ttu-id="1f40c-142">`eval`Or eval が無効にされたため、スクリプトは終了されました `function` 。</span><span class="sxs-lookup"><span data-stu-id="1f40c-142">A script was terminated because it tried to use `eval` or `function` and eval was disabled.</span></span>|  
|`JsErrorScriptException`|<span data-ttu-id="1f40c-143">スクリプトの実行中に JavaScript 例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-143">A JavaScript exception occurred while running a script.</span></span>|  
|`JsErrorScriptTerminated`|<span data-ttu-id="1f40c-144">ランタイムの中断要求により、スクリプトが終了されました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-144">A script was terminated due to a request to suspend a runtime.</span></span>|  
|`JsErrorWrongRuntime`|<span data-ttu-id="1f40c-145">異なる JavaScript ランタイムで作成されたオブジェクトとのホスティング API が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-145">A hosting API was called with object created on different JavaScript runtime.</span></span>|  
|`JsErrorWrongThread`|<span data-ttu-id="1f40c-146">間違ったスレッドでホスト API が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="1f40c-146">A hosting API was called on the wrong thread.</span></span>|  
|`JsNoError`|<span data-ttu-id="1f40c-147">成功エラーコード。</span><span class="sxs-lookup"><span data-stu-id="1f40c-147">Success error code.</span></span>|  
  
## <span data-ttu-id="1f40c-148">要件</span><span class="sxs-lookup"><span data-stu-id="1f40c-148">Requirements</span></span>  
 <span data-ttu-id="1f40c-149">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1f40c-149">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1f40c-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f40c-150">See Also</span></span>  
 [<span data-ttu-id="1f40c-151">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1f40c-151">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)