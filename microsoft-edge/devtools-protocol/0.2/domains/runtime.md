---
description: Runtime ドメインの参照。 ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
title: ランタイムドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 710b3b3e0383f1f6feb7947e0468730d2e0b0e66
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882864"
---
# <span data-ttu-id="98d50-106">ランタイムドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="98d50-106">Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="98d50-107">ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="98d50-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="98d50-108">評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="98d50-109">元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="98d50-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="98d50-110">Methods</span></span>**](#methods) | <span data-ttu-id="98d50-111">[enable](#enable)、 [disable](#disable)、 [evaluate](#evaluate)、 [callfunctionon](#callfunctionon)、 [waitpromise](#awaitpromise)、 [getProperties](#getproperties)、 [globalLexicalScopeNames](#globallexicalscopenames)、 [releaseobject](#releaseobject)、 [releaseobjectgroup](#releaseobjectgroup)、 [discardConsoleEntries](#discardconsoleentries)</span><span class="sxs-lookup"><span data-stu-id="98d50-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |
| [**<span data-ttu-id="98d50-112">イベント</span><span class="sxs-lookup"><span data-stu-id="98d50-112">Events</span></span>**](#events) | <span data-ttu-id="98d50-113">[Executioncontextcreated](#executioncontextcreated)、 [executioncontextcreated](#executioncontextdestroyed)、 [executioncontextsクリアー](#executioncontextscleared)、 [exceptionthrown](#exceptionthrown)、 [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="98d50-113">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |
| [**<span data-ttu-id="98d50-114">型</span><span class="sxs-lookup"><span data-stu-id="98d50-114">Types</span></span>**](#types) | <span data-ttu-id="98d50-115">[Scriptid](#scriptid)、 [remoteobjectid](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [remoteobjectid](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [callargument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [executioncontextdescription](#executioncontextdescription)、 [exceptiondetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [callargument](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="98d50-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="98d50-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="98d50-116">Methods</span></span>

### <span data-ttu-id="98d50-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="98d50-117">enable</span></span>
<span data-ttu-id="98d50-118">およびイベントのレポートを有効にし <code>executionContextCreated</code> <code>executionContextDestroyed</code> <code>executionContextsCleared</code> ます。</span><span class="sxs-lookup"><span data-stu-id="98d50-118">Enables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span> <span data-ttu-id="98d50-119">レポートを有効にすると、 <code>executionContextCreated</code> 既存の実行コンテキストごとに、イベントが直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-119">When the reporting gets enabled the <code>executionContextCreated</code> event will be sent immediately for each existing execution context.</span></span>

</p>

---

### <span data-ttu-id="98d50-120">[無効]</span><span class="sxs-lookup"><span data-stu-id="98d50-120">disable</span></span>
<span data-ttu-id="98d50-121">およびイベントの報告を無効 <code>executionContextCreated</code> にし <code>executionContextDestroyed</code> <code>executionContextsCleared</code> ます。</span><span class="sxs-lookup"><span data-stu-id="98d50-121">Disables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span>

</p>

---

### <span data-ttu-id="98d50-122">ぜひ</span><span class="sxs-lookup"><span data-stu-id="98d50-122">evaluate</span></span>
<span data-ttu-id="98d50-123">グローバルオブジェクトで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="98d50-123">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-124">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-125">expression</span><span class="sxs-lookup"><span data-stu-id="98d50-125">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-126">評価する式。</span><span class="sxs-lookup"><span data-stu-id="98d50-126">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-127">includeCommandLineAPI</span><span class="sxs-lookup"><span data-stu-id="98d50-127">includeCommandLineAPI</span></span> <br/> <i><span data-ttu-id="98d50-128">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-128">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-129">評価中にコマンドライン API を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="98d50-129">Determines whether Command Line API should be available during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-130">objectGroup</span><span class="sxs-lookup"><span data-stu-id="98d50-130">objectGroup</span></span> <br/> <i><span data-ttu-id="98d50-131">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-131">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-132">複数のオブジェクトを解放するために使用できるシンボリックグループ名。</span><span class="sxs-lookup"><span data-stu-id="98d50-132">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-133">silent</span><span class="sxs-lookup"><span data-stu-id="98d50-133">silent</span></span> <br/> <i><span data-ttu-id="98d50-134">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-134">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-135">サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="98d50-135">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="98d50-136"><code>setPauseOnException</code>State の上書き。</span><span class="sxs-lookup"><span data-stu-id="98d50-136">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-137">contextId</span><span class="sxs-lookup"><span data-stu-id="98d50-137">contextId</span></span> <br/> <i><span data-ttu-id="98d50-138">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-138">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-139">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="98d50-139">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="98d50-140">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-140">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-141">returnByValue</span><span class="sxs-lookup"><span data-stu-id="98d50-141">returnByValue</span></span> <br/> <i><span data-ttu-id="98d50-142">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-142">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-143">結果が、値によって送信される必要がある JSON オブジェクトであると想定されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="98d50-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-144">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="98d50-144">awaitPromise</span></span> <br/> <i><span data-ttu-id="98d50-145">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-145">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-146">結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="98d50-146">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-147">返し</span><span class="sxs-lookup"><span data-stu-id="98d50-147">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-148">より</span><span class="sxs-lookup"><span data-stu-id="98d50-148">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-149">評価結果。</span><span class="sxs-lookup"><span data-stu-id="98d50-149">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-150">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="98d50-150">callFunctionOn</span></span>
<span data-ttu-id="98d50-151">指定したオブジェクトで指定された宣言の関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d50-151">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="98d50-152">結果のオブジェクトグループがターゲットオブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-152">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-153">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-153">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-154">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="98d50-154">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-155">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="98d50-155">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-156">objectId</span><span class="sxs-lookup"><span data-stu-id="98d50-156">objectId</span></span> <br/> <i><span data-ttu-id="98d50-157">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-157">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-158">呼び出す関数の対象となるオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-158">Identifier of the object to call function on.</span></span> <span data-ttu-id="98d50-159">ObjectId または executionContextId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-159">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="98d50-160">objectId は、evaluate () 関数からのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-160">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-161">arguments</span><span class="sxs-lookup"><span data-stu-id="98d50-161">arguments</span></span> <br/> <i><span data-ttu-id="98d50-162">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-162">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="98d50-163">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d50-163">Call arguments.</span></span> <span data-ttu-id="98d50-164">すべての呼び出し引数は、ターゲットオブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-164">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-165">silent</span><span class="sxs-lookup"><span data-stu-id="98d50-165">silent</span></span> <br/> <i><span data-ttu-id="98d50-166">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-167">サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="98d50-167">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="98d50-168"><code>setPauseOnException</code>State の上書き。</span><span class="sxs-lookup"><span data-stu-id="98d50-168">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-169">returnByValue</span><span class="sxs-lookup"><span data-stu-id="98d50-169">returnByValue</span></span> <br/> <i><span data-ttu-id="98d50-170">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-170">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-171">結果が JSON オブジェクトであると想定されるかどうか。値で送信する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="98d50-171">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-172">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="98d50-172">awaitPromise</span></span> <br/> <i><span data-ttu-id="98d50-173">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-173">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-174">結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="98d50-174">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-175">executionContextId</span><span class="sxs-lookup"><span data-stu-id="98d50-175">executionContextId</span></span> <br/> <i><span data-ttu-id="98d50-176">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-176">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-177">関数の呼び出しに使用するグローバルオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="98d50-177">Specifies execution context which global object will be used to call function on.</span></span> <span data-ttu-id="98d50-178">ExecutionContextId または objectId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-178">Either executionContextId or objectId should be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-179">objectGroup</span><span class="sxs-lookup"><span data-stu-id="98d50-179">objectGroup</span></span> <br/> <i><span data-ttu-id="98d50-180">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-180">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-181">複数のオブジェクトを解放するために使用できるシンボリックグループ名。</span><span class="sxs-lookup"><span data-stu-id="98d50-181">Symbolic group name that can be used to release multiple objects.</span></span> <span data-ttu-id="98d50-182">ObjectGroup が指定されておらず、objectId が指定されていない場合、objectGroup は object から継承されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-182">If objectGroup is not specified and objectId is, objectGroup will be inherited from object.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-183">返し</span><span class="sxs-lookup"><span data-stu-id="98d50-183">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-184">より</span><span class="sxs-lookup"><span data-stu-id="98d50-184">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-185">通話の結果。</span><span class="sxs-lookup"><span data-stu-id="98d50-185">Call result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-186">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="98d50-186">awaitPromise</span></span>
<span data-ttu-id="98d50-187">指定された promise オブジェクト id を使用して、約束にハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="98d50-187">Add handler to promise with given promise object id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-188">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-189">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="98d50-189">promiseObjectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-190">約束の識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-190">Identifier of the promise.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-191">returnByValue</span><span class="sxs-lookup"><span data-stu-id="98d50-191">returnByValue</span></span> <br/> <i><span data-ttu-id="98d50-192">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-192">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-193">結果が、値によって送信される必要がある JSON オブジェクトであると想定されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="98d50-193">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-194">返し</span><span class="sxs-lookup"><span data-stu-id="98d50-194">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-195">より</span><span class="sxs-lookup"><span data-stu-id="98d50-195">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-196">約束の結果。</span><span class="sxs-lookup"><span data-stu-id="98d50-196">Promise result.</span></span>  <span data-ttu-id="98d50-197">Promise が拒否された場合は、拒否されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-197">Will contain rejected value if promise was rejected.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-198">getProperties</span><span class="sxs-lookup"><span data-stu-id="98d50-198">getProperties</span></span>
<span data-ttu-id="98d50-199">指定されたオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="98d50-199">Returns properties of a given object.</span></span> <span data-ttu-id="98d50-200">結果のオブジェクトグループがターゲットオブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-200">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-201">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-201">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-202">objectId</span><span class="sxs-lookup"><span data-stu-id="98d50-202">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-203">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-203">Identifier of the object to return properties for.</span></span> <span data-ttu-id="98d50-204">objectId はデバッガーからである必要があります。 evaluateOnCallFrame () 関数。</span><span class="sxs-lookup"><span data-stu-id="98d50-204">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-205">ownProperties</span><span class="sxs-lookup"><span data-stu-id="98d50-205">ownProperties</span></span> <br/> <i><span data-ttu-id="98d50-206">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-206">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-207">True の場合は、プロトタイプチェーンではなく、要素自体にのみ属しているプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="98d50-207">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-208">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="98d50-208">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="98d50-209">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-209">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="98d50-210">的.</span><span class="sxs-lookup"><span data-stu-id="98d50-210">Experimental.</span></span> </b></span><span data-ttu-id="98d50-211">True の場合は、アクセサープロパティ (getter/setter) のみを返します。内部プロパティは返されません。</span><span class="sxs-lookup"><span data-stu-id="98d50-211">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-212">返し</span><span class="sxs-lookup"><span data-stu-id="98d50-212">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-213">より</span><span class="sxs-lookup"><span data-stu-id="98d50-213">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="98d50-214">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="98d50-214">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-215">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="98d50-215">globalLexicalScopeNames</span></span>
<span data-ttu-id="98d50-216">すべての let、const、および class 変数を本体のグローバルスコープから返します。</span><span class="sxs-lookup"><span data-stu-id="98d50-216">Returns all let, const, and class variables from the console global scope.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-217">返し</span><span class="sxs-lookup"><span data-stu-id="98d50-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-218">名</span><span class="sxs-lookup"><span data-stu-id="98d50-218">names</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-219">releaseObject</span><span class="sxs-lookup"><span data-stu-id="98d50-219">releaseObject</span></span>
<span data-ttu-id="98d50-220">指定した id のリモートオブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="98d50-220">Releases remote object with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-221">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-221">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-222">objectId</span><span class="sxs-lookup"><span data-stu-id="98d50-222">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-223">解放するオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-223">Identifier of the object to release.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-224">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="98d50-224">releaseObjectGroup</span></span>
<span data-ttu-id="98d50-225">指定したグループに属しているすべてのリモートオブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="98d50-225">Releases all remote objects that belong to a given group.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-226">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-226">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-227">objectGroup</span><span class="sxs-lookup"><span data-stu-id="98d50-227">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-228">シンボリックオブジェクトグループ名。</span><span class="sxs-lookup"><span data-stu-id="98d50-228">Symbolic object group name.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-229">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="98d50-229">discardConsoleEntries</span></span>
<span data-ttu-id="98d50-230">収集された例外とコンソール API の呼び出しを破棄します。</span><span class="sxs-lookup"><span data-stu-id="98d50-230">Discards collected exceptions and console API calls.</span></span>

</p>

---

## <span data-ttu-id="98d50-231">イベント</span><span class="sxs-lookup"><span data-stu-id="98d50-231">Events</span></span>

### <span data-ttu-id="98d50-232">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="98d50-232">executionContextCreated</span></span>
<span data-ttu-id="98d50-233">新しい実行コンテキストが作成されたときに発行されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-233">Issued when new execution context is created.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-234">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-234">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-235">context</span><span class="sxs-lookup"><span data-stu-id="98d50-235">context</span></span></td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td><span data-ttu-id="98d50-236">新しく作成された実行コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="98d50-236">A newly created execution context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-237">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="98d50-237">executionContextDestroyed</span></span>
<span data-ttu-id="98d50-238">実行コンテキストが破棄されたときに発行されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-238">Issued when execution context is destroyed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-240">executionContextId</span><span class="sxs-lookup"><span data-stu-id="98d50-240">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-241">破棄されたコンテキストの Id</span><span class="sxs-lookup"><span data-stu-id="98d50-241">Id of the destroyed context</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-242">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="98d50-242">executionContextsCleared</span></span>
<span data-ttu-id="98d50-243">ブラウザーですべての executionContexts が消去されたときに発行される</span><span class="sxs-lookup"><span data-stu-id="98d50-243">Issued when all executionContexts were cleared in browser</span></span>

</p>

---

### <span data-ttu-id="98d50-244">例外のスロー</span><span class="sxs-lookup"><span data-stu-id="98d50-244">exceptionThrown</span></span>
<span data-ttu-id="98d50-245">例外がスローされて処理不能になったときに発行されます。</span><span class="sxs-lookup"><span data-stu-id="98d50-245">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-246">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-246">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-247">示</span><span class="sxs-lookup"><span data-stu-id="98d50-247">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="98d50-248">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="98d50-248">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-249">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="98d50-249">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="98d50-250">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="98d50-250">consoleAPICalled</span></span>


<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-251">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98d50-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-252">型</span><span class="sxs-lookup"><span data-stu-id="98d50-252">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="98d50-253">許可される値: ログ、情報、警告、エラー、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、Startgroup折りたたまれた、endGroup</span><span class="sxs-lookup"><span data-stu-id="98d50-253">Allowed values: log, info, warning, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, timeStamp, startGroup, startGroupCollapsed, endGroup</span></span></i></td>
            <td><span data-ttu-id="98d50-254">通話の種類。</span><span class="sxs-lookup"><span data-stu-id="98d50-254">Type of the call.</span></span> <span data-ttu-id="98d50-255">これには、ログ、情報、警告、エラー、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、Groupcollapsed が含まれます。</span><span class="sxs-lookup"><span data-stu-id="98d50-255">This includes log, info, warn, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, exception, timeStamp, group, groupCollapsed, groupEnd.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-256">引数</span><span class="sxs-lookup"><span data-stu-id="98d50-256">args</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td><span data-ttu-id="98d50-257">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d50-257">Call arguments.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-258">executionContextId</span><span class="sxs-lookup"><span data-stu-id="98d50-258">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-259">本体の呼び出しが行われたコンテキストの識別子</span><span class="sxs-lookup"><span data-stu-id="98d50-259">Identifier of the context where console call was made</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-260">示</span><span class="sxs-lookup"><span data-stu-id="98d50-260">timestamp</span></span> <br/> <i><span data-ttu-id="98d50-261">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-261">optional</span></span></i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="98d50-262">通話のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="98d50-262">Call timestamp.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-263">stackTrace</span><span class="sxs-lookup"><span data-stu-id="98d50-263">stackTrace</span></span> <br/> <i><span data-ttu-id="98d50-264">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-264">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="98d50-265">使用可能な場合にスタックトレースがキャプチャされる</span><span class="sxs-lookup"><span data-stu-id="98d50-265">Stack trace captured if available</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="98d50-266">型</span><span class="sxs-lookup"><span data-stu-id="98d50-266">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="98d50-267">ScriptId</span><span class="sxs-lookup"><span data-stu-id="98d50-267">ScriptId</span></span> `string`

<span data-ttu-id="98d50-268">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-268">Unique script identifier.</span></span>

</p>

---

### <a name="remoteobjectid"></a> <span data-ttu-id="98d50-269">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="98d50-269">RemoteObjectId</span></span> `string`

<span data-ttu-id="98d50-270">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-270">Unique object identifier.</span></span>

</p>

---

### <a name="unserializablevalue"></a> <span data-ttu-id="98d50-271">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="98d50-271">UnserializableValue</span></span> `string`

<span data-ttu-id="98d50-272">Stringified にすることができないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="98d50-272">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="98d50-273">許可される値</span><span class="sxs-lookup"><span data-stu-id="98d50-273">Allowed Values</span></span>
<span data-ttu-id="98d50-274">無限大、NaN、-無限大、-0</span><span class="sxs-lookup"><span data-stu-id="98d50-274">Infinity, NaN, -Infinity, -0</span></span>
</p>

---

### <a name="remoteobject"></a> <span data-ttu-id="98d50-275">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="98d50-275">RemoteObject</span></span> `object`

<span data-ttu-id="98d50-276">元の JavaScript オブジェクトを参照する Mirror オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98d50-276">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-277">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-277">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-278">型</span><span class="sxs-lookup"><span data-stu-id="98d50-278">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="98d50-279">使用できる値: object、関数、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="98d50-279">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="98d50-280">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="98d50-280">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-281">subtype</span><span class="sxs-lookup"><span data-stu-id="98d50-281">subtype</span></span> <br/> <i><span data-ttu-id="98d50-282">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-282">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="98d50-283">許可される値: null、エラー、promise、ノード</span><span class="sxs-lookup"><span data-stu-id="98d50-283">Allowed values: null, error, promise, node</span></span></i></td>
            <td><span data-ttu-id="98d50-284">オブジェクトサブタイプのヒント。</span><span class="sxs-lookup"><span data-stu-id="98d50-284">Object subtype hint.</span></span> <span data-ttu-id="98d50-285">型の値のみに指定され <code>object</code> ます。</span><span class="sxs-lookup"><span data-stu-id="98d50-285">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-286">名</span><span class="sxs-lookup"><span data-stu-id="98d50-286">className</span></span> <br/> <i><span data-ttu-id="98d50-287">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-287">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-288">オブジェクトクラス (コンストラクター) 名。</span><span class="sxs-lookup"><span data-stu-id="98d50-288">Object class (constructor) name.</span></span> <span data-ttu-id="98d50-289">型の値のみに指定され <code>object</code> ます。</span><span class="sxs-lookup"><span data-stu-id="98d50-289">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-290">value</span><span class="sxs-lookup"><span data-stu-id="98d50-290">value</span></span> <br/> <i><span data-ttu-id="98d50-291">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-291">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="98d50-292">プリミティブ値または JSON 値に応じたリモートオブジェクトの値 (要求された場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-292">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-293">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="98d50-293">unserializableValue</span></span> <br/> <i><span data-ttu-id="98d50-294">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-294">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="98d50-295">JSON 値は、JSON では使用できません。 stringified</span><span class="sxs-lookup"><span data-stu-id="98d50-295">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="98d50-296">が、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="98d50-296">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-297">description</span><span class="sxs-lookup"><span data-stu-id="98d50-297">description</span></span> <br/> <i><span data-ttu-id="98d50-298">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-298">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-299">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="98d50-299">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-300">objectId</span><span class="sxs-lookup"><span data-stu-id="98d50-300">objectId</span></span> <br/> <i><span data-ttu-id="98d50-301">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-301">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-302">一意のオブジェクト識別子 (プリミティブ以外の値の場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-302">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-303">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="98d50-303">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="98d50-304">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-304">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="98d50-305">的.</span><span class="sxs-lookup"><span data-stu-id="98d50-305">Experimental.</span></span> </b></span><span data-ttu-id="98d50-306">Microsoft: このオブジェクトに関連付けられているデバッガープロパティ id。</span><span class="sxs-lookup"><span data-stu-id="98d50-306">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="98d50-307">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="98d50-307">PropertyDescriptor</span></span> `object`

<span data-ttu-id="98d50-308">オブジェクトプロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="98d50-308">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-309">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-309">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-310">name</span><span class="sxs-lookup"><span data-stu-id="98d50-310">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-311">プロパティ名またはシンボルの説明。</span><span class="sxs-lookup"><span data-stu-id="98d50-311">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-312">value</span><span class="sxs-lookup"><span data-stu-id="98d50-312">value</span></span> <br/> <i><span data-ttu-id="98d50-313">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-313">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-314">プロパティに関連付けられた値。</span><span class="sxs-lookup"><span data-stu-id="98d50-314">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-315">書き</span><span class="sxs-lookup"><span data-stu-id="98d50-315">writable</span></span> <br/> <i><span data-ttu-id="98d50-316">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-316">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-317">プロパティに関連付けられている値が変更される可能性がある場合は True (データ記述子のみ)。</span><span class="sxs-lookup"><span data-stu-id="98d50-317">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-318">取得</span><span class="sxs-lookup"><span data-stu-id="98d50-318">get</span></span> <br/> <i><span data-ttu-id="98d50-319">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-319">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-320">プロパティの getter として機能する関数、または <code>undefined</code> getter (アクセサー記述子のみ) がない場合。</span><span class="sxs-lookup"><span data-stu-id="98d50-320">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-321">set</span><span class="sxs-lookup"><span data-stu-id="98d50-321">set</span></span> <br/> <i><span data-ttu-id="98d50-322">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-322">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-323">プロパティの setter として機能する関数、または <code>undefined</code> setter (アクセサー記述子のみ) がない場合。</span><span class="sxs-lookup"><span data-stu-id="98d50-323">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-324">構成</span><span class="sxs-lookup"><span data-stu-id="98d50-324">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-325">このプロパティ記述子の型が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合は True です。</span><span class="sxs-lookup"><span data-stu-id="98d50-325">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-326">加算</span><span class="sxs-lookup"><span data-stu-id="98d50-326">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-327">対応するオブジェクトのプロパティの列挙中にこのプロパティが表示される場合は True です。</span><span class="sxs-lookup"><span data-stu-id="98d50-327">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-328">例外</span><span class="sxs-lookup"><span data-stu-id="98d50-328">wasThrown</span></span> <br/> <i><span data-ttu-id="98d50-329">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-329">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-330">評価中に結果がスローされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="98d50-330">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-331">isOwn</span><span class="sxs-lookup"><span data-stu-id="98d50-331">isOwn</span></span> <br/> <i><span data-ttu-id="98d50-332">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-332">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="98d50-333">プロパティがそのオブジェクトに対して所有されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="98d50-333">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-334">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="98d50-334">msReturnValue</span></span> <br/> <i><span data-ttu-id="98d50-335">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-335">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="98d50-336">的.</span><span class="sxs-lookup"><span data-stu-id="98d50-336">Experimental.</span></span> </b></span><span data-ttu-id="98d50-337">Microsoft: プロパティが戻り値の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="98d50-337">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-338">symbol</span><span class="sxs-lookup"><span data-stu-id="98d50-338">symbol</span></span> <br/> <i><span data-ttu-id="98d50-339">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-339">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-340">プロパティが型の場合は、プロパティのシンボルオブジェクト `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="98d50-340">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> <span data-ttu-id="98d50-341">CallArgument</span><span class="sxs-lookup"><span data-stu-id="98d50-341">CallArgument</span></span> `object`

<span data-ttu-id="98d50-342">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="98d50-342">Represents function call argument.</span></span> <span data-ttu-id="98d50-343">リモートオブジェクト id <code>objectId</code> 、プリミティブ <code>value</code> 、unserializable プリミティブ値、またはどちらも指定しないようにします (未定義の場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-343">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-344">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-344">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-345">value</span><span class="sxs-lookup"><span data-stu-id="98d50-345">value</span></span> <br/> <i><span data-ttu-id="98d50-346">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-346">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="98d50-347">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98d50-347">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-348">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="98d50-348">unserializableValue</span></span> <br/> <i><span data-ttu-id="98d50-349">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-349">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="98d50-350">Stringified にすることができないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="98d50-350">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-351">objectId</span><span class="sxs-lookup"><span data-stu-id="98d50-351">objectId</span></span> <br/> <i><span data-ttu-id="98d50-352">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-352">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="98d50-353">リモートオブジェクトハンドル。</span><span class="sxs-lookup"><span data-stu-id="98d50-353">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="executioncontextid"></a> <span data-ttu-id="98d50-354">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="98d50-354">ExecutionContextId</span></span> `integer`

<span data-ttu-id="98d50-355">実行コンテキストの Id です。</span><span class="sxs-lookup"><span data-stu-id="98d50-355">Id of an execution context.</span></span>

</p>

---

### <a name="executioncontextdescription"></a> <span data-ttu-id="98d50-356">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="98d50-356">ExecutionContextDescription</span></span> `object`

<span data-ttu-id="98d50-357">分離世界の説明。</span><span class="sxs-lookup"><span data-stu-id="98d50-357">Description of an isolated world.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-358">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-358">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-359">id</span><span class="sxs-lookup"><span data-stu-id="98d50-359">id</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-360">実行コンテキストの一意の id。</span><span class="sxs-lookup"><span data-stu-id="98d50-360">Unique id of the execution context.</span></span> <span data-ttu-id="98d50-361">これは、実行コンテキストスクリプトの評価を実行することを指定するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="98d50-361">It can be used to specify in which execution context script evaluation should be performed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-362">cdn</span><span class="sxs-lookup"><span data-stu-id="98d50-362">origin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-363">実行コンテキストの起点。</span><span class="sxs-lookup"><span data-stu-id="98d50-363">Execution context origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-364">name</span><span class="sxs-lookup"><span data-stu-id="98d50-364">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-365">特定のコンテキストを説明する人間が読める名前。</span><span class="sxs-lookup"><span data-stu-id="98d50-365">Human readable name describing given context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> <span data-ttu-id="98d50-366">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="98d50-366">ExceptionDetails</span></span> `object`

<span data-ttu-id="98d50-367">スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="98d50-367">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-368">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-369">exceptionId</span><span class="sxs-lookup"><span data-stu-id="98d50-369">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="98d50-370">例外 id。</span><span class="sxs-lookup"><span data-stu-id="98d50-370">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-371">テキスト</span><span class="sxs-lookup"><span data-stu-id="98d50-371">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-372">例外テキスト。利用可能な場合は、exception オブジェクトと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-372">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-373">lineNumber</span><span class="sxs-lookup"><span data-stu-id="98d50-373">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="98d50-374">例外の場所 (0 ベース) の行番号。</span><span class="sxs-lookup"><span data-stu-id="98d50-374">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-375">列番号</span><span class="sxs-lookup"><span data-stu-id="98d50-375">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="98d50-376">例外の場所の列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="98d50-376">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-377">scriptId</span><span class="sxs-lookup"><span data-stu-id="98d50-377">scriptId</span></span> <br/> <i><span data-ttu-id="98d50-378">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-378">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="98d50-379">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="98d50-379">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-380">url</span><span class="sxs-lookup"><span data-stu-id="98d50-380">url</span></span> <br/> <i><span data-ttu-id="98d50-381">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-381">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-382">スクリプトが報告されなかったときに使用される、例外の場所の URL です。</span><span class="sxs-lookup"><span data-stu-id="98d50-382">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-383">stackTrace</span><span class="sxs-lookup"><span data-stu-id="98d50-383">stackTrace</span></span> <br/> <i><span data-ttu-id="98d50-384">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-384">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="98d50-385">JavaScript スタックトレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-385">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-386">エラー</span><span class="sxs-lookup"><span data-stu-id="98d50-386">exception</span></span> <br/> <i><span data-ttu-id="98d50-387">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-387">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="98d50-388">例外オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-388">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-389">executionContextId</span><span class="sxs-lookup"><span data-stu-id="98d50-389">executionContextId</span></span> <br/> <i><span data-ttu-id="98d50-390">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-390">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="98d50-391">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="98d50-391">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="timestamp"></a> <span data-ttu-id="98d50-392">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="98d50-392">Timestamp</span></span> `integer`

<span data-ttu-id="98d50-393">エポックからのミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="98d50-393">Number of milliseconds since epoch.</span></span>

</p>

---

### <a name="callframe"></a> <span data-ttu-id="98d50-394">CallFrame</span><span class="sxs-lookup"><span data-stu-id="98d50-394">CallFrame</span></span> `object`

<span data-ttu-id="98d50-395">実行時エラーとアサーションのスタックエントリ。</span><span class="sxs-lookup"><span data-stu-id="98d50-395">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-396">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-396">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-397">functionName</span><span class="sxs-lookup"><span data-stu-id="98d50-397">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-398">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="98d50-398">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-399">scriptId</span><span class="sxs-lookup"><span data-stu-id="98d50-399">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="98d50-400">JavaScript スクリプト id。デバッガーが有効になっていない場合は、ScriptId が空になります。</span><span class="sxs-lookup"><span data-stu-id="98d50-400">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-401">url</span><span class="sxs-lookup"><span data-stu-id="98d50-401">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-402">JavaScript スクリプト名または url。</span><span class="sxs-lookup"><span data-stu-id="98d50-402">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-403">lineNumber</span><span class="sxs-lookup"><span data-stu-id="98d50-403">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="98d50-404">JavaScript のスクリプト行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="98d50-404">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-405">列番号</span><span class="sxs-lookup"><span data-stu-id="98d50-405">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="98d50-406">JavaScript スクリプトの列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="98d50-406">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> <span data-ttu-id="98d50-407">StackTrace</span><span class="sxs-lookup"><span data-stu-id="98d50-407">StackTrace</span></span> `object`

<span data-ttu-id="98d50-408">アサーションまたはエラーメッセージのフレームを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="98d50-408">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="98d50-409">プロパティ</span><span class="sxs-lookup"><span data-stu-id="98d50-409">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="98d50-410">description</span><span class="sxs-lookup"><span data-stu-id="98d50-410">description</span></span> <br/> <i><span data-ttu-id="98d50-411">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-411">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="98d50-412">このスタックトレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="98d50-412">String label of this stack trace.</span></span> <span data-ttu-id="98d50-413">Async トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98d50-413">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-414">callFrames</span><span class="sxs-lookup"><span data-stu-id="98d50-414">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="98d50-415">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="98d50-415">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="98d50-416">所属</span><span class="sxs-lookup"><span data-stu-id="98d50-416">parent</span></span> <br/> <i><span data-ttu-id="98d50-417">オプション</span><span class="sxs-lookup"><span data-stu-id="98d50-417">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="98d50-418">このスタックの前にある非同期 JavaScript スタックトレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="98d50-418">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
