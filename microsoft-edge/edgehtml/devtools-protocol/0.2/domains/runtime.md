---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f18cca951b298e8b4d870a7d722f30c9d28ad346
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234789"
---
# <span data-ttu-id="f5fa2-106">ランタイム ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="f5fa2-106">Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="f5fa2-107">ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="f5fa2-108">評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="f5fa2-109">元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="f5fa2-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="f5fa2-110">Methods</span></span>**](#methods) | <span data-ttu-id="f5fa2-111">[有効](#enable)、[無効](#disable)、[評価](#evaluate)、callFunctionOn、awaitPromise、getProperties [、globalLexicalScopeNames、releaseObject、releaseObjectGroup、discardConsoleEntries](#globallexicalscopenames) [](#getproperties) [](#awaitpromise) [](#discardconsoleentries) [](#callfunctionon) [](#releaseobject) [](#releaseobjectgroup)</span><span class="sxs-lookup"><span data-stu-id="f5fa2-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |
| [**<span data-ttu-id="f5fa2-112">イベント</span><span class="sxs-lookup"><span data-stu-id="f5fa2-112">Events</span></span>**](#events) | <span data-ttu-id="f5fa2-113">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="f5fa2-113">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |
| [**<span data-ttu-id="f5fa2-114">型</span><span class="sxs-lookup"><span data-stu-id="f5fa2-114">Types</span></span>**](#types) | <span data-ttu-id="f5fa2-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="f5fa2-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="f5fa2-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="f5fa2-116">Methods</span></span>

### <span data-ttu-id="f5fa2-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="f5fa2-117">enable</span></span>
<span data-ttu-id="f5fa2-118">イベントのレポート <code>executionContextCreated</code> を <code>executionContextDestroyed</code> 有効 <code>executionContextsCleared</code> にする。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-118">Enables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span> <span data-ttu-id="f5fa2-119">レポートが有効になると、イベント <code>executionContextCreated</code> は既存の実行コンテキストごとに直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-119">When the reporting gets enabled the <code>executionContextCreated</code> event will be sent immediately for each existing execution context.</span></span>

</p>

---

### <span data-ttu-id="f5fa2-120">[無効]</span><span class="sxs-lookup"><span data-stu-id="f5fa2-120">disable</span></span>
<span data-ttu-id="f5fa2-121">イベントのレポート <code>executionContextCreated</code> を <code>executionContextDestroyed</code> 無効 <code>executionContextsCleared</code> にします。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-121">Disables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span>

</p>

---

### <span data-ttu-id="f5fa2-122">evaluate</span><span class="sxs-lookup"><span data-stu-id="f5fa2-122">evaluate</span></span>
<span data-ttu-id="f5fa2-123">グローバル オブジェクトの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-123">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-124">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-125">式</span><span class="sxs-lookup"><span data-stu-id="f5fa2-125">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-126">評価する式。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-126">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-127">includeCommandLineAPI</span><span class="sxs-lookup"><span data-stu-id="f5fa2-127">includeCommandLineAPI</span></span> <br/> <i><span data-ttu-id="f5fa2-128">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-128">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-129">評価時にコマンド ライン API を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-129">Determines whether Command Line API should be available during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-130">objectGroup</span><span class="sxs-lookup"><span data-stu-id="f5fa2-130">objectGroup</span></span> <br/> <i><span data-ttu-id="f5fa2-131">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-131">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-132">複数のオブジェクトを解放するために使用できるシンボリック グループ名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-132">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-133">silent</span><span class="sxs-lookup"><span data-stu-id="f5fa2-133">silent</span></span> <br/> <i><span data-ttu-id="f5fa2-134">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-134">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-135">サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-135">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="f5fa2-136">状態を上書 <code>setPauseOnException</code> きします。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-136">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-137">contextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-137">contextId</span></span> <br/> <i><span data-ttu-id="f5fa2-138">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-138">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-139">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-139">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="f5fa2-140">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-140">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-141">returnByValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-141">returnByValue</span></span> <br/> <i><span data-ttu-id="f5fa2-142">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-142">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-143">結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-144">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="f5fa2-144">awaitPromise</span></span> <br/> <i><span data-ttu-id="f5fa2-145">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-145">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-146">結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻る必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-146">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-147">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-147">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-148">result</span><span class="sxs-lookup"><span data-stu-id="f5fa2-148">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-149">評価結果。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-149">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-150">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="f5fa2-150">callFunctionOn</span></span>
<span data-ttu-id="f5fa2-151">指定されたオブジェクトの特定の宣言を使用して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-151">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="f5fa2-152">結果のオブジェクト グループはターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-152">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-153">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-153">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-154">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="f5fa2-154">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-155">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-155">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-156">objectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-156">objectId</span></span> <br/> <i><span data-ttu-id="f5fa2-157">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-157">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-158">関数を呼び出すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-158">Identifier of the object to call function on.</span></span> <span data-ttu-id="f5fa2-159">objectId または executionContextId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-159">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="f5fa2-160">objectId は Runtime.evaluate() 関数の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-160">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-161">arguments</span><span class="sxs-lookup"><span data-stu-id="f5fa2-161">arguments</span></span> <br/> <i><span data-ttu-id="f5fa2-162">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-162">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="f5fa2-163">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-163">Call arguments.</span></span> <span data-ttu-id="f5fa2-164">すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-164">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-165">silent</span><span class="sxs-lookup"><span data-stu-id="f5fa2-165">silent</span></span> <br/> <i><span data-ttu-id="f5fa2-166">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-167">サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-167">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="f5fa2-168">状態を上書 <code>setPauseOnException</code> きします。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-168">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-169">returnByValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-169">returnByValue</span></span> <br/> <i><span data-ttu-id="f5fa2-170">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-170">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-171">結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-171">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-172">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="f5fa2-172">awaitPromise</span></span> <br/> <i><span data-ttu-id="f5fa2-173">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-173">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-174">結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻る必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-174">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-175">executionContextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-175">executionContextId</span></span> <br/> <i><span data-ttu-id="f5fa2-176">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-176">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-177">関数の呼び出しに使用するグローバル オブジェクトの実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-177">Specifies execution context which global object will be used to call function on.</span></span> <span data-ttu-id="f5fa2-178">executionContextId または objectId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-178">Either executionContextId or objectId should be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-179">objectGroup</span><span class="sxs-lookup"><span data-stu-id="f5fa2-179">objectGroup</span></span> <br/> <i><span data-ttu-id="f5fa2-180">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-180">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-181">複数のオブジェクトを解放するために使用できるシンボリック グループ名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-181">Symbolic group name that can be used to release multiple objects.</span></span> <span data-ttu-id="f5fa2-182">objectGroup が指定されていない場合、objectId が指定されている場合、objectGroup はオブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-182">If objectGroup is not specified and objectId is, objectGroup will be inherited from object.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-183">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-183">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-184">result</span><span class="sxs-lookup"><span data-stu-id="f5fa2-184">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-185">呼び出しの結果。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-185">Call result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-186">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="f5fa2-186">awaitPromise</span></span>
<span data-ttu-id="f5fa2-187">指定された promise オブジェクト ID と約束するハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-187">Add handler to promise with given promise object id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-188">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-189">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-189">promiseObjectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-190">promise の識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-190">Identifier of the promise.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-191">returnByValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-191">returnByValue</span></span> <br/> <i><span data-ttu-id="f5fa2-192">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-192">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-193">結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-193">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-194">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-194">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-195">result</span><span class="sxs-lookup"><span data-stu-id="f5fa2-195">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-196">Promise の結果。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-196">Promise result.</span></span>  <span data-ttu-id="f5fa2-197">promise が拒否された場合、拒否された値が含まれる。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-197">Will contain rejected value if promise was rejected.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-198">getProperties</span><span class="sxs-lookup"><span data-stu-id="f5fa2-198">getProperties</span></span>
<span data-ttu-id="f5fa2-199">指定したオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-199">Returns properties of a given object.</span></span> <span data-ttu-id="f5fa2-200">結果のオブジェクト グループはターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-200">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-201">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-201">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-202">objectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-202">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-203">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-203">Identifier of the object to return properties for.</span></span> <span data-ttu-id="f5fa2-204">objectId は Debugger.evaluateOnCallFrame() 関数の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-204">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-205">ownProperties</span><span class="sxs-lookup"><span data-stu-id="f5fa2-205">ownProperties</span></span> <br/> <i><span data-ttu-id="f5fa2-206">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-206">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-207">true の場合、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-207">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-208">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="f5fa2-208">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="f5fa2-209">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-209">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="f5fa2-210">試験的。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-210">Experimental.</span></span> </b></span><span data-ttu-id="f5fa2-211">true の場合、アクセサー プロパティ (getter/setter を使用) のみを返します。内部プロパティも返されません。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-211">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-212">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-212">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-213">result</span><span class="sxs-lookup"><span data-stu-id="f5fa2-213">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="f5fa2-214">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-214">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-215">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="f5fa2-215">globalLexicalScopeNames</span></span>
<span data-ttu-id="f5fa2-216">コンソール グローバル スコープから、すべての let、const、およびクラス変数を返します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-216">Returns all let, const, and class variables from the console global scope.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-217">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-218">names</span><span class="sxs-lookup"><span data-stu-id="f5fa2-218">names</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-219">releaseObject</span><span class="sxs-lookup"><span data-stu-id="f5fa2-219">releaseObject</span></span>
<span data-ttu-id="f5fa2-220">指定された ID を持つリモート オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-220">Releases remote object with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-221">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-221">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-222">objectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-222">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-223">解放するオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-223">Identifier of the object to release.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-224">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="f5fa2-224">releaseObjectGroup</span></span>
<span data-ttu-id="f5fa2-225">特定のグループに属しているすべてのリモート オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-225">Releases all remote objects that belong to a given group.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-226">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-226">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-227">objectGroup</span><span class="sxs-lookup"><span data-stu-id="f5fa2-227">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-228">シンボリック オブジェクト グループ名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-228">Symbolic object group name.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-229">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="f5fa2-229">discardConsoleEntries</span></span>
<span data-ttu-id="f5fa2-230">収集された例外とコンソール API 呼び出しを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-230">Discards collected exceptions and console API calls.</span></span>

</p>

---

## <span data-ttu-id="f5fa2-231">イベント</span><span class="sxs-lookup"><span data-stu-id="f5fa2-231">Events</span></span>

### <span data-ttu-id="f5fa2-232">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="f5fa2-232">executionContextCreated</span></span>
<span data-ttu-id="f5fa2-233">新しい実行コンテキストが作成されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-233">Issued when new execution context is created.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-234">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-234">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-235">context</span><span class="sxs-lookup"><span data-stu-id="f5fa2-235">context</span></span></td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td><span data-ttu-id="f5fa2-236">新しく作成された実行コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-236">A newly created execution context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-237">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="f5fa2-237">executionContextDestroyed</span></span>
<span data-ttu-id="f5fa2-238">実行コンテキストが破棄されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-238">Issued when execution context is destroyed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-240">executionContextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-240">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-241">破棄されたコンテキストの ID</span><span class="sxs-lookup"><span data-stu-id="f5fa2-241">Id of the destroyed context</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-242">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="f5fa2-242">executionContextsCleared</span></span>
<span data-ttu-id="f5fa2-243">ブラウザーですべての executionContexts がクリアされた場合に発行されます</span><span class="sxs-lookup"><span data-stu-id="f5fa2-243">Issued when all executionContexts were cleared in browser</span></span>

</p>

---

### <span data-ttu-id="f5fa2-244">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="f5fa2-244">exceptionThrown</span></span>
<span data-ttu-id="f5fa2-245">例外がスローされ、処理されない場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-245">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-246">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-246">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-247">timestamp</span><span class="sxs-lookup"><span data-stu-id="f5fa2-247">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="f5fa2-248">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-248">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-249">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="f5fa2-249">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f5fa2-250">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="f5fa2-250">consoleAPICalled</span></span>


<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-251">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5fa2-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-252">型</span><span class="sxs-lookup"><span data-stu-id="f5fa2-252">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="f5fa2-253">有効な値: log、info、warning、error、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、startGroupCollapsed、endGroup</span><span class="sxs-lookup"><span data-stu-id="f5fa2-253">Allowed values: log, info, warning, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, timeStamp, startGroup, startGroupCollapsed, endGroup</span></span></i></td>
            <td><span data-ttu-id="f5fa2-254">通話の種類。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-254">Type of the call.</span></span> <span data-ttu-id="f5fa2-255">これには、ログ、情報、警告、エラー、デバッグ、アサート、テーブル、トレース、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、groupEnd が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-255">This includes log, info, warn, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, exception, timeStamp, group, groupCollapsed, groupEnd.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-256">args</span><span class="sxs-lookup"><span data-stu-id="f5fa2-256">args</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td><span data-ttu-id="f5fa2-257">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-257">Call arguments.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-258">executionContextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-258">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-259">コンソール呼び出しが行われたコンテキストの識別子</span><span class="sxs-lookup"><span data-stu-id="f5fa2-259">Identifier of the context where console call was made</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-260">timestamp</span><span class="sxs-lookup"><span data-stu-id="f5fa2-260">timestamp</span></span> <br/> <i><span data-ttu-id="f5fa2-261">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-261">optional</span></span></i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="f5fa2-262">呼び出しのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-262">Call timestamp.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-263">stackTrace</span><span class="sxs-lookup"><span data-stu-id="f5fa2-263">stackTrace</span></span> <br/> <i><span data-ttu-id="f5fa2-264">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-264">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="f5fa2-265">可能な場合にキャプチャされたスタック トレース</span><span class="sxs-lookup"><span data-stu-id="f5fa2-265">Stack trace captured if available</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="f5fa2-266">型</span><span class="sxs-lookup"><span data-stu-id="f5fa2-266">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="f5fa2-267">ScriptId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-267">ScriptId</span></span> `string`

<span data-ttu-id="f5fa2-268">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-268">Unique script identifier.</span></span>

</p>

---

### <a name="remoteobjectid"></a> <span data-ttu-id="f5fa2-269">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-269">RemoteObjectId</span></span> `string`

<span data-ttu-id="f5fa2-270">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-270">Unique object identifier.</span></span>

</p>

---

### <a name="unserializablevalue"></a> <span data-ttu-id="f5fa2-271">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-271">UnserializableValue</span></span> `string`

<span data-ttu-id="f5fa2-272">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-272">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="f5fa2-273">使用できる値</span><span class="sxs-lookup"><span data-stu-id="f5fa2-273">Allowed Values</span></span>
<span data-ttu-id="f5fa2-274">Infinity、NaN、-Infinity、-0</span><span class="sxs-lookup"><span data-stu-id="f5fa2-274">Infinity, NaN, -Infinity, -0</span></span>
</p>

---

### <a name="remoteobject"></a> <span data-ttu-id="f5fa2-275">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="f5fa2-275">RemoteObject</span></span> `object`

<span data-ttu-id="f5fa2-276">元の JavaScript オブジェクトを参照するミラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-276">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-277">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-277">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-278">型</span><span class="sxs-lookup"><span data-stu-id="f5fa2-278">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="f5fa2-279">有効な値: object、function、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="f5fa2-279">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="f5fa2-280">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-280">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-281">subtype</span><span class="sxs-lookup"><span data-stu-id="f5fa2-281">subtype</span></span> <br/> <i><span data-ttu-id="f5fa2-282">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-282">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="f5fa2-283">使用できる値: null、error、promise、node</span><span class="sxs-lookup"><span data-stu-id="f5fa2-283">Allowed values: null, error, promise, node</span></span></i></td>
            <td><span data-ttu-id="f5fa2-284">オブジェクトサブタイプのヒント。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-284">Object subtype hint.</span></span> <span data-ttu-id="f5fa2-285">型の値 <code>object</code> にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-285">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-286">className</span><span class="sxs-lookup"><span data-stu-id="f5fa2-286">className</span></span> <br/> <i><span data-ttu-id="f5fa2-287">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-287">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-288">オブジェクト クラス (コンストラクター) 名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-288">Object class (constructor) name.</span></span> <span data-ttu-id="f5fa2-289">型の値 <code>object</code> にのみ指定されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-289">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-290">value</span><span class="sxs-lookup"><span data-stu-id="f5fa2-290">value</span></span> <br/> <i><span data-ttu-id="f5fa2-291">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-291">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="f5fa2-292">プリミティブ値または JSON 値の場合のリモート オブジェクト値 (要求された場合)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-292">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-293">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-293">unserializableValue</span></span> <br/> <i><span data-ttu-id="f5fa2-294">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-294">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="f5fa2-295">JSON 文字列化できないプリミティブ値には、次の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-295">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="f5fa2-296">が、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-296">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-297">description</span><span class="sxs-lookup"><span data-stu-id="f5fa2-297">description</span></span> <br/> <i><span data-ttu-id="f5fa2-298">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-298">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-299">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-299">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-300">objectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-300">objectId</span></span> <br/> <i><span data-ttu-id="f5fa2-301">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-301">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-302">一意のオブジェクト識別子 (プリミティブ値以外の場合)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-302">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-303">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-303">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="f5fa2-304">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-304">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="f5fa2-305">試験的。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-305">Experimental.</span></span> </b></span><span data-ttu-id="f5fa2-306">Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-306">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="f5fa2-307">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="f5fa2-307">PropertyDescriptor</span></span> `object`

<span data-ttu-id="f5fa2-308">オブジェクト プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-308">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-309">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-309">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-310">name</span><span class="sxs-lookup"><span data-stu-id="f5fa2-310">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-311">プロパティ名または記号の説明。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-311">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-312">value</span><span class="sxs-lookup"><span data-stu-id="f5fa2-312">value</span></span> <br/> <i><span data-ttu-id="f5fa2-313">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-313">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-314">プロパティに関連付けられている値。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-314">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-315">書き込み可能</span><span class="sxs-lookup"><span data-stu-id="f5fa2-315">writable</span></span> <br/> <i><span data-ttu-id="f5fa2-316">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-316">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-317">True の 場合は、プロパティに関連付けられている値が変更される可能性があります (データ記述子のみ)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-317">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-318">取得</span><span class="sxs-lookup"><span data-stu-id="f5fa2-318">get</span></span> <br/> <i><span data-ttu-id="f5fa2-319">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-319">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-320">プロパティの getter として機能する関数、または getter がない場合 (アクセサー記述子 <code>undefined</code> のみ)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-320">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-321">set</span><span class="sxs-lookup"><span data-stu-id="f5fa2-321">set</span></span> <br/> <i><span data-ttu-id="f5fa2-322">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-322">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-323">プロパティのセッターとして機能する関数、または setter がない場合 (アクセサー記述子 <code>undefined</code> のみ)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-323">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-324">構成可能</span><span class="sxs-lookup"><span data-stu-id="f5fa2-324">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-325">True の 場合は、このプロパティ記述子の型が変更され、対応するオブジェクトからプロパティを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-325">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-326">enumerable</span><span class="sxs-lookup"><span data-stu-id="f5fa2-326">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-327">True の 場合、このプロパティは、対応するオブジェクトのプロパティの列挙中に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-327">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-328">wasThrown</span><span class="sxs-lookup"><span data-stu-id="f5fa2-328">wasThrown</span></span> <br/> <i><span data-ttu-id="f5fa2-329">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-329">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-330">True の 場合は、評価中に結果がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-330">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-331">isOwn</span><span class="sxs-lookup"><span data-stu-id="f5fa2-331">isOwn</span></span> <br/> <i><span data-ttu-id="f5fa2-332">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-332">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="f5fa2-333">True の 場合は、プロパティがオブジェクトに対して所有されています。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-333">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-334">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-334">msReturnValue</span></span> <br/> <i><span data-ttu-id="f5fa2-335">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-335">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="f5fa2-336">試験的。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-336">Experimental.</span></span> </b></span><span data-ttu-id="f5fa2-337">Microsoft: プロパティが戻り値の場合は True。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-337">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-338">symbol</span><span class="sxs-lookup"><span data-stu-id="f5fa2-338">symbol</span></span> <br/> <i><span data-ttu-id="f5fa2-339">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-339">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-340">プロパティが型の場合、プロパティ シンボル `symbol` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-340">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> <span data-ttu-id="f5fa2-341">CallArgument</span><span class="sxs-lookup"><span data-stu-id="f5fa2-341">CallArgument</span></span> `object`

<span data-ttu-id="f5fa2-342">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-342">Represents function call argument.</span></span> <span data-ttu-id="f5fa2-343">リモート オブジェクト ID、プリミティブ、読み取りできないプリミティブ値、または <code>objectId</code> <code>value</code> (未定義の場合) どちらも指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-343">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-344">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-344">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-345">value</span><span class="sxs-lookup"><span data-stu-id="f5fa2-345">value</span></span> <br/> <i><span data-ttu-id="f5fa2-346">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-346">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="f5fa2-347">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-347">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-348">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="f5fa2-348">unserializableValue</span></span> <br/> <i><span data-ttu-id="f5fa2-349">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-349">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="f5fa2-350">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-350">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-351">objectId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-351">objectId</span></span> <br/> <i><span data-ttu-id="f5fa2-352">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-352">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="f5fa2-353">リモート オブジェクト ハンドル。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-353">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="executioncontextid"></a> <span data-ttu-id="f5fa2-354">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-354">ExecutionContextId</span></span> `integer`

<span data-ttu-id="f5fa2-355">実行コンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-355">Id of an execution context.</span></span>

</p>

---

### <a name="executioncontextdescription"></a> <span data-ttu-id="f5fa2-356">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="f5fa2-356">ExecutionContextDescription</span></span> `object`

<span data-ttu-id="f5fa2-357">分離された世界の説明。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-357">Description of an isolated world.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-358">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-358">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-359">id</span><span class="sxs-lookup"><span data-stu-id="f5fa2-359">id</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-360">実行コンテキストの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-360">Unique id of the execution context.</span></span> <span data-ttu-id="f5fa2-361">これは、実行コンテキスト スクリプトの評価を実行する必要がある実行コンテキストを指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-361">It can be used to specify in which execution context script evaluation should be performed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-362">origin</span><span class="sxs-lookup"><span data-stu-id="f5fa2-362">origin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-363">実行コンテキストの原点。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-363">Execution context origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-364">name</span><span class="sxs-lookup"><span data-stu-id="f5fa2-364">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-365">特定のコンテキストを記述する人間が読み取り可能な名前。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-365">Human readable name describing given context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> <span data-ttu-id="f5fa2-366">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="f5fa2-366">ExceptionDetails</span></span> `object`

<span data-ttu-id="f5fa2-367">スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-367">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-368">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-369">exceptionId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-369">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="f5fa2-370">例外 ID。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-370">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-371">テキスト</span><span class="sxs-lookup"><span data-stu-id="f5fa2-371">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-372">例外テキスト。利用可能な場合は例外オブジェクトと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-372">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-373">lineNumber</span><span class="sxs-lookup"><span data-stu-id="f5fa2-373">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="f5fa2-374">例外の場所の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-374">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-375">columnNumber</span><span class="sxs-lookup"><span data-stu-id="f5fa2-375">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="f5fa2-376">例外の場所の列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-376">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-377">scriptId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-377">scriptId</span></span> <br/> <i><span data-ttu-id="f5fa2-378">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-378">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="f5fa2-379">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-379">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-380">url</span><span class="sxs-lookup"><span data-stu-id="f5fa2-380">url</span></span> <br/> <i><span data-ttu-id="f5fa2-381">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-381">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-382">スクリプトが報告されていないときに使用される例外の場所の URL。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-382">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-383">stackTrace</span><span class="sxs-lookup"><span data-stu-id="f5fa2-383">stackTrace</span></span> <br/> <i><span data-ttu-id="f5fa2-384">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-384">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="f5fa2-385">JavaScript スタック トレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-385">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-386">exception</span><span class="sxs-lookup"><span data-stu-id="f5fa2-386">exception</span></span> <br/> <i><span data-ttu-id="f5fa2-387">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-387">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="f5fa2-388">Exception オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-388">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-389">executionContextId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-389">executionContextId</span></span> <br/> <i><span data-ttu-id="f5fa2-390">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-390">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="f5fa2-391">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-391">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="timestamp"></a> <span data-ttu-id="f5fa2-392">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-392">Timestamp</span></span> `integer`

<span data-ttu-id="f5fa2-393">エポックからのミリ秒単位の値です。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-393">Number of milliseconds since epoch.</span></span>

</p>

---

### <a name="callframe"></a> <span data-ttu-id="f5fa2-394">CallFrame</span><span class="sxs-lookup"><span data-stu-id="f5fa2-394">CallFrame</span></span> `object`

<span data-ttu-id="f5fa2-395">ランタイム エラーとアサーションのスタック エントリ。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-395">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-396">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-396">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-397">functionName</span><span class="sxs-lookup"><span data-stu-id="f5fa2-397">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-398">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-398">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-399">scriptId</span><span class="sxs-lookup"><span data-stu-id="f5fa2-399">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="f5fa2-400">JavaScript スクリプト ID。デバッガーが有効になっていない場合、ScriptId は空になります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-400">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-401">url</span><span class="sxs-lookup"><span data-stu-id="f5fa2-401">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-402">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-402">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-403">lineNumber</span><span class="sxs-lookup"><span data-stu-id="f5fa2-403">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="f5fa2-404">JavaScript スクリプト行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-404">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-405">columnNumber</span><span class="sxs-lookup"><span data-stu-id="f5fa2-405">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="f5fa2-406">JavaScript スクリプトの列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-406">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> <span data-ttu-id="f5fa2-407">StackTrace</span><span class="sxs-lookup"><span data-stu-id="f5fa2-407">StackTrace</span></span> `object`

<span data-ttu-id="f5fa2-408">アサーションまたはエラー メッセージの呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-408">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f5fa2-409">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5fa2-409">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f5fa2-410">description</span><span class="sxs-lookup"><span data-stu-id="f5fa2-410">description</span></span> <br/> <i><span data-ttu-id="f5fa2-411">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-411">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f5fa2-412">このスタック トレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-412">String label of this stack trace.</span></span> <span data-ttu-id="f5fa2-413">非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-413">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-414">callFrames</span><span class="sxs-lookup"><span data-stu-id="f5fa2-414">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="f5fa2-415">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-415">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f5fa2-416">parent</span><span class="sxs-lookup"><span data-stu-id="f5fa2-416">parent</span></span> <br/> <i><span data-ttu-id="f5fa2-417">オプション</span><span class="sxs-lookup"><span data-stu-id="f5fa2-417">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="f5fa2-418">このスタックより前の非同期 JavaScript スタック トレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="f5fa2-418">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
