---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。  ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。  評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。  元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9aa87c1c289452844ef3442811f84881fc752b4
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397693"
---
# <a name="runtime-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="299d7-106">ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="299d7-106">Runtime Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="299d7-107">ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="299d7-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span>  <span data-ttu-id="299d7-108">評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span>  <span data-ttu-id="299d7-109">元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>  

| <span data-ttu-id="299d7-110">分類</span><span class="sxs-lookup"><span data-stu-id="299d7-110">Classification</span></span> | <span data-ttu-id="299d7-111">Members</span><span class="sxs-lookup"><span data-stu-id="299d7-111">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="299d7-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="299d7-112">Methods</span></span>](#methods) | <span data-ttu-id="299d7-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span><span class="sxs-lookup"><span data-stu-id="299d7-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span></span> |  
| [<span data-ttu-id="299d7-114">イベント</span><span class="sxs-lookup"><span data-stu-id="299d7-114">Events</span></span>](#events) | <span data-ttu-id="299d7-115">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span><span class="sxs-lookup"><span data-stu-id="299d7-115">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span></span> |  
| [<span data-ttu-id="299d7-116">型</span><span class="sxs-lookup"><span data-stu-id="299d7-116">Types</span></span>](#types) | <span data-ttu-id="299d7-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="299d7-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |  

## <a name="methods"></a><span data-ttu-id="299d7-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="299d7-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="299d7-119">[有効]</span><span class="sxs-lookup"><span data-stu-id="299d7-119">enable</span></span>  

<span data-ttu-id="299d7-120">イベントのレポートを有効 `executionContextsCleared` にする。</span><span class="sxs-lookup"><span data-stu-id="299d7-120">Enables reporting of the `executionContextsCleared` event.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="299d7-121">[無効]</span><span class="sxs-lookup"><span data-stu-id="299d7-121">disable</span></span>  

<span data-ttu-id="299d7-122">イベントのレポートを無効 `executionContextsCleared` にします。</span><span class="sxs-lookup"><span data-stu-id="299d7-122">Disables reporting of the `executionContextsCleared` event.</span></span>  

&nbsp;  

---  

### <a name="evaluate"></a><span data-ttu-id="299d7-123">評価する</span><span class="sxs-lookup"><span data-stu-id="299d7-123">evaluate</span></span>  

<span data-ttu-id="299d7-124">グローバル オブジェクトの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="299d7-124">Evaluates expression on global object.</span></span>  

| <span data-ttu-id="299d7-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="299d7-125">Parameters</span></span> | <span data-ttu-id="299d7-126">型</span><span class="sxs-lookup"><span data-stu-id="299d7-126">Type</span></span> | <span data-ttu-id="299d7-127">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-127">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-128">式</span><span class="sxs-lookup"><span data-stu-id="299d7-128">expression</span></span> | `string` | <span data-ttu-id="299d7-129">評価する式。</span><span class="sxs-lookup"><span data-stu-id="299d7-129">Expression to evaluate.</span></span> |  
| <span data-ttu-id="299d7-130">silent \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-130">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-131">評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="299d7-131">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="299d7-132">状態を上書 `setPauseOnException` きします。</span><span class="sxs-lookup"><span data-stu-id="299d7-132">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="299d7-133">contextId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-133">contextId \(optional\)</span></span> | [<span data-ttu-id="299d7-134">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="299d7-134">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="299d7-135">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="299d7-135">Specifies in which execution context to perform evaluation.</span></span>  <span data-ttu-id="299d7-136">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-136">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span> |  
| <span data-ttu-id="299d7-137">returnByValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-137">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-138">結果が値によって送信される JSON オブジェクトと予想されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="299d7-138">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  
| <span data-ttu-id="299d7-139">awaitPromise \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-139">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-140">結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="299d7-140">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="299d7-141">戻り値</span><span class="sxs-lookup"><span data-stu-id="299d7-141">Returns</span></span> | <span data-ttu-id="299d7-142">型</span><span class="sxs-lookup"><span data-stu-id="299d7-142">Type</span></span> | <span data-ttu-id="299d7-143">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-143">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-144">result</span><span class="sxs-lookup"><span data-stu-id="299d7-144">result</span></span> | [<span data-ttu-id="299d7-145">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-145">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-146">評価結果。</span><span class="sxs-lookup"><span data-stu-id="299d7-146">Evaluation result.</span></span> |  

---  

### <a name="callfunctionon"></a><span data-ttu-id="299d7-147">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="299d7-147">callFunctionOn</span></span>  

<span data-ttu-id="299d7-148">指定されたオブジェクトに対して指定された宣言を持つ関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="299d7-148">Calls function with given declaration on the given object.</span></span>  <span data-ttu-id="299d7-149">結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-149">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="299d7-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="299d7-150">Parameters</span></span> | <span data-ttu-id="299d7-151">型</span><span class="sxs-lookup"><span data-stu-id="299d7-151">Type</span></span> | <span data-ttu-id="299d7-152">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-152">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-153">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="299d7-153">functionDeclaration</span></span> | `string` | <span data-ttu-id="299d7-154">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="299d7-154">Declaration of the function to call.</span></span> |  
| <span data-ttu-id="299d7-155">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-155">objectId \(optional\)</span></span> | [<span data-ttu-id="299d7-156">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="299d7-156">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="299d7-157">関数を呼び出すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="299d7-157">Identifier of the object to call function on.</span></span>  <span data-ttu-id="299d7-158">または `objectId` 指定 `executionContextId` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-158">Either `objectId` or `executionContextId` should be specified.</span></span>  <span data-ttu-id="299d7-159">objectId は Runtime.evaluate() 関数の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-159">objectId must be from the Runtime.evaluate() function.</span></span> |  
| <span data-ttu-id="299d7-160">arguments \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-160">arguments \(optional\)</span></span> | [<span data-ttu-id="299d7-161">CallArgument[]</span><span class="sxs-lookup"><span data-stu-id="299d7-161">CallArgument[]</span></span>](#callargument) | <span data-ttu-id="299d7-162">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="299d7-162">Call arguments.</span></span>  <span data-ttu-id="299d7-163">すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-163">All call arguments must belong to the same JavaScript world as the target object.</span></span> |  
| <span data-ttu-id="299d7-164">silent \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-164">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-165">評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="299d7-165">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="299d7-166">状態を上書 `setPauseOnException` きします。</span><span class="sxs-lookup"><span data-stu-id="299d7-166">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="299d7-167">returnByValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-167">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-168">結果が値によって送信される JSON オブジェクトと予想されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="299d7-168">Whether the result is expected to be a JSON object which should be sent by value.</span></span> |  
| <span data-ttu-id="299d7-169">awaitPromise \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-169">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-170">結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="299d7-170">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="299d7-171">戻り値</span><span class="sxs-lookup"><span data-stu-id="299d7-171">Returns</span></span> | <span data-ttu-id="299d7-172">型</span><span class="sxs-lookup"><span data-stu-id="299d7-172">Type</span></span> | <span data-ttu-id="299d7-173">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-173">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-174">result</span><span class="sxs-lookup"><span data-stu-id="299d7-174">result</span></span> | [<span data-ttu-id="299d7-175">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-175">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-176">結果を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="299d7-176">Call result.</span></span> |  

---  

### <a name="getproperties"></a><span data-ttu-id="299d7-177">getProperties</span><span class="sxs-lookup"><span data-stu-id="299d7-177">getProperties</span></span>  

<span data-ttu-id="299d7-178">指定したオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="299d7-178">Returns properties of a given object.</span></span>  <span data-ttu-id="299d7-179">結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-179">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="299d7-180">パラメーター</span><span class="sxs-lookup"><span data-stu-id="299d7-180">Parameters</span></span> | <span data-ttu-id="299d7-181">型</span><span class="sxs-lookup"><span data-stu-id="299d7-181">Type</span></span> | <span data-ttu-id="299d7-182">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-182">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-183">objectId</span><span class="sxs-lookup"><span data-stu-id="299d7-183">objectId</span></span> | [<span data-ttu-id="299d7-184">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="299d7-184">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="299d7-185">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="299d7-185">Identifier of the object to return properties for.</span></span>  `objectId` <span data-ttu-id="299d7-186">関数からである必要 `Debugger.evaluateOnCallFrame()` があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-186">must be from the `Debugger.evaluateOnCallFrame()` function.</span></span> |  
| <span data-ttu-id="299d7-187">ownProperties \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-187">ownProperties \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-188">If `true` は、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="299d7-188">If `true`, returns properties belonging only to the element itself, not to its prototype chain.</span></span> |  
| <span data-ttu-id="299d7-189">accessorPropertiesOnly \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-189">accessorPropertiesOnly \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-190">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="299d7-190">**Experimental**.</span></span>  <span data-ttu-id="299d7-191">場合 `true` は、アクセサー プロパティ \(getter/setter\) のみを返します。内部プロパティも返されません。</span><span class="sxs-lookup"><span data-stu-id="299d7-191">If `true`, returns accessor properties \(with getter/setter\) only; internal properties are not returned either.</span></span> |  

| <span data-ttu-id="299d7-192">戻り値</span><span class="sxs-lookup"><span data-stu-id="299d7-192">Returns</span></span> | <span data-ttu-id="299d7-193">型</span><span class="sxs-lookup"><span data-stu-id="299d7-193">Type</span></span> | <span data-ttu-id="299d7-194">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-194">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-195">result</span><span class="sxs-lookup"><span data-stu-id="299d7-195">result</span></span> | [<span data-ttu-id="299d7-196">PropertyDescriptor[]</span><span class="sxs-lookup"><span data-stu-id="299d7-196">PropertyDescriptor[]</span></span>](#propertydescriptor) | <span data-ttu-id="299d7-197">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="299d7-197">Object properties.</span></span> |  

---  

## <a name="events"></a><span data-ttu-id="299d7-198">イベント</span><span class="sxs-lookup"><span data-stu-id="299d7-198">Events</span></span>  

### <a name="executioncontextscleared"></a><span data-ttu-id="299d7-199">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="299d7-199">executionContextsCleared</span></span>  

<span data-ttu-id="299d7-200">ブラウザーですべての executionContexts がクリアされた場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-200">Issued when all executionContexts were cleared in browser.</span></span>  

&nbsp;  

---  

### <a name="exceptionthrown"></a><span data-ttu-id="299d7-201">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="299d7-201">exceptionThrown</span></span>  

<span data-ttu-id="299d7-202">例外がスローされ、処理されない場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="299d7-202">Issued when exception was thrown and unhandled.</span></span>  

| <span data-ttu-id="299d7-203">パラメーター</span><span class="sxs-lookup"><span data-stu-id="299d7-203">Parameters</span></span> | <span data-ttu-id="299d7-204">型</span><span class="sxs-lookup"><span data-stu-id="299d7-204">Type</span></span> | <span data-ttu-id="299d7-205">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-205">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-206">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="299d7-206">timestamp</span></span> | [<span data-ttu-id="299d7-207">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="299d7-207">Timestamp</span></span>](#timestamp) | <span data-ttu-id="299d7-208">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="299d7-208">Timestamp of the exception.</span></span> |  
| <span data-ttu-id="299d7-209">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="299d7-209">exceptionDetails</span></span> | [<span data-ttu-id="299d7-210">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="299d7-210">ExceptionDetails</span></span>](#exceptiondetails) | &nbsp; |  

---  

## <a name="types"></a><span data-ttu-id="299d7-211">型</span><span class="sxs-lookup"><span data-stu-id="299d7-211">Types</span></span>  

### <a name="scriptid-string"></a><span data-ttu-id="299d7-212">ScriptId 文字列</span><span class="sxs-lookup"><span data-stu-id="299d7-212">ScriptId string</span></span>  

<a name="scriptid"></a>  

<span data-ttu-id="299d7-213">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="299d7-213">Unique script identifier.</span></span>  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a><span data-ttu-id="299d7-214">RemoteObjectId 文字列</span><span class="sxs-lookup"><span data-stu-id="299d7-214">RemoteObjectId string</span></span>  

<a name="remoteobjectid"></a>  

<span data-ttu-id="299d7-215">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="299d7-215">Unique object identifier.</span></span>  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a><span data-ttu-id="299d7-216">UnserializableValue 文字列</span><span class="sxs-lookup"><span data-stu-id="299d7-216">UnserializableValue string</span></span>  

<a name="unserializablevalue"></a>  

<span data-ttu-id="299d7-217">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="299d7-217">Primitive value which cannot be JSON-stringified.</span></span>  

##### <a name="allowed-values"></a><span data-ttu-id="299d7-218">許可される値</span><span class="sxs-lookup"><span data-stu-id="299d7-218">Allowed Values</span></span>  

`Infinity`<span data-ttu-id="299d7-219">, `NaN`, `-Infinity`,</span><span class="sxs-lookup"><span data-stu-id="299d7-219">, `NaN`, `-Infinity`,</span></span> `-0`  

---  

### <a name="remoteobject-object"></a><span data-ttu-id="299d7-220">RemoteObject オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-220">RemoteObject object</span></span>  

<a name="remoteobject"></a>  

<span data-ttu-id="299d7-221">元の JavaScript オブジェクトを参照するミラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="299d7-221">Mirror object referencing original JavaScript object.</span></span>  

| <span data-ttu-id="299d7-222">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-222">Properties</span></span> | <span data-ttu-id="299d7-223">型</span><span class="sxs-lookup"><span data-stu-id="299d7-223">Type</span></span> | <span data-ttu-id="299d7-224">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-224">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-225">型</span><span class="sxs-lookup"><span data-stu-id="299d7-225">type</span></span> | `string` | <span data-ttu-id="299d7-226">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="299d7-226">Object type.</span></span>  <span data-ttu-id="299d7-227">使用できる値: `object` `function` `undefined` 、、、、、、、、 `string` `number` `boolean`</span><span class="sxs-lookup"><span data-stu-id="299d7-227">Allowed values:  `object`, `function`, `undefined`, `string`, `number`, `boolean`, and</span></span> `symbol` |  
| <span data-ttu-id="299d7-228">サブタイプ \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-228">subtype \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-229">オブジェクトのサブタイプ ヒント。</span><span class="sxs-lookup"><span data-stu-id="299d7-229">Object subtype hint.</span></span>  <span data-ttu-id="299d7-230">型の値 `object` にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="299d7-230">Specified for `object` type values only.</span></span>  <span data-ttu-id="299d7-231">使用できる値:  `null` `error` 、、および</span><span class="sxs-lookup"><span data-stu-id="299d7-231">Allowed values:  `null`, `error`, and</span></span> `promise` |  
| <span data-ttu-id="299d7-232">className \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-232">className \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-233">オブジェクト クラス \(constructor\) 名。</span><span class="sxs-lookup"><span data-stu-id="299d7-233">Object class \(constructor\) name.</span></span>  <span data-ttu-id="299d7-234">型の値 `object` にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="299d7-234">Specified for `object` type values only.</span></span> |  
| <span data-ttu-id="299d7-235">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-235">value \(optional\)</span></span> | `any` | <span data-ttu-id="299d7-236">プリミティブ値または JSON 値の場合のリモート オブジェクト値 \(要求された場合\)。</span><span class="sxs-lookup"><span data-stu-id="299d7-236">Remote object value in case of primitive values or JSON values \(if it was requested\).</span></span> |  
| <span data-ttu-id="299d7-237">unserializableValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-237">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="299d7-238">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="299d7-238">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="299d7-239">JSON 文字列化できないプリミティブ値は持たれていますが `value` 、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="299d7-239">Primitive value which can not be JSON-stringified does not have `value`, but gets this property.</span></span> |  
| <span data-ttu-id="299d7-240">description \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-240">description \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-241">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="299d7-241">String representation of the object.</span></span> |  
| <span data-ttu-id="299d7-242">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-242">objectId \(optional\)</span></span> | [<span data-ttu-id="299d7-243">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="299d7-243">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="299d7-244">一意のオブジェクト識別子 \(非プリミティブ値\)。</span><span class="sxs-lookup"><span data-stu-id="299d7-244">Unique object identifier \(for non-primitive values\).</span></span> |  
| <span data-ttu-id="299d7-245">msDebuggerPropertyId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-245">msDebuggerPropertyId \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-246">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="299d7-246">**Experimental**.</span></span>  <span data-ttu-id="299d7-247">Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="299d7-247">Microsoft:  The associated debugger property ID for this object.</span></span> |  

---  

### <a name="propertydescriptor-object"></a><span data-ttu-id="299d7-248">PropertyDescriptor オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-248">PropertyDescriptor object</span></span>  

<a name="propertydescriptor"></a>  

<span data-ttu-id="299d7-249">オブジェクト プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="299d7-249">Object property descriptor.</span></span>  

| <span data-ttu-id="299d7-250">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-250">Properties</span></span> | <span data-ttu-id="299d7-251">型</span><span class="sxs-lookup"><span data-stu-id="299d7-251">Type</span></span> | <span data-ttu-id="299d7-252">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-252">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-253">name</span><span class="sxs-lookup"><span data-stu-id="299d7-253">name</span></span> | `string` | <span data-ttu-id="299d7-254">プロパティ名またはシンボルの説明。</span><span class="sxs-lookup"><span data-stu-id="299d7-254">Property name or symbol description.</span></span> |  
| <span data-ttu-id="299d7-255">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-255">value \(optional\)</span></span> | [<span data-ttu-id="299d7-256">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-256">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-257">プロパティに関連付けられている値。</span><span class="sxs-lookup"><span data-stu-id="299d7-257">The value associated with the property.</span></span> |  
| <span data-ttu-id="299d7-258">書き込み可能 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-258">writable \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="299d7-259">プロパティに関連付けられている値が変更される場合 \(データ記述子のみ\)。</span><span class="sxs-lookup"><span data-stu-id="299d7-259">if the value associated with the property may be changed \(data descriptors only\).</span></span> |  
| <span data-ttu-id="299d7-260">get \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-260">get \(optional\)</span></span> | [<span data-ttu-id="299d7-261">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-261">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-262">プロパティの getter として機能する関数、または `undefined` getter \(アクセサー記述子のみ\) がない場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-262">A function which serves as a getter for the property, or `undefined` if there is no getter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="299d7-263">set \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-263">set \(optional\)</span></span> | [<span data-ttu-id="299d7-264">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-264">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-265">プロパティのセッターとして機能する関数、または `undefined` setter \(アクセサー記述子のみ\) がない場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-265">A function which serves as a setter for the property, or `undefined` if there is no setter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="299d7-266">構成可能</span><span class="sxs-lookup"><span data-stu-id="299d7-266">configurable</span></span> | `boolean` | `True` <span data-ttu-id="299d7-267">このプロパティ記述子の種類が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-267">if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span> |  
| <span data-ttu-id="299d7-268">列挙可能</span><span class="sxs-lookup"><span data-stu-id="299d7-268">enumerable</span></span> | `boolean` | `True` <span data-ttu-id="299d7-269">このプロパティが対応するオブジェクトのプロパティの列挙中に表示される場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-269">if this property shows up during enumeration of the properties on the corresponding object.</span></span> |  
| <span data-ttu-id="299d7-270">wasThrown \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-270">wasThrown \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="299d7-271">評価中に結果がスローされた場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-271">if the result was thrown during the evaluation.</span></span> |  
| <span data-ttu-id="299d7-272">isOwn \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-272">isOwn \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="299d7-273">プロパティがオブジェクトに対して所有されている場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-273">if the property is owned for the object.</span></span> |  
| <span data-ttu-id="299d7-274">msReturnValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-274">msReturnValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="299d7-275">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="299d7-275">**Experimental**.</span></span>  <span data-ttu-id="299d7-276">Microsoft:  `True` プロパティが戻り値の場合。</span><span class="sxs-lookup"><span data-stu-id="299d7-276">Microsoft:  `True` if the property is a return value.</span></span> |  
| <span data-ttu-id="299d7-277">symbol \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-277">symbol \(optional\)</span></span> | [<span data-ttu-id="299d7-278">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-278">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-279">プロパティが型の場合は、プロパティ シンボル `symbol` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="299d7-279">Property symbol object, if the property is of the `symbol` type.</span></span> |  

---  

### <a name="callargument-object"></a><span data-ttu-id="299d7-280">CallArgument オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-280">CallArgument object</span></span>  

<a name="callargument"></a>  

<span data-ttu-id="299d7-281">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="299d7-281">Represents function call argument.</span></span>  <span data-ttu-id="299d7-282">リモート オブジェクト `value` ID、非erializable プリミティブ値、または \(for undefined\) のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-282">Either remote object ID `value`, unserializable primitive value or neither of \(for undefined\) them should be specified.</span></span>  

| <span data-ttu-id="299d7-283">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-283">Properties</span></span> | <span data-ttu-id="299d7-284">型</span><span class="sxs-lookup"><span data-stu-id="299d7-284">Type</span></span> | <span data-ttu-id="299d7-285">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-285">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-286">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-286">value \(optional\)</span></span> | `any` | <span data-ttu-id="299d7-287">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="299d7-287">Primitive value or serializable javascript object.</span></span> |  
| <span data-ttu-id="299d7-288">unserializableValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-288">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="299d7-289">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="299d7-289">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="299d7-290">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="299d7-290">Primitive value which can not be JSON-stringified.</span></span> |  
| <span data-ttu-id="299d7-291">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-291">objectId \(optional\)</span></span> | [<span data-ttu-id="299d7-292">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="299d7-292">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="299d7-293">リモート オブジェクト ハンドル。</span><span class="sxs-lookup"><span data-stu-id="299d7-293">Remote object handle.</span></span> |  

---  

### <a name="executioncontextid-integer"></a><span data-ttu-id="299d7-294">ExecutionContextId 整数</span><span class="sxs-lookup"><span data-stu-id="299d7-294">ExecutionContextId integer</span></span>  

<a name="executioncontextid"></a>  

<span data-ttu-id="299d7-295">実行コンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="299d7-295">ID of an execution context.</span></span>  

&nbsp;  

---  

### <a name="exceptiondetails-object"></a><span data-ttu-id="299d7-296">ExceptionDetails オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-296">ExceptionDetails object</span></span>  

<a name="exceptiondetails"></a>  

<span data-ttu-id="299d7-297">スクリプトのコンパイルまたは実行中にスローされた例外 \(または error\) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="299d7-297">Detailed information about exception \(or error\) that was thrown during script compilation or execution.</span></span>  

| <span data-ttu-id="299d7-298">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-298">Properties</span></span> | <span data-ttu-id="299d7-299">型</span><span class="sxs-lookup"><span data-stu-id="299d7-299">Type</span></span> | <span data-ttu-id="299d7-300">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-300">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-301">exceptionId</span><span class="sxs-lookup"><span data-stu-id="299d7-301">exceptionId</span></span> | `integer` | <span data-ttu-id="299d7-302">例外 ID。</span><span class="sxs-lookup"><span data-stu-id="299d7-302">Exception ID.</span></span> |  
| <span data-ttu-id="299d7-303">テキスト</span><span class="sxs-lookup"><span data-stu-id="299d7-303">text</span></span> | `string` | <span data-ttu-id="299d7-304">使用可能な場合は例外オブジェクトと共に使用する必要がある例外テキスト。</span><span class="sxs-lookup"><span data-stu-id="299d7-304">Exception text, which should be used together with exception object when available.</span></span> |  
| <span data-ttu-id="299d7-305">lineNumber</span><span class="sxs-lookup"><span data-stu-id="299d7-305">lineNumber</span></span> | `integer` | <span data-ttu-id="299d7-306">例外の場所 \(0 ベース\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="299d7-306">Line number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="299d7-307">columnNumber</span><span class="sxs-lookup"><span data-stu-id="299d7-307">columnNumber</span></span> | `integer` | <span data-ttu-id="299d7-308">例外の場所 \(0 ベース\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="299d7-308">Column number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="299d7-309">scriptId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-309">scriptId \(optional\)</span></span> | [<span data-ttu-id="299d7-310">ScriptId</span><span class="sxs-lookup"><span data-stu-id="299d7-310">ScriptId</span></span>](#scriptid) | <span data-ttu-id="299d7-311">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="299d7-311">Script ID of the exception location.</span></span> |  
| <span data-ttu-id="299d7-312">url \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-312">url \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-313">スクリプトが報告されていないときに使用する例外の場所の URL。</span><span class="sxs-lookup"><span data-stu-id="299d7-313">URL of the exception location, to be used when the script was not reported.</span></span> |  
| <span data-ttu-id="299d7-314">stackTrace \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-314">stackTrace \(optional\)</span></span> | [<span data-ttu-id="299d7-315">StackTrace</span><span class="sxs-lookup"><span data-stu-id="299d7-315">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="299d7-316">JavaScript スタック トレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="299d7-316">JavaScript stack trace if available.</span></span> |  
| <span data-ttu-id="299d7-317">例外 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-317">exception \(optional\)</span></span> | [<span data-ttu-id="299d7-318">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="299d7-318">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="299d7-319">例外オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="299d7-319">Exception object if available.</span></span> |  
| <span data-ttu-id="299d7-320">executionContextId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-320">executionContextId \(optional\)</span></span> | [<span data-ttu-id="299d7-321">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="299d7-321">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="299d7-322">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="299d7-322">Identifier of the context where exception happened.</span></span> |  

---  

### <a name="timestamp-integer"></a><span data-ttu-id="299d7-323">タイムスタンプの整数</span><span class="sxs-lookup"><span data-stu-id="299d7-323">Timestamp integer</span></span>  

<a name="timestamp"></a>  

<span data-ttu-id="299d7-324">エポックからのミリ秒単位。</span><span class="sxs-lookup"><span data-stu-id="299d7-324">Number of milliseconds since epoch.</span></span>  

&nbsp;  

---  

### <a name="callframe-object"></a><span data-ttu-id="299d7-325">CallFrame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-325">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="299d7-326">ランタイム エラーとアサーションのスタック エントリ。</span><span class="sxs-lookup"><span data-stu-id="299d7-326">Stack entry for runtime errors and assertions.</span></span>  

| <span data-ttu-id="299d7-327">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-327">Properties</span></span> | <span data-ttu-id="299d7-328">型</span><span class="sxs-lookup"><span data-stu-id="299d7-328">Type</span></span> | <span data-ttu-id="299d7-329">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-329">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-330">functionName</span><span class="sxs-lookup"><span data-stu-id="299d7-330">functionName</span></span> | `string` | <span data-ttu-id="299d7-331">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="299d7-331">JavaScript function name.</span></span> |  
| <span data-ttu-id="299d7-332">scriptId</span><span class="sxs-lookup"><span data-stu-id="299d7-332">scriptId</span></span> | [<span data-ttu-id="299d7-333">ScriptId</span><span class="sxs-lookup"><span data-stu-id="299d7-333">ScriptId</span></span>](#scriptid) | <span data-ttu-id="299d7-334">JavaScript スクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="299d7-334">JavaScript script ID.</span></span> |  
| <span data-ttu-id="299d7-335">url</span><span class="sxs-lookup"><span data-stu-id="299d7-335">url</span></span> | `string` | <span data-ttu-id="299d7-336">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="299d7-336">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="299d7-337">lineNumber</span><span class="sxs-lookup"><span data-stu-id="299d7-337">lineNumber</span></span> | `integer` | <span data-ttu-id="299d7-338">JavaScript スクリプト行番号 \(0-based\)。</span><span class="sxs-lookup"><span data-stu-id="299d7-338">JavaScript script line number \(0-based\).</span></span> |  
| <span data-ttu-id="299d7-339">columnNumber</span><span class="sxs-lookup"><span data-stu-id="299d7-339">columnNumber</span></span> | `integer` | <span data-ttu-id="299d7-340">JavaScript スクリプト列番号 \(0-based\)。</span><span class="sxs-lookup"><span data-stu-id="299d7-340">JavaScript script column number \(0-based\).</span></span> |  

---  

### <a name="stacktrace-object"></a><span data-ttu-id="299d7-341">StackTrace オブジェクト</span><span class="sxs-lookup"><span data-stu-id="299d7-341">StackTrace object</span></span>  

<a name="stacktrace"></a>  

<span data-ttu-id="299d7-342">アサーションまたはエラー メッセージの呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="299d7-342">Call frames for assertions or error messages.</span></span>  

| <span data-ttu-id="299d7-343">プロパティ</span><span class="sxs-lookup"><span data-stu-id="299d7-343">Properties</span></span> | <span data-ttu-id="299d7-344">型</span><span class="sxs-lookup"><span data-stu-id="299d7-344">Type</span></span> | <span data-ttu-id="299d7-345">詳細</span><span class="sxs-lookup"><span data-stu-id="299d7-345">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="299d7-346">description \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-346">description \(optional\)</span></span> | `string` | <span data-ttu-id="299d7-347">このスタック トレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="299d7-347">String label of this stack trace.</span></span>  <span data-ttu-id="299d7-348">非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="299d7-348">For async traces this may be a name of the function that initiated the async call.</span></span> |  
| <span data-ttu-id="299d7-349">callFrames</span><span class="sxs-lookup"><span data-stu-id="299d7-349">callFrames</span></span> | [<span data-ttu-id="299d7-350">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="299d7-350">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="299d7-351">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="299d7-351">JavaScript function name.</span></span> |  
| <span data-ttu-id="299d7-352">parent \(optional\)</span><span class="sxs-lookup"><span data-stu-id="299d7-352">parent \(optional\)</span></span> | [<span data-ttu-id="299d7-353">StackTrace</span><span class="sxs-lookup"><span data-stu-id="299d7-353">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="299d7-354">このスタックの前に含まれる非同期 JavaScript スタック トレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="299d7-354">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span> |  

---  
