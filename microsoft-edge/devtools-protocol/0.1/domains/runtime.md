---
description: Runtime ドメインの参照。 ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
title: ランタイムドメイン-DevTools プロトコルバージョン0.1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 33bc98b272aaa8831e908207b97ea7d3d0842976
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569622"
---
# <span data-ttu-id="2d717-106">言語</span><span class="sxs-lookup"><span data-stu-id="2d717-106">Runtime</span></span>
<span data-ttu-id="2d717-107">ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="2d717-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="2d717-108">評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="2d717-109">元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="2d717-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d717-110">Methods</span></span>**](#methods) | <span data-ttu-id="2d717-111">[enable](#enable)、 [disable](#disable)、 [evaluate](#evaluate)、 [callfunctionon](#callfunctionon)、 [getProperties](#getproperties)</span><span class="sxs-lookup"><span data-stu-id="2d717-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span></span> |
| [**<span data-ttu-id="2d717-112">イベント</span><span class="sxs-lookup"><span data-stu-id="2d717-112">Events</span></span>**](#events) | <span data-ttu-id="2d717-113">[Executioncontextscleared](#executioncontextscleared)、 [exceptionthrown](#exceptionthrown)</span><span class="sxs-lookup"><span data-stu-id="2d717-113">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span></span> |
| [**<span data-ttu-id="2d717-114">型</span><span class="sxs-lookup"><span data-stu-id="2d717-114">Types</span></span>**](#types) | <span data-ttu-id="2d717-115">[Scriptid](#scriptid)、 [remoteobjectid](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [remoteobjectid](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [callargument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [exceptiondetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [callargument](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="2d717-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="2d717-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d717-116">Methods</span></span>

### <span data-ttu-id="2d717-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="2d717-117">enable</span></span>
<span data-ttu-id="2d717-118">イベントの報告を有効に <code>executionContextsCleared</code> します。</span><span class="sxs-lookup"><span data-stu-id="2d717-118">Enables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="2d717-119">[無効]</span><span class="sxs-lookup"><span data-stu-id="2d717-119">disable</span></span>
<span data-ttu-id="2d717-120">イベントの報告を無効に <code>executionContextsCleared</code> します。</span><span class="sxs-lookup"><span data-stu-id="2d717-120">Disables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="2d717-121">ぜひ</span><span class="sxs-lookup"><span data-stu-id="2d717-121">evaluate</span></span>
<span data-ttu-id="2d717-122">グローバルオブジェクトで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="2d717-122">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d717-123">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-124">expression</span><span class="sxs-lookup"><span data-stu-id="2d717-124">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-125">評価する式。</span><span class="sxs-lookup"><span data-stu-id="2d717-125">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-126">silent</span><span class="sxs-lookup"><span data-stu-id="2d717-126">silent</span></span> <br/> <i><span data-ttu-id="2d717-127">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-127">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-128">サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="2d717-128">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="2d717-129"><code>setPauseOnException</code>State の上書き。</span><span class="sxs-lookup"><span data-stu-id="2d717-129">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-130">contextId</span><span class="sxs-lookup"><span data-stu-id="2d717-130">contextId</span></span> <br/> <i><span data-ttu-id="2d717-131">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-131">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="2d717-132">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d717-132">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="2d717-133">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-133">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-134">returnByValue</span><span class="sxs-lookup"><span data-stu-id="2d717-134">returnByValue</span></span> <br/> <i><span data-ttu-id="2d717-135">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-135">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-136">結果が、値によって送信される必要がある JSON オブジェクトであると想定されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2d717-136">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-137">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="2d717-137">awaitPromise</span></span> <br/> <i><span data-ttu-id="2d717-138">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-138">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-139">結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2d717-139">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-140">返し</span><span class="sxs-lookup"><span data-stu-id="2d717-140">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-141">より</span><span class="sxs-lookup"><span data-stu-id="2d717-141">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-142">評価結果。</span><span class="sxs-lookup"><span data-stu-id="2d717-142">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2d717-143">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="2d717-143">callFunctionOn</span></span>
<span data-ttu-id="2d717-144">指定したオブジェクトで指定された宣言の関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2d717-144">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="2d717-145">結果のオブジェクトグループがターゲットオブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-145">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d717-146">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-147">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="2d717-147">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-148">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="2d717-148">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-149">objectId</span><span class="sxs-lookup"><span data-stu-id="2d717-149">objectId</span></span> <br/> <i><span data-ttu-id="2d717-150">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-150">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="2d717-151">呼び出す関数の対象となるオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="2d717-151">Identifier of the object to call function on.</span></span> <span data-ttu-id="2d717-152">ObjectId または executionContextId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d717-152">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="2d717-153">objectId は、evaluate () 関数からのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d717-153">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-154">arguments</span><span class="sxs-lookup"><span data-stu-id="2d717-154">arguments</span></span> <br/> <i><span data-ttu-id="2d717-155">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-155">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="2d717-156">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2d717-156">Call arguments.</span></span> <span data-ttu-id="2d717-157">すべての呼び出し引数は、ターゲットオブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d717-157">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-158">silent</span><span class="sxs-lookup"><span data-stu-id="2d717-158">silent</span></span> <br/> <i><span data-ttu-id="2d717-159">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-159">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-160">サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="2d717-160">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="2d717-161"><code>setPauseOnException</code>State の上書き。</span><span class="sxs-lookup"><span data-stu-id="2d717-161">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-162">returnByValue</span><span class="sxs-lookup"><span data-stu-id="2d717-162">returnByValue</span></span> <br/> <i><span data-ttu-id="2d717-163">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-163">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-164">結果が JSON オブジェクトであると想定されるかどうか。値で送信する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2d717-164">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-165">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="2d717-165">awaitPromise</span></span> <br/> <i><span data-ttu-id="2d717-166">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-167">結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2d717-167">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-168">返し</span><span class="sxs-lookup"><span data-stu-id="2d717-168">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-169">より</span><span class="sxs-lookup"><span data-stu-id="2d717-169">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-170">通話の結果。</span><span class="sxs-lookup"><span data-stu-id="2d717-170">Call result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="2d717-171">getProperties</span><span class="sxs-lookup"><span data-stu-id="2d717-171">getProperties</span></span>
<span data-ttu-id="2d717-172">指定されたオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="2d717-172">Returns properties of a given object.</span></span> <span data-ttu-id="2d717-173">結果のオブジェクトグループがターゲットオブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-173">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-174">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d717-174">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-175">objectId</span><span class="sxs-lookup"><span data-stu-id="2d717-175">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="2d717-176">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="2d717-176">Identifier of the object to return properties for.</span></span>  <span data-ttu-id="2d717-177">objectId はデバッガーからである必要があります。 evaluateOnCallFrame () 関数。</span><span class="sxs-lookup"><span data-stu-id="2d717-177">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-178">ownProperties</span><span class="sxs-lookup"><span data-stu-id="2d717-178">ownProperties</span></span> <br/> <i><span data-ttu-id="2d717-179">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-179">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-180">True の場合は、プロトタイプチェーンではなく、要素自体にのみ属しているプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="2d717-180">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-181">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="2d717-181">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="2d717-182">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-182">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="2d717-183">的.</span><span class="sxs-lookup"><span data-stu-id="2d717-183">Experimental.</span></span> </b></span><span data-ttu-id="2d717-184">True の場合は、アクセサープロパティ (getter/setter) のみを返します。内部プロパティは返されません。</span><span class="sxs-lookup"><span data-stu-id="2d717-184">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-185">返し</span><span class="sxs-lookup"><span data-stu-id="2d717-185">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-186">より</span><span class="sxs-lookup"><span data-stu-id="2d717-186">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="2d717-187">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2d717-187">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="2d717-188">イベント</span><span class="sxs-lookup"><span data-stu-id="2d717-188">Events</span></span>

### <span data-ttu-id="2d717-189">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="2d717-189">executionContextsCleared</span></span>
<span data-ttu-id="2d717-190">ブラウザーですべての executionContexts が消去されたときに発行される</span><span class="sxs-lookup"><span data-stu-id="2d717-190">Issued when all executionContexts were cleared in browser</span></span>


---

### <span data-ttu-id="2d717-191">例外のスロー</span><span class="sxs-lookup"><span data-stu-id="2d717-191">exceptionThrown</span></span>
<span data-ttu-id="2d717-192">例外がスローされて処理不能になったときに発行されます。</span><span class="sxs-lookup"><span data-stu-id="2d717-192">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-193">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d717-193">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-194">示</span><span class="sxs-lookup"><span data-stu-id="2d717-194">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="2d717-195">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="2d717-195">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-196">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="2d717-196">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="2d717-197">型</span><span class="sxs-lookup"><span data-stu-id="2d717-197">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="2d717-198">ScriptId</span><span class="sxs-lookup"><span data-stu-id="2d717-198">ScriptId</span></span> `string`

<span data-ttu-id="2d717-199">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="2d717-199">Unique script identifier.</span></span>


---

### <a name="remoteobjectid"></a> <span data-ttu-id="2d717-200">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="2d717-200">RemoteObjectId</span></span> `string`

<span data-ttu-id="2d717-201">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="2d717-201">Unique object identifier.</span></span>


---

### <a name="unserializablevalue"></a> <span data-ttu-id="2d717-202">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="2d717-202">UnserializableValue</span></span> `string`

<span data-ttu-id="2d717-203">Stringified にすることができないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="2d717-203">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="2d717-204">許可される値</span><span class="sxs-lookup"><span data-stu-id="2d717-204">Allowed Values</span></span>
<span data-ttu-id="2d717-205">無限大、NaN、-無限大、-0</span><span class="sxs-lookup"><span data-stu-id="2d717-205">Infinity, NaN, -Infinity, -0</span></span>

---

### <a name="remoteobject"></a> <span data-ttu-id="2d717-206">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="2d717-206">RemoteObject</span></span> `object`

<span data-ttu-id="2d717-207">元の JavaScript オブジェクトを参照する Mirror オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d717-207">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-208">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-208">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-209">型</span><span class="sxs-lookup"><span data-stu-id="2d717-209">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="2d717-210">使用できる値: object、関数、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="2d717-210">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="2d717-211">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="2d717-211">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-212">subtype</span><span class="sxs-lookup"><span data-stu-id="2d717-212">subtype</span></span> <br/> <i><span data-ttu-id="2d717-213">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-213">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="2d717-214">指定可能な値: null、エラー、promise</span><span class="sxs-lookup"><span data-stu-id="2d717-214">Allowed values: null, error, promise</span></span></i></td>
            <td><span data-ttu-id="2d717-215">オブジェクトサブタイプのヒント。</span><span class="sxs-lookup"><span data-stu-id="2d717-215">Object subtype hint.</span></span> <span data-ttu-id="2d717-216">型の値のみに指定され <code>object</code> ます。</span><span class="sxs-lookup"><span data-stu-id="2d717-216">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-217">名</span><span class="sxs-lookup"><span data-stu-id="2d717-217">className</span></span> <br/> <i><span data-ttu-id="2d717-218">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-218">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-219">オブジェクトクラス (コンストラクター) 名。</span><span class="sxs-lookup"><span data-stu-id="2d717-219">Object class (constructor) name.</span></span> <span data-ttu-id="2d717-220">型の値のみに指定され <code>object</code> ます。</span><span class="sxs-lookup"><span data-stu-id="2d717-220">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-221">value</span><span class="sxs-lookup"><span data-stu-id="2d717-221">value</span></span> <br/> <i><span data-ttu-id="2d717-222">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-222">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="2d717-223">プリミティブ値または JSON 値に応じたリモートオブジェクトの値 (要求された場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-223">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-224">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="2d717-224">unserializableValue</span></span> <br/> <i><span data-ttu-id="2d717-225">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-225">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="2d717-226">JSON 値は、JSON では使用できません。 stringified</span><span class="sxs-lookup"><span data-stu-id="2d717-226">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="2d717-227">が、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d717-227">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-228">description</span><span class="sxs-lookup"><span data-stu-id="2d717-228">description</span></span> <br/> <i><span data-ttu-id="2d717-229">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-229">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-230">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="2d717-230">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-231">objectId</span><span class="sxs-lookup"><span data-stu-id="2d717-231">objectId</span></span> <br/> <i><span data-ttu-id="2d717-232">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-232">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="2d717-233">一意のオブジェクト識別子 (プリミティブ以外の値の場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-233">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-234">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="2d717-234">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="2d717-235">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-235">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="2d717-236">的.</span><span class="sxs-lookup"><span data-stu-id="2d717-236">Experimental.</span></span> </b></span><span data-ttu-id="2d717-237">Microsoft: このオブジェクトに関連付けられているデバッガープロパティ id。</span><span class="sxs-lookup"><span data-stu-id="2d717-237">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="2d717-238">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="2d717-238">PropertyDescriptor</span></span> `object`

<span data-ttu-id="2d717-239">オブジェクトプロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="2d717-239">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-240">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-240">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-241">name</span><span class="sxs-lookup"><span data-stu-id="2d717-241">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-242">プロパティ名またはシンボルの説明。</span><span class="sxs-lookup"><span data-stu-id="2d717-242">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-243">value</span><span class="sxs-lookup"><span data-stu-id="2d717-243">value</span></span> <br/> <i><span data-ttu-id="2d717-244">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-244">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-245">プロパティに関連付けられた値。</span><span class="sxs-lookup"><span data-stu-id="2d717-245">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-246">書き</span><span class="sxs-lookup"><span data-stu-id="2d717-246">writable</span></span> <br/> <i><span data-ttu-id="2d717-247">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-247">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-248">プロパティに関連付けられている値が変更される可能性がある場合は True (データ記述子のみ)。</span><span class="sxs-lookup"><span data-stu-id="2d717-248">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-249">取得</span><span class="sxs-lookup"><span data-stu-id="2d717-249">get</span></span> <br/> <i><span data-ttu-id="2d717-250">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-250">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-251">プロパティの getter として機能する関数、または <code>undefined</code> getter (アクセサー記述子のみ) がない場合。</span><span class="sxs-lookup"><span data-stu-id="2d717-251">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-252">set</span><span class="sxs-lookup"><span data-stu-id="2d717-252">set</span></span> <br/> <i><span data-ttu-id="2d717-253">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-253">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-254">プロパティの setter として機能する関数、または <code>undefined</code> setter (アクセサー記述子のみ) がない場合。</span><span class="sxs-lookup"><span data-stu-id="2d717-254">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-255">構成</span><span class="sxs-lookup"><span data-stu-id="2d717-255">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-256">このプロパティ記述子の型が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2d717-256">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-257">加算</span><span class="sxs-lookup"><span data-stu-id="2d717-257">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-258">対応するオブジェクトのプロパティの列挙中にこのプロパティが表示される場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2d717-258">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-259">例外</span><span class="sxs-lookup"><span data-stu-id="2d717-259">wasThrown</span></span> <br/> <i><span data-ttu-id="2d717-260">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-260">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-261">評価中に結果がスローされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2d717-261">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-262">isOwn</span><span class="sxs-lookup"><span data-stu-id="2d717-262">isOwn</span></span> <br/> <i><span data-ttu-id="2d717-263">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-263">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="2d717-264">プロパティがそのオブジェクトに対して所有されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="2d717-264">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-265">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="2d717-265">msReturnValue</span></span> <br/> <i><span data-ttu-id="2d717-266">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-266">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="2d717-267">的.</span><span class="sxs-lookup"><span data-stu-id="2d717-267">Experimental.</span></span> </b></span><span data-ttu-id="2d717-268">Microsoft: プロパティが戻り値の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2d717-268">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-269">symbol</span><span class="sxs-lookup"><span data-stu-id="2d717-269">symbol</span></span> <br/> <i><span data-ttu-id="2d717-270">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-270">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-271">プロパティが型の場合は、プロパティのシンボルオブジェクト `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="2d717-271">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>

---

### <a name="callargument"></a> <span data-ttu-id="2d717-272">CallArgument</span><span class="sxs-lookup"><span data-stu-id="2d717-272">CallArgument</span></span> `object`

<span data-ttu-id="2d717-273">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="2d717-273">Represents function call argument.</span></span> <span data-ttu-id="2d717-274">リモートオブジェクト id <code>objectId</code> 、プリミティブ <code>value</code> 、unserializable プリミティブ値、またはどちらも指定しないようにします (未定義の場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-274">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-275">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-275">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-276">value</span><span class="sxs-lookup"><span data-stu-id="2d717-276">value</span></span> <br/> <i><span data-ttu-id="2d717-277">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-277">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="2d717-278">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d717-278">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-279">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="2d717-279">unserializableValue</span></span> <br/> <i><span data-ttu-id="2d717-280">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-280">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="2d717-281">Stringified にすることができないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="2d717-281">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-282">objectId</span><span class="sxs-lookup"><span data-stu-id="2d717-282">objectId</span></span> <br/> <i><span data-ttu-id="2d717-283">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-283">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="2d717-284">リモートオブジェクトハンドル。</span><span class="sxs-lookup"><span data-stu-id="2d717-284">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="executioncontextid"></a> <span data-ttu-id="2d717-285">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="2d717-285">ExecutionContextId</span></span> `integer`

<span data-ttu-id="2d717-286">実行コンテキストの Id です。</span><span class="sxs-lookup"><span data-stu-id="2d717-286">Id of an execution context.</span></span>


---

### <a name="exceptiondetails"></a> <span data-ttu-id="2d717-287">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="2d717-287">ExceptionDetails</span></span> `object`

<span data-ttu-id="2d717-288">スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="2d717-288">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-289">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-289">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-290">exceptionId</span><span class="sxs-lookup"><span data-stu-id="2d717-290">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2d717-291">例外 id。</span><span class="sxs-lookup"><span data-stu-id="2d717-291">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-292">テキスト</span><span class="sxs-lookup"><span data-stu-id="2d717-292">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-293">例外テキスト。利用可能な場合は、exception オブジェクトと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d717-293">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-294">lineNumber</span><span class="sxs-lookup"><span data-stu-id="2d717-294">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2d717-295">例外の場所 (0 ベース) の行番号。</span><span class="sxs-lookup"><span data-stu-id="2d717-295">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-296">列番号</span><span class="sxs-lookup"><span data-stu-id="2d717-296">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2d717-297">例外の場所の列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="2d717-297">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-298">scriptId</span><span class="sxs-lookup"><span data-stu-id="2d717-298">scriptId</span></span> <br/> <i><span data-ttu-id="2d717-299">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-299">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="2d717-300">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="2d717-300">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-301">url</span><span class="sxs-lookup"><span data-stu-id="2d717-301">url</span></span> <br/> <i><span data-ttu-id="2d717-302">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-302">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-303">スクリプトが報告されなかったときに使用される、例外の場所の URL です。</span><span class="sxs-lookup"><span data-stu-id="2d717-303">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-304">stackTrace</span><span class="sxs-lookup"><span data-stu-id="2d717-304">stackTrace</span></span> <br/> <i><span data-ttu-id="2d717-305">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-305">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="2d717-306">JavaScript スタックトレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-306">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-307">エラー</span><span class="sxs-lookup"><span data-stu-id="2d717-307">exception</span></span> <br/> <i><span data-ttu-id="2d717-308">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-308">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="2d717-309">例外オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-309">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-310">executionContextId</span><span class="sxs-lookup"><span data-stu-id="2d717-310">executionContextId</span></span> <br/> <i><span data-ttu-id="2d717-311">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-311">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="2d717-312">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="2d717-312">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="timestamp"></a> <span data-ttu-id="2d717-313">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="2d717-313">Timestamp</span></span> `integer`

<span data-ttu-id="2d717-314">エポックからのミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="2d717-314">Number of milliseconds since epoch.</span></span>


---

### <a name="callframe"></a> <span data-ttu-id="2d717-315">CallFrame</span><span class="sxs-lookup"><span data-stu-id="2d717-315">CallFrame</span></span> `object`

<span data-ttu-id="2d717-316">実行時エラーとアサーションのスタックエントリ。</span><span class="sxs-lookup"><span data-stu-id="2d717-316">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-317">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-317">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-318">functionName</span><span class="sxs-lookup"><span data-stu-id="2d717-318">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-319">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="2d717-319">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-320">scriptId</span><span class="sxs-lookup"><span data-stu-id="2d717-320">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="2d717-321">JavaScript スクリプト id。</span><span class="sxs-lookup"><span data-stu-id="2d717-321">JavaScript script id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-322">url</span><span class="sxs-lookup"><span data-stu-id="2d717-322">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-323">JavaScript スクリプト名または url。</span><span class="sxs-lookup"><span data-stu-id="2d717-323">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-324">lineNumber</span><span class="sxs-lookup"><span data-stu-id="2d717-324">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2d717-325">JavaScript のスクリプト行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="2d717-325">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-326">列番号</span><span class="sxs-lookup"><span data-stu-id="2d717-326">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="2d717-327">JavaScript スクリプトの列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="2d717-327">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="stacktrace"></a> <span data-ttu-id="2d717-328">StackTrace</span><span class="sxs-lookup"><span data-stu-id="2d717-328">StackTrace</span></span> `object`

<span data-ttu-id="2d717-329">アサーションまたはエラーメッセージのフレームを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2d717-329">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="2d717-330">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d717-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="2d717-331">description</span><span class="sxs-lookup"><span data-stu-id="2d717-331">description</span></span> <br/> <i><span data-ttu-id="2d717-332">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-332">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="2d717-333">このスタックトレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="2d717-333">String label of this stack trace.</span></span> <span data-ttu-id="2d717-334">Async トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d717-334">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-335">callFrames</span><span class="sxs-lookup"><span data-stu-id="2d717-335">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="2d717-336">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="2d717-336">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="2d717-337">所属</span><span class="sxs-lookup"><span data-stu-id="2d717-337">parent</span></span> <br/> <i><span data-ttu-id="2d717-338">オプション</span><span class="sxs-lookup"><span data-stu-id="2d717-338">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="2d717-339">このスタックの前にある非同期 JavaScript スタックトレース (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="2d717-339">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>

---
