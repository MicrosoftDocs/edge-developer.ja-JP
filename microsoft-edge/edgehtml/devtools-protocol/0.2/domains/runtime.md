---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: afc79a17c5002f60806872a9add57f518ff6cb45
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398141"
---
# <a name="runtime-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="19998-106">ランタイム ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="19998-106">Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="19998-107">ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="19998-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="19998-108">評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="19998-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="19998-109">元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="19998-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>  

| <span data-ttu-id="19998-110">分類</span><span class="sxs-lookup"><span data-stu-id="19998-110">Classification</span></span> | <span data-ttu-id="19998-111">Members</span><span class="sxs-lookup"><span data-stu-id="19998-111">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="19998-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="19998-112">Methods</span></span>**](#methods) | <span data-ttu-id="19998-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span><span class="sxs-lookup"><span data-stu-id="19998-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |  
| [**<span data-ttu-id="19998-114">イベント</span><span class="sxs-lookup"><span data-stu-id="19998-114">Events</span></span>**](#events) | <span data-ttu-id="19998-115">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="19998-115">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |  
| [**<span data-ttu-id="19998-116">型</span><span class="sxs-lookup"><span data-stu-id="19998-116">Types</span></span>**](#types) | <span data-ttu-id="19998-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), ExecutionContextId , [ExecutionContextDescription , ExceptionDetails](#executioncontextdescription), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace) [](#executioncontextid) [](#exceptiondetails)</span><span class="sxs-lookup"><span data-stu-id="19998-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |  

## <a name="methods"></a><span data-ttu-id="19998-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="19998-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="19998-119">[有効]</span><span class="sxs-lookup"><span data-stu-id="19998-119">enable</span></span>  

<span data-ttu-id="19998-120">、、およびイベント `executionContextCreated` `executionContextDestroyed` のレポートを `executionContextsCleared` 有効にします。</span><span class="sxs-lookup"><span data-stu-id="19998-120">Enables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.</span></span>  <span data-ttu-id="19998-121">レポートが有効になると、イベント `executionContextCreated` は既存の実行コンテキストごとに直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="19998-121">When the reporting gets enabled the `executionContextCreated` event will be sent immediately for each existing execution context.</span></span>  

---  

### <a name="disable"></a><span data-ttu-id="19998-122">[無効]</span><span class="sxs-lookup"><span data-stu-id="19998-122">disable</span></span>  

<span data-ttu-id="19998-123">、およびイベントの `executionContextCreated` レポート `executionContextDestroyed` を `executionContextsCleared` 無効にします。</span><span class="sxs-lookup"><span data-stu-id="19998-123">Disables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.</span></span>  

---  

### <a name="evaluate"></a><span data-ttu-id="19998-124">評価する</span><span class="sxs-lookup"><span data-stu-id="19998-124">evaluate</span></span>  

<span data-ttu-id="19998-125">グローバル オブジェクトの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="19998-125">Evaluates expression on global object.</span></span>  

| <span data-ttu-id="19998-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-126">Parameters</span></span> | <span data-ttu-id="19998-127">型</span><span class="sxs-lookup"><span data-stu-id="19998-127">Type</span></span> | <span data-ttu-id="19998-128">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-128">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-129">式</span><span class="sxs-lookup"><span data-stu-id="19998-129">expression</span></span> | `string` | <span data-ttu-id="19998-130">評価する式。</span><span class="sxs-lookup"><span data-stu-id="19998-130">Expression to evaluate.</span></span> |  
| <span data-ttu-id="19998-131">includeCommandLineAPI \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-131">includeCommandLineAPI \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-132">評価中にコマンド ライン API を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="19998-132">Determines whether Command Line API should be available during the evaluation.</span></span> |  
| <span data-ttu-id="19998-133">objectGroup \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-133">objectGroup \(optional\)</span></span> | `string` | <span data-ttu-id="19998-134">複数のオブジェクトを解放するために使用できるシンボリック グループ名。</span><span class="sxs-lookup"><span data-stu-id="19998-134">Symbolic group name that can be used to release multiple objects.</span></span> |  
| <span data-ttu-id="19998-135">silent \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-135">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-136">評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="19998-136">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="19998-137">状態を上書 `setPauseOnException` きします。</span><span class="sxs-lookup"><span data-stu-id="19998-137">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="19998-138">contextId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-138">contextId \(optional\)</span></span> | [<span data-ttu-id="19998-139">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-139">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-140">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="19998-140">Specifies in which execution context to perform evaluation.</span></span>  <span data-ttu-id="19998-141">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="19998-141">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span> |  
| <span data-ttu-id="19998-142">returnByValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-142">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-143">結果が値によって送信される JSON オブジェクトと予想されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="19998-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  
| <span data-ttu-id="19998-144">awaitPromise \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-144">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-145">結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="19998-145">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="19998-146">戻り値</span><span class="sxs-lookup"><span data-stu-id="19998-146">Returns</span></span> | <span data-ttu-id="19998-147">型</span><span class="sxs-lookup"><span data-stu-id="19998-147">Type</span></span> | <span data-ttu-id="19998-148">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-148">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-149">result</span><span class="sxs-lookup"><span data-stu-id="19998-149">result</span></span> | [<span data-ttu-id="19998-150">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-150">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-151">評価結果。</span><span class="sxs-lookup"><span data-stu-id="19998-151">Evaluation result.</span></span> |  

---  

### <a name="callfunctionon"></a><span data-ttu-id="19998-152">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="19998-152">callFunctionOn</span></span>  

<span data-ttu-id="19998-153">指定されたオブジェクトに対して指定された宣言を持つ関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19998-153">Calls function with given declaration on the given object.</span></span>  <span data-ttu-id="19998-154">結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="19998-154">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="19998-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-155">Parameters</span></span> | <span data-ttu-id="19998-156">型</span><span class="sxs-lookup"><span data-stu-id="19998-156">Type</span></span> | <span data-ttu-id="19998-157">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-158">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="19998-158">functionDeclaration</span></span> | `string` | <span data-ttu-id="19998-159">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="19998-159">Declaration of the function to call.</span></span> |  
| <span data-ttu-id="19998-160">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-160">objectId \(optional\)</span></span> | [<span data-ttu-id="19998-161">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-161">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="19998-162">関数を呼び出すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-162">Identifier of the object to call function on.</span></span>  <span data-ttu-id="19998-163">または `objectId` 指定 `executionContextId` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19998-163">Either `objectId` or `executionContextId` should be specified.</span></span>  `objectId` <span data-ttu-id="19998-164">関数からである必要 `Runtime.evaluate()` があります。</span><span class="sxs-lookup"><span data-stu-id="19998-164">must be from the `Runtime.evaluate()` function.</span></span> |  
| <span data-ttu-id="19998-165">arguments \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-165">arguments \(optional\)</span></span> | [<span data-ttu-id="19998-166">CallArgument[]</span><span class="sxs-lookup"><span data-stu-id="19998-166">CallArgument[]</span></span>](#callargument) | <span data-ttu-id="19998-167">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19998-167">Call arguments.</span></span>  <span data-ttu-id="19998-168">すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="19998-168">All call arguments must belong to the same JavaScript world as the target object.</span></span> |  
| <span data-ttu-id="19998-169">boolean \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-169">boolean \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-170">評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="19998-170">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="19998-171">状態を上書 `setPauseOnException` きします。</span><span class="sxs-lookup"><span data-stu-id="19998-171">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="19998-172">returnByValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-172">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-173">結果が値によって送信される JSON オブジェクトと予想されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="19998-173">Whether the result is expected to be a JSON object which should be sent by value.</span></span> |  
| <span data-ttu-id="19998-174">awaitPromise \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-174">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-175">結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="19998-175">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  
| <span data-ttu-id="19998-176">executionContextId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-176">executionContextId \(optional\)</span></span> | [<span data-ttu-id="19998-177">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-177">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-178">関数の呼び出しに使用するグローバル オブジェクトの実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="19998-178">Specifies execution context which global object will be used to call function on.</span></span>  <span data-ttu-id="19998-179">いずれも</span><span class="sxs-lookup"><span data-stu-id="19998-179">Either</span></span>
`executionContextId` <span data-ttu-id="19998-180">または `objectId` 指定する必要があります</span><span class="sxs-lookup"><span data-stu-id="19998-180">or `objectId` should be specified</span></span> |  
| <span data-ttu-id="19998-181">objectGroup \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-181">objectGroup \(optional\)</span></span> | `string` | <span data-ttu-id="19998-182">複数のオブジェクトを解放するために使用できるシンボリック グループ名。</span><span class="sxs-lookup"><span data-stu-id="19998-182">Symbolic group name that can be used to release multiple objects.</span></span>  <span data-ttu-id="19998-183">指定 `objectGroup` されていない場合は `objectId` 、オブジェクト `objectGroup` から継承されます。</span><span class="sxs-lookup"><span data-stu-id="19998-183">If `objectGroup` is not specified and `objectId` is, `objectGroup` will be inherited from object.</span></span> |  

| <span data-ttu-id="19998-184">戻り値</span><span class="sxs-lookup"><span data-stu-id="19998-184">Returns</span></span> | <span data-ttu-id="19998-185">型</span><span class="sxs-lookup"><span data-stu-id="19998-185">Type</span></span> | <span data-ttu-id="19998-186">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-186">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-187">result</span><span class="sxs-lookup"><span data-stu-id="19998-187">result</span></span> | [<span data-ttu-id="19998-188">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-188">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-189">結果を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19998-189">Call result.</span></span> |  

---  

### <a name="awaitpromise"></a><span data-ttu-id="19998-190">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="19998-190">awaitPromise</span></span>  

<span data-ttu-id="19998-191">指定された promise オブジェクト ID で約束するハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="19998-191">Add handler to promise with given promise object id.</span></span>  

| <span data-ttu-id="19998-192">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-192">Parameters</span></span> | <span data-ttu-id="19998-193">型</span><span class="sxs-lookup"><span data-stu-id="19998-193">Type</span></span> | <span data-ttu-id="19998-194">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-194">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-195">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-195">promiseObjectId</span></span> | [<span data-ttu-id="19998-196">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-196">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="19998-197">約束の識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-197">Identifier of the promise.</span></span> |  
| <span data-ttu-id="19998-198">returnByValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-198">returnByValue \(optional\)</span></span> | <span data-ttu-id="19998-199">ブール値</span><span class="sxs-lookup"><span data-stu-id="19998-199">boolean</span></span> | <span data-ttu-id="19998-200">結果が値によって送信される JSON オブジェクトと予想されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="19998-200">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  

| <span data-ttu-id="19998-201">戻り値</span><span class="sxs-lookup"><span data-stu-id="19998-201">Returns</span></span> | <span data-ttu-id="19998-202">型</span><span class="sxs-lookup"><span data-stu-id="19998-202">Type</span></span> | <span data-ttu-id="19998-203">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-204">result</span><span class="sxs-lookup"><span data-stu-id="19998-204">result</span></span> | [<span data-ttu-id="19998-205">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-205">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-206">Promise の結果。</span><span class="sxs-lookup"><span data-stu-id="19998-206">Promise result.</span></span>  <span data-ttu-id="19998-207">promise が拒否された場合、拒否された値が含まれる。</span><span class="sxs-lookup"><span data-stu-id="19998-207">Will contain rejected value if promise was rejected.</span></span> |  

---  

### <a name="getproperties"></a><span data-ttu-id="19998-208">getProperties</span><span class="sxs-lookup"><span data-stu-id="19998-208">getProperties</span></span>  

<span data-ttu-id="19998-209">指定したオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="19998-209">Returns properties of a given object.</span></span> <span data-ttu-id="19998-210">結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="19998-210">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="19998-211">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-211">Parameters</span></span> | <span data-ttu-id="19998-212">型</span><span class="sxs-lookup"><span data-stu-id="19998-212">Type</span></span> | <span data-ttu-id="19998-213">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-213">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-214">objectId</span><span class="sxs-lookup"><span data-stu-id="19998-214">objectId</span></span> | [<span data-ttu-id="19998-215">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-215">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="19998-216">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-216">Identifier of the object to return properties for.</span></span>  `objectId` <span data-ttu-id="19998-217">関数からである必要 `Debugger.evaluateOnCallFrame()` があります。</span><span class="sxs-lookup"><span data-stu-id="19998-217">must be from the `Debugger.evaluateOnCallFrame()` function.</span></span> |  
| <span data-ttu-id="19998-218">ownProperties \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-218">ownProperties \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-219">If `true` は、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="19998-219">If `true`, returns properties belonging only to the element itself, not to its prototype chain.</span></span> |  
| <span data-ttu-id="19998-220">accessorPropertiesOnly \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-220">accessorPropertiesOnly \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-221">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="19998-221">**Experimental**.</span></span>  <span data-ttu-id="19998-222">場合 `true` は、アクセサー プロパティ \(getter/setter\) のみを返します。内部プロパティも返されません。</span><span class="sxs-lookup"><span data-stu-id="19998-222">If `true`, returns accessor properties \(with getter/setter\) only; internal properties are not returned either.</span></span> |  

| <span data-ttu-id="19998-223">戻り値</span><span class="sxs-lookup"><span data-stu-id="19998-223">Returns</span></span> | <span data-ttu-id="19998-224">型</span><span class="sxs-lookup"><span data-stu-id="19998-224">Type</span></span> | <span data-ttu-id="19998-225">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-225">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-226">result</span><span class="sxs-lookup"><span data-stu-id="19998-226">result</span></span> | [<span data-ttu-id="19998-227">PropertyDescriptor[]</span><span class="sxs-lookup"><span data-stu-id="19998-227">PropertyDescriptor[]</span></span>](#propertydescriptor) | <span data-ttu-id="19998-228">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="19998-228">Object properties.</span></span> |  

---  

### <a name="globallexicalscopenames"></a><span data-ttu-id="19998-229">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="19998-229">globalLexicalScopeNames</span></span>  

<span data-ttu-id="19998-230">コンソール のグローバル スコープからすべての let 変数、const 変数、およびクラス変数を返します。</span><span class="sxs-lookup"><span data-stu-id="19998-230">Returns all let, const, and class variables from the console global scope.</span></span>  

| <span data-ttu-id="19998-231">戻り値</span><span class="sxs-lookup"><span data-stu-id="19998-231">Returns</span></span> | <span data-ttu-id="19998-232">型</span><span class="sxs-lookup"><span data-stu-id="19998-232">Type</span></span> | <span data-ttu-id="19998-233">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-233">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-234">名前</span><span class="sxs-lookup"><span data-stu-id="19998-234">names</span></span> | `string[]` | &nbsp; |  

---  

### <a name="releaseobject"></a><span data-ttu-id="19998-235">releaseObject</span><span class="sxs-lookup"><span data-stu-id="19998-235">releaseObject</span></span>  

<span data-ttu-id="19998-236">指定された ID を持つリモート オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="19998-236">Releases remote object with given ID.</span></span>  

| <span data-ttu-id="19998-237">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-237">Parameters</span></span> | <span data-ttu-id="19998-238">型</span><span class="sxs-lookup"><span data-stu-id="19998-238">Type</span></span> | <span data-ttu-id="19998-239">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-239">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-240">objectId</span><span class="sxs-lookup"><span data-stu-id="19998-240">objectId</span></span> | [<span data-ttu-id="19998-241">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-241">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="19998-242">解放するオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-242">Identifier of the object to release.</span></span> |  

---  

### <a name="releaseobjectgroup"></a><span data-ttu-id="19998-243">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="19998-243">releaseObjectGroup</span></span>  

<span data-ttu-id="19998-244">特定のグループに属しているすべてのリモート オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="19998-244">Releases all remote objects that belong to a given group.</span></span>  

| <span data-ttu-id="19998-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-245">Parameters</span></span> | <span data-ttu-id="19998-246">型</span><span class="sxs-lookup"><span data-stu-id="19998-246">Type</span></span> | <span data-ttu-id="19998-247">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-247">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-248">objectGroup</span><span class="sxs-lookup"><span data-stu-id="19998-248">objectGroup</span></span> | `string` | <span data-ttu-id="19998-249">シンボリック オブジェクト グループ名。</span><span class="sxs-lookup"><span data-stu-id="19998-249">Symbolic object group name.</span></span> |  

---  

### <a name="discardconsoleentries"></a><span data-ttu-id="19998-250">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="19998-250">discardConsoleEntries</span></span>  

<span data-ttu-id="19998-251">収集された例外とコンソール API 呼び出しを破棄します。</span><span class="sxs-lookup"><span data-stu-id="19998-251">Discards collected exceptions and console API calls.</span></span>  

---  

## <a name="events"></a><span data-ttu-id="19998-252">イベント</span><span class="sxs-lookup"><span data-stu-id="19998-252">Events</span></span>  

### <a name="executioncontextcreated"></a><span data-ttu-id="19998-253">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="19998-253">executionContextCreated</span></span>  

<span data-ttu-id="19998-254">新しい実行コンテキストが作成されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="19998-254">Issued when new execution context is created.</span></span>  

| <span data-ttu-id="19998-255">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-255">Parameters</span></span> | <span data-ttu-id="19998-256">型</span><span class="sxs-lookup"><span data-stu-id="19998-256">Type</span></span> | <span data-ttu-id="19998-257">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-257">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-258">context</span><span class="sxs-lookup"><span data-stu-id="19998-258">context</span></span> | [<span data-ttu-id="19998-259">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="19998-259">ExecutionContextDescription</span></span>](#executioncontextdescription) | <span data-ttu-id="19998-260">新しく作成された実行コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="19998-260">A newly created execution context.</span></span> |  

---  

### <a name="executioncontextdestroyed"></a><span data-ttu-id="19998-261">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="19998-261">executionContextDestroyed</span></span>  

<span data-ttu-id="19998-262">実行コンテキストが破棄されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="19998-262">Issued when execution context is destroyed.</span></span>  

| <span data-ttu-id="19998-263">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-263">Parameters</span></span> | <span data-ttu-id="19998-264">型</span><span class="sxs-lookup"><span data-stu-id="19998-264">Type</span></span> | <span data-ttu-id="19998-265">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-265">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-266">executionContextId</span></span> | [<span data-ttu-id="19998-267">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-267">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-268">破棄されたコンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="19998-268">ID of the destroyed context.</span></span> |  

---  

### <a name="executioncontextscleared"></a><span data-ttu-id="19998-269">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="19998-269">executionContextsCleared</span></span>  

<span data-ttu-id="19998-270">ブラウザーですべての executionContexts がクリアされた場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="19998-270">Issued when all executionContexts were cleared in browser.</span></span>  

&nbsp;  

---  

### <a name="exceptionthrown"></a><span data-ttu-id="19998-271">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="19998-271">exceptionThrown</span></span>  

<span data-ttu-id="19998-272">例外がスローされ、処理されない場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="19998-272">Issued when exception was thrown and unhandled.</span></span>  

| <span data-ttu-id="19998-273">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-273">Parameters</span></span> | <span data-ttu-id="19998-274">型</span><span class="sxs-lookup"><span data-stu-id="19998-274">Type</span></span> | <span data-ttu-id="19998-275">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-275">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-276">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="19998-276">timestamp</span></span> | [<span data-ttu-id="19998-277">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="19998-277">Timestamp</span></span>](#timestamp) | <span data-ttu-id="19998-278">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="19998-278">Timestamp of the exception.</span></span> |  
| <span data-ttu-id="19998-279">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="19998-279">exceptionDetails</span></span> | [<span data-ttu-id="19998-280">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="19998-280">ExceptionDetails</span></span>](#exceptiondetails) | &nbsp; |  

---  

### <a name="consoleapicalled"></a><span data-ttu-id="19998-281">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="19998-281">consoleAPICalled</span></span>  

| <span data-ttu-id="19998-282">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19998-282">Parameters</span></span> | <span data-ttu-id="19998-283">型</span><span class="sxs-lookup"><span data-stu-id="19998-283">Type</span></span> | <span data-ttu-id="19998-284">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-284">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-285">型</span><span class="sxs-lookup"><span data-stu-id="19998-285">type</span></span> | `string` | <span data-ttu-id="19998-286">呼び出しの種類。</span><span class="sxs-lookup"><span data-stu-id="19998-286">Type of the call.</span></span>  <span data-ttu-id="19998-287">使用できる値:  `log` , , , , `info` `warning` `error` `debug` `assert` `table` , `trace` `dir` , `dirxml` `clear` `select` `count` `countReset` `timeEnd` `timeStamp` `startGroup` `startGroupCollapsed` ,</span><span class="sxs-lookup"><span data-stu-id="19998-287">Allowed values:  `log`, `info`, `warning`, `error`, `debug`, `assert`, `table`, `trace`, `dir`, `dirxml`, `clear`, `select`, `count`, `countReset`, `timeEnd`, `timeStamp`, `startGroup`, `startGroupCollapsed`, and</span></span> `endGroup` |  
| <span data-ttu-id="19998-288">args</span><span class="sxs-lookup"><span data-stu-id="19998-288">args</span></span> | <span data-ttu-id="19998-289">[RemoteObject[]](#remoteobject</span><span class="sxs-lookup"><span data-stu-id="19998-289">[RemoteObject[]](#remoteobject</span></span> | <span data-ttu-id="19998-290">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19998-290">Call arguments.</span></span> |  
| <span data-ttu-id="19998-291">executionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-291">executionContextId</span></span> | [<span data-ttu-id="19998-292">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-292">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-293">コンソール呼び出しが行われたコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-293">Identifier of the context where console call was made.</span></span> |  
| <span data-ttu-id="19998-294">timestamp \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-294">timestamp \(optional\)</span></span> | [<span data-ttu-id="19998-295">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="19998-295">Timestamp</span></span>](#timestamp) | <span data-ttu-id="19998-296">タイムスタンプを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19998-296">Call timestamp.</span></span> |  
| <span data-ttu-id="19998-297">stackTrace \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-297">stackTrace \(optional\)</span></span> | [<span data-ttu-id="19998-298">StackTrace</span><span class="sxs-lookup"><span data-stu-id="19998-298">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="19998-299">使用可能な場合にキャプチャされるスタック トレース。</span><span class="sxs-lookup"><span data-stu-id="19998-299">Stack trace captured if available.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="19998-300">型</span><span class="sxs-lookup"><span data-stu-id="19998-300">Types</span></span>  

### <a name="scriptid-string"></a><span data-ttu-id="19998-301">ScriptId 文字列</span><span class="sxs-lookup"><span data-stu-id="19998-301">ScriptId string</span></span>  

<a name="scriptid"></a>

<span data-ttu-id="19998-302">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-302">Unique script identifier.</span></span>  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a><span data-ttu-id="19998-303">RemoteObjectId 文字列</span><span class="sxs-lookup"><span data-stu-id="19998-303">RemoteObjectId string</span></span>  

<a name="remoteobjectid"></a>

<span data-ttu-id="19998-304">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-304">Unique object identifier.</span></span>  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a><span data-ttu-id="19998-305">UnserializableValue 文字列</span><span class="sxs-lookup"><span data-stu-id="19998-305">UnserializableValue string</span></span>  

<a name="unserializablevalue"></a>  

<span data-ttu-id="19998-306">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="19998-306">Primitive value which cannot be JSON-stringified.</span></span>  

##### <a name="allowed-values"></a><span data-ttu-id="19998-307">許可される値</span><span class="sxs-lookup"><span data-stu-id="19998-307">Allowed Values</span></span>  

`Infinity`<span data-ttu-id="19998-308">, `NaN`, `-Infinity`,</span><span class="sxs-lookup"><span data-stu-id="19998-308">, `NaN`, `-Infinity`,</span></span> `-0`  

---  

### <a name="remoteobject-object"></a><span data-ttu-id="19998-309">RemoteObject オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-309">RemoteObject object</span></span>  

<a name="remoteobject"></a>  

<span data-ttu-id="19998-310">元の JavaScript オブジェクトを参照するミラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="19998-310">Mirror object referencing original JavaScript object.</span></span>  

| <span data-ttu-id="19998-311">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-311">Properties</span></span> | <span data-ttu-id="19998-312">型</span><span class="sxs-lookup"><span data-stu-id="19998-312">Type</span></span> | <span data-ttu-id="19998-313">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-313">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-314">型</span><span class="sxs-lookup"><span data-stu-id="19998-314">type</span></span> | `string` | <span data-ttu-id="19998-315">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="19998-315">Object type.</span></span>  <span data-ttu-id="19998-316">使用できる値: `object` `function` `undefined` 、、、、、、、、 `string` `number` `boolean`</span><span class="sxs-lookup"><span data-stu-id="19998-316">Allowed values:  `object`, `function`, `undefined`, `string`, `number`, `boolean`, and</span></span> `symbol` |  
| <span data-ttu-id="19998-317">サブタイプ \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-317">subtype \(optional\)</span></span> | `string` | <span data-ttu-id="19998-318">オブジェクトのサブタイプ ヒント。</span><span class="sxs-lookup"><span data-stu-id="19998-318">Object subtype hint.</span></span>  <span data-ttu-id="19998-319">型の値 `object` にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="19998-319">Specified for `object` type values only.</span></span>  <span data-ttu-id="19998-320">使用できる値:  `null` `error` `promise` 、、、および</span><span class="sxs-lookup"><span data-stu-id="19998-320">Allowed values:  `null`, `error`, `promise`, and</span></span> `node` |  
| <span data-ttu-id="19998-321">className \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-321">className \(optional\)</span></span> | `string` | <span data-ttu-id="19998-322">オブジェクト クラス \(constructor\) 名。</span><span class="sxs-lookup"><span data-stu-id="19998-322">Object class \(constructor\) name.</span></span>  <span data-ttu-id="19998-323">型の値 `object` にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="19998-323">Specified for `object` type values only.</span></span> |  
| <span data-ttu-id="19998-324">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-324">value \(optional\)</span></span> | `any` | <span data-ttu-id="19998-325">プリミティブ値または JSON 値の場合のリモート オブジェクト値 \(要求された場合\)。</span><span class="sxs-lookup"><span data-stu-id="19998-325">Remote object value in case of primitive values or JSON values \(if it was requested\).</span></span> |  
| <span data-ttu-id="19998-326">unserializableValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-326">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="19998-327">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="19998-327">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="19998-328">JSON 文字列化できないプリミティブ値は持たれていますが `value` 、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="19998-328">Primitive value which can not be JSON-stringified does not have `value`, but gets this property.</span></span> |  
| <span data-ttu-id="19998-329">description \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-329">description \(optional\)</span></span> | `string` | <span data-ttu-id="19998-330">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="19998-330">String representation of the object.</span></span> |  
| <span data-ttu-id="19998-331">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-331">objectId \(optional\)</span></span> | [<span data-ttu-id="19998-332">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="19998-332">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="19998-333">一意のオブジェクト識別子 \(非プリミティブ値\)。</span><span class="sxs-lookup"><span data-stu-id="19998-333">Unique object identifier \(for non-primitive values\).</span></span> |  
| <span data-ttu-id="19998-334">msDebuggerPropertyId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-334">msDebuggerPropertyId \(optional\)</span></span> | `string` | <span data-ttu-id="19998-335">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="19998-335">**Experimental**.</span></span>  <span data-ttu-id="19998-336">Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="19998-336">Microsoft:  The associated debugger property ID for this object.</span></span> |  

---  

### <a name="propertydescriptor-object"></a><span data-ttu-id="19998-337">PropertyDescriptor オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-337">PropertyDescriptor object</span></span>  

<a name="propertydescriptor"></a>  

<span data-ttu-id="19998-338">オブジェクト プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="19998-338">Object property descriptor.</span></span>  

| <span data-ttu-id="19998-339">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-339">Properties</span></span> | <span data-ttu-id="19998-340">型</span><span class="sxs-lookup"><span data-stu-id="19998-340">Type</span></span> | <span data-ttu-id="19998-341">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-341">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-342">name</span><span class="sxs-lookup"><span data-stu-id="19998-342">name</span></span> | `string` | <span data-ttu-id="19998-343">プロパティ名またはシンボルの説明。</span><span class="sxs-lookup"><span data-stu-id="19998-343">Property name or symbol description.</span></span> |  
| <span data-ttu-id="19998-344">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-344">value \(optional\)</span></span> | [<span data-ttu-id="19998-345">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-345">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-346">プロパティに関連付けられている値。</span><span class="sxs-lookup"><span data-stu-id="19998-346">The value associated with the property.</span></span> |  
| <span data-ttu-id="19998-347">書き込み可能 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-347">writable \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="19998-348">プロパティに関連付けられている値が変更される場合 \(データ記述子のみ\)。</span><span class="sxs-lookup"><span data-stu-id="19998-348">if the value associated with the property may be changed \(data descriptors only\).</span></span> |  
| <span data-ttu-id="19998-349">get \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-349">get \(optional\)</span></span> | [<span data-ttu-id="19998-350">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-350">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-351">プロパティの getter として機能する関数、または `undefined` getter \(アクセサー記述子のみ\) がない場合。</span><span class="sxs-lookup"><span data-stu-id="19998-351">A function which serves as a getter for the property, or `undefined` if there is no getter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="19998-352">set \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-352">set \(optional\)</span></span> | [<span data-ttu-id="19998-353">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-353">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-354">プロパティのセッターとして機能する関数、または `undefined` setter \(アクセサー記述子のみ\) がない場合。</span><span class="sxs-lookup"><span data-stu-id="19998-354">A function which serves as a setter for the property, or `undefined` if there is no setter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="19998-355">構成可能</span><span class="sxs-lookup"><span data-stu-id="19998-355">configurable</span></span> | `boolean` | `True` <span data-ttu-id="19998-356">このプロパティ記述子の種類が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合。</span><span class="sxs-lookup"><span data-stu-id="19998-356">if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span> |  
| <span data-ttu-id="19998-357">列挙可能</span><span class="sxs-lookup"><span data-stu-id="19998-357">enumerable</span></span> | `boolean` | `True` <span data-ttu-id="19998-358">このプロパティが対応するオブジェクトのプロパティの列挙中に表示される場合。</span><span class="sxs-lookup"><span data-stu-id="19998-358">if this property shows up during enumeration of the properties on the corresponding object.</span></span> |  
| <span data-ttu-id="19998-359">wasThrown \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-359">wasThrown \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="19998-360">評価中に結果がスローされた場合。</span><span class="sxs-lookup"><span data-stu-id="19998-360">if the result was thrown during the evaluation.</span></span> |  
| <span data-ttu-id="19998-361">isOwn \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-361">isOwn \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="19998-362">プロパティがオブジェクトに対して所有されている場合。</span><span class="sxs-lookup"><span data-stu-id="19998-362">if the property is owned for the object.</span></span> |  
| <span data-ttu-id="19998-363">msReturnValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-363">msReturnValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="19998-364">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="19998-364">**Experimental**.</span></span>  <span data-ttu-id="19998-365">Microsoft:  `True` プロパティが戻り値の場合。</span><span class="sxs-lookup"><span data-stu-id="19998-365">Microsoft:  `True` if the property is a return value.</span></span> |  
| <span data-ttu-id="19998-366">symbol \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-366">symbol \(optional\)</span></span> | [<span data-ttu-id="19998-367">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-367">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-368">プロパティが型の場合は、プロパティ シンボル `symbol` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="19998-368">Property symbol object, if the property is of the `symbol` type.</span></span> |  

---  

### <a name="callargument-object"></a><span data-ttu-id="19998-369">CallArgument オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-369">CallArgument object</span></span>  

<a name="callargument"></a>  

<span data-ttu-id="19998-370">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="19998-370">Represents function call argument.</span></span>  <span data-ttu-id="19998-371">リモート オブジェクト ID、プリミティブ、非データ化可能なプリミティブ値、または `objectId` `value` \(for undefined\) のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19998-371">Either remote object ID `objectId`, primitive `value`, unserializable primitive value, or neither of \(for undefined\) them should be specified.</span></span>  

| <span data-ttu-id="19998-372">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-372">Properties</span></span> | <span data-ttu-id="19998-373">型</span><span class="sxs-lookup"><span data-stu-id="19998-373">Type</span></span> | <span data-ttu-id="19998-374">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-374">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-375">value \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-375">value \(optional\)</span></span> | `any` | <span data-ttu-id="19998-376">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="19998-376">Primitive value or serializable javascript object.</span></span> |  
| <span data-ttu-id="19998-377">unserializableValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-377">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="19998-378">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="19998-378">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="19998-379">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="19998-379">Primitive value which can not be JSON-stringified.</span></span> |  
| <span data-ttu-id="19998-380">objectId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-380">objectId \(optional\)</span></span> | <span data-ttu-id="19998-381">[RemoteObjectId](#remoteobjectid)]</span><span class="sxs-lookup"><span data-stu-id="19998-381">[RemoteObjectId](#remoteobjectid)]</span></span> | <span data-ttu-id="19998-382">リモート オブジェクト ハンドル。</span><span class="sxs-lookup"><span data-stu-id="19998-382">Remote object handle.</span></span> |  

---  

### <a name="executioncontextid-integer"></a><span data-ttu-id="19998-383">ExecutionContextId 整数</span><span class="sxs-lookup"><span data-stu-id="19998-383">ExecutionContextId integer</span></span>  

<a name="executioncontextid"></a>  

<span data-ttu-id="19998-384">実行コンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="19998-384">ID of an execution context.</span></span>  

&nbsp;  

---  

### <a name="executioncontextdescription-object"></a><span data-ttu-id="19998-385">ExecutionContextDescription オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-385">ExecutionContextDescription object</span></span>  

<a name="executioncontextdescription"></a>  

<span data-ttu-id="19998-386">孤立した世界の説明。</span><span class="sxs-lookup"><span data-stu-id="19998-386">Description of an isolated world.</span></span>  

| <span data-ttu-id="19998-387">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-387">Properties</span></span> | <span data-ttu-id="19998-388">型</span><span class="sxs-lookup"><span data-stu-id="19998-388">Type</span></span> | <span data-ttu-id="19998-389">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-389">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-390">id</span><span class="sxs-lookup"><span data-stu-id="19998-390">id</span></span> | [<span data-ttu-id="19998-391">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-391">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-392">実行コンテキストの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="19998-392">Unique ID of the execution context.</span></span>  <span data-ttu-id="19998-393">これは、実行コンテキストを指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="19998-393">It can be used to specify in which execution context</span></span>
<span data-ttu-id="19998-394">スクリプトの評価を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19998-394">script evaluation should be performed.</span></span> |  
| <span data-ttu-id="19998-395">origin</span><span class="sxs-lookup"><span data-stu-id="19998-395">origin</span></span> | `string` | <span data-ttu-id="19998-396">実行コンテキストの起点。</span><span class="sxs-lookup"><span data-stu-id="19998-396">Execution context origin.</span></span> |  
| <span data-ttu-id="19998-397">name</span><span class="sxs-lookup"><span data-stu-id="19998-397">name</span></span> | `string` | <span data-ttu-id="19998-398">特定のコンテキストを記述する人間の読み取り可能な名前。</span><span class="sxs-lookup"><span data-stu-id="19998-398">Human readable name describing given context.</span></span> |  

---  

### <a name="exceptiondetails-object"></a><span data-ttu-id="19998-399">ExceptionDetails オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-399">ExceptionDetails object</span></span>  

<a name="exceptiondetails"></a>  

<span data-ttu-id="19998-400">スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="19998-400">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>  

| <span data-ttu-id="19998-401">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-401">Properties</span></span> | <span data-ttu-id="19998-402">型</span><span class="sxs-lookup"><span data-stu-id="19998-402">Type</span></span> | <span data-ttu-id="19998-403">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-403">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-404">exceptionId</span><span class="sxs-lookup"><span data-stu-id="19998-404">exceptionId</span></span> | `integer` | <span data-ttu-id="19998-405">例外 ID。</span><span class="sxs-lookup"><span data-stu-id="19998-405">Exception ID.</span></span> |  
| <span data-ttu-id="19998-406">テキスト</span><span class="sxs-lookup"><span data-stu-id="19998-406">text</span></span> | `string` | <span data-ttu-id="19998-407">使用可能な場合は例外オブジェクトと共に使用する必要がある例外テキスト。</span><span class="sxs-lookup"><span data-stu-id="19998-407">Exception text, which should be used together with exception object when available.</span></span> |  
| <span data-ttu-id="19998-408">lineNumber</span><span class="sxs-lookup"><span data-stu-id="19998-408">lineNumber</span></span> | `integer` | <span data-ttu-id="19998-409">例外の場所 \(0 ベース\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="19998-409">Line number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="19998-410">columnNumber</span><span class="sxs-lookup"><span data-stu-id="19998-410">columnNumber</span></span> | `integer` | <span data-ttu-id="19998-411">例外の場所 \(0 ベース\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="19998-411">Column number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="19998-412">scriptId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-412">scriptId \(optional\)</span></span> | [<span data-ttu-id="19998-413">ScriptId</span><span class="sxs-lookup"><span data-stu-id="19998-413">ScriptId</span></span>](#scriptid) | <span data-ttu-id="19998-414">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="19998-414">Script ID of the exception location.</span></span> |  
| <span data-ttu-id="19998-415">url \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-415">url \(optional\)</span></span> | `string` | <span data-ttu-id="19998-416">スクリプトが報告されていないときに使用する例外の場所の URL。</span><span class="sxs-lookup"><span data-stu-id="19998-416">URL of the exception location, to be used when the script was not reported.</span></span> |  
| <span data-ttu-id="19998-417">stackTrace \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-417">stackTrace \(optional\)</span></span> | [<span data-ttu-id="19998-418">StackTrace</span><span class="sxs-lookup"><span data-stu-id="19998-418">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="19998-419">JavaScript スタック トレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="19998-419">JavaScript stack trace if available.</span></span> |  
| <span data-ttu-id="19998-420">例外 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-420">exception \(optional\)</span></span> | [<span data-ttu-id="19998-421">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="19998-421">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="19998-422">例外オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="19998-422">Exception object if available.</span></span> |  
| <span data-ttu-id="19998-423">executionContextId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-423">executionContextId \(optional\)</span></span> | [<span data-ttu-id="19998-424">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="19998-424">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="19998-425">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="19998-425">Identifier of the context where exception happened.</span></span> |  

---  

### <a name="timestamp-integer"></a><span data-ttu-id="19998-426">タイムスタンプの整数</span><span class="sxs-lookup"><span data-stu-id="19998-426">Timestamp integer</span></span>  

<a name="timestamp"></a>  

<span data-ttu-id="19998-427">エポックからのミリ秒単位。</span><span class="sxs-lookup"><span data-stu-id="19998-427">Number of milliseconds since epoch.</span></span>  

&nbsp;  

---  

### <a name="callframe-object"></a><span data-ttu-id="19998-428">CallFrame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-428">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="19998-429">ランタイム エラーとアサーションのスタック エントリ。</span><span class="sxs-lookup"><span data-stu-id="19998-429">Stack entry for runtime errors and assertions.</span></span>  

| <span data-ttu-id="19998-430">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-430">Properties</span></span> | <span data-ttu-id="19998-431">型</span><span class="sxs-lookup"><span data-stu-id="19998-431">Type</span></span> | <span data-ttu-id="19998-432">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-432">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-433">functionName</span><span class="sxs-lookup"><span data-stu-id="19998-433">functionName</span></span> | `string` | <span data-ttu-id="19998-434">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="19998-434">JavaScript function name.</span></span> |  
| <span data-ttu-id="19998-435">scriptId</span><span class="sxs-lookup"><span data-stu-id="19998-435">scriptId</span></span> | [<span data-ttu-id="19998-436">ScriptId</span><span class="sxs-lookup"><span data-stu-id="19998-436">ScriptId</span></span>](#scriptid) | <span data-ttu-id="19998-437">JavaScript スクリプト ID。デバッガーが有効になっていない場合、ScriptId は空になります。</span><span class="sxs-lookup"><span data-stu-id="19998-437">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span> |  
| <span data-ttu-id="19998-438">url</span><span class="sxs-lookup"><span data-stu-id="19998-438">url</span></span> | `string` | <span data-ttu-id="19998-439">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="19998-439">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="19998-440">lineNumber</span><span class="sxs-lookup"><span data-stu-id="19998-440">lineNumber</span></span> | `integer` | <span data-ttu-id="19998-441">JavaScript スクリプト行番号 \(0-based\)。</span><span class="sxs-lookup"><span data-stu-id="19998-441">JavaScript script line number \(0-based\).</span></span> |  
| <span data-ttu-id="19998-442">columnNumber</span><span class="sxs-lookup"><span data-stu-id="19998-442">columnNumber</span></span> | <span data-ttu-id="19998-443">整数</span><span class="sxs-lookup"><span data-stu-id="19998-443">integer</span></span> | <span data-ttu-id="19998-444">JavaScript スクリプト列番号 \(0-based\)。</span><span class="sxs-lookup"><span data-stu-id="19998-444">JavaScript script column number \(0-based\).</span></span> |  

---  

### <a name="stacktrace-object"></a><span data-ttu-id="19998-445">StackTrace オブジェクト</span><span class="sxs-lookup"><span data-stu-id="19998-445">StackTrace object</span></span>  

<a name="stacktrace"></a>  

<span data-ttu-id="19998-446">アサーションまたはエラー メッセージの呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="19998-446">Call frames for assertions or error messages.</span></span>  

| <span data-ttu-id="19998-447">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19998-447">Properties</span></span> | <span data-ttu-id="19998-448">型</span><span class="sxs-lookup"><span data-stu-id="19998-448">Type</span></span> | <span data-ttu-id="19998-449">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-449">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="19998-450">description \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-450">description \(optional\)</span></span> | `string` | <span data-ttu-id="19998-451">このスタック トレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="19998-451">String label of this stack trace.</span></span>  <span data-ttu-id="19998-452">非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19998-452">For async traces this may be a name of the function that initiated the async call.</span></span> |  
| <span data-ttu-id="19998-453">callFrames</span><span class="sxs-lookup"><span data-stu-id="19998-453">callFrames</span></span> | [<span data-ttu-id="19998-454">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="19998-454">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="19998-455">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="19998-455">JavaScript function name.</span></span> |  
| <span data-ttu-id="19998-456">parent \(optional\)</span><span class="sxs-lookup"><span data-stu-id="19998-456">parent \(optional\)</span></span> | [<span data-ttu-id="19998-457">StackTrace</span><span class="sxs-lookup"><span data-stu-id="19998-457">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="19998-458">このスタックの前に含まれる非同期 JavaScript スタック トレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="19998-458">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span> |  

---  
