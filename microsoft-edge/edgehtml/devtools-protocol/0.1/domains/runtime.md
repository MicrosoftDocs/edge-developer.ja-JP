---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 942a105199c8740fb7f7496b2a68e3eb0cc46fb4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234426"
---
# <span data-ttu-id="b972d-106">ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="b972d-106">Runtime Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="b972d-107">ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="b972d-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="b972d-108">評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b972d-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="b972d-109">元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="b972d-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="b972d-110">Methods</span></span>**](#methods) | <span data-ttu-id="b972d-111">[有効](#enable)、[無効、](#disable)[評価](#evaluate)[、callFunctionOn、getProperties](#callfunctionon) [](#getproperties)</span><span class="sxs-lookup"><span data-stu-id="b972d-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span></span> |
| [**<span data-ttu-id="b972d-112">イベント</span><span class="sxs-lookup"><span data-stu-id="b972d-112">Events</span></span>**](#events) | <span data-ttu-id="b972d-113">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span><span class="sxs-lookup"><span data-stu-id="b972d-113">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span></span> |
| [**<span data-ttu-id="b972d-114">型</span><span class="sxs-lookup"><span data-stu-id="b972d-114">Types</span></span>**](#types) | <span data-ttu-id="b972d-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="b972d-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="b972d-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="b972d-116">Methods</span></span>

### <span data-ttu-id="b972d-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="b972d-117">enable</span></span>
<span data-ttu-id="b972d-118">イベントのレポートを有効 <code>executionContextsCleared</code> にする。</span><span class="sxs-lookup"><span data-stu-id="b972d-118">Enables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="b972d-119">[無効]</span><span class="sxs-lookup"><span data-stu-id="b972d-119">disable</span></span>
<span data-ttu-id="b972d-120">イベントのレポートを無効 <code>executionContextsCleared</code> にします。</span><span class="sxs-lookup"><span data-stu-id="b972d-120">Disables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="b972d-121">evaluate</span><span class="sxs-lookup"><span data-stu-id="b972d-121">evaluate</span></span>
<span data-ttu-id="b972d-122">グローバル オブジェクトの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="b972d-122">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b972d-123">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-124">式</span><span class="sxs-lookup"><span data-stu-id="b972d-124">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-125">評価する式。</span><span class="sxs-lookup"><span data-stu-id="b972d-125">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-126">silent</span><span class="sxs-lookup"><span data-stu-id="b972d-126">silent</span></span> <br/> <i><span data-ttu-id="b972d-127">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-127">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-128">サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="b972d-128">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="b972d-129">状態を上書 <code>setPauseOnException</code> きします。</span><span class="sxs-lookup"><span data-stu-id="b972d-129">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-130">contextId</span><span class="sxs-lookup"><span data-stu-id="b972d-130">contextId</span></span> <br/> <i><span data-ttu-id="b972d-131">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-131">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="b972d-132">評価を実行する実行コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="b972d-132">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="b972d-133">パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-133">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-134">returnByValue</span><span class="sxs-lookup"><span data-stu-id="b972d-134">returnByValue</span></span> <br/> <i><span data-ttu-id="b972d-135">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-135">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-136">結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="b972d-136">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-137">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="b972d-137">awaitPromise</span></span> <br/> <i><span data-ttu-id="b972d-138">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-138">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-139">結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻るかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b972d-139">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-140">戻り値</span><span class="sxs-lookup"><span data-stu-id="b972d-140">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-141">result</span><span class="sxs-lookup"><span data-stu-id="b972d-141">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-142">評価結果。</span><span class="sxs-lookup"><span data-stu-id="b972d-142">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="b972d-143">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="b972d-143">callFunctionOn</span></span>
<span data-ttu-id="b972d-144">指定されたオブジェクトの特定の宣言を使用して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b972d-144">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="b972d-145">結果のオブジェクト グループはターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-145">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b972d-146">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-147">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="b972d-147">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-148">呼び出す関数の宣言。</span><span class="sxs-lookup"><span data-stu-id="b972d-148">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-149">objectId</span><span class="sxs-lookup"><span data-stu-id="b972d-149">objectId</span></span> <br/> <i><span data-ttu-id="b972d-150">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-150">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="b972d-151">関数を呼び出すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="b972d-151">Identifier of the object to call function on.</span></span> <span data-ttu-id="b972d-152">objectId または executionContextId のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-152">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="b972d-153">objectId は Runtime.evaluate() 関数の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-153">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-154">arguments</span><span class="sxs-lookup"><span data-stu-id="b972d-154">arguments</span></span> <br/> <i><span data-ttu-id="b972d-155">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-155">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="b972d-156">引数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b972d-156">Call arguments.</span></span> <span data-ttu-id="b972d-157">すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-157">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-158">silent</span><span class="sxs-lookup"><span data-stu-id="b972d-158">silent</span></span> <br/> <i><span data-ttu-id="b972d-159">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-159">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-160">サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="b972d-160">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="b972d-161">状態を上書 <code>setPauseOnException</code> きします。</span><span class="sxs-lookup"><span data-stu-id="b972d-161">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-162">returnByValue</span><span class="sxs-lookup"><span data-stu-id="b972d-162">returnByValue</span></span> <br/> <i><span data-ttu-id="b972d-163">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-163">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-164">結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="b972d-164">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-165">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="b972d-165">awaitPromise</span></span> <br/> <i><span data-ttu-id="b972d-166">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-167">結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻るかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b972d-167">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-168">戻り値</span><span class="sxs-lookup"><span data-stu-id="b972d-168">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-169">result</span><span class="sxs-lookup"><span data-stu-id="b972d-169">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-170">呼び出しの結果。</span><span class="sxs-lookup"><span data-stu-id="b972d-170">Call result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="b972d-171">getProperties</span><span class="sxs-lookup"><span data-stu-id="b972d-171">getProperties</span></span>
<span data-ttu-id="b972d-172">指定したオブジェクトのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="b972d-172">Returns properties of a given object.</span></span> <span data-ttu-id="b972d-173">結果のオブジェクト グループはターゲット オブジェクトから継承されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-173">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-174">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b972d-174">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-175">objectId</span><span class="sxs-lookup"><span data-stu-id="b972d-175">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="b972d-176">プロパティを返すオブジェクトの識別子。</span><span class="sxs-lookup"><span data-stu-id="b972d-176">Identifier of the object to return properties for.</span></span>  <span data-ttu-id="b972d-177">objectId は Debugger.evaluateOnCallFrame() 関数の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-177">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-178">ownProperties</span><span class="sxs-lookup"><span data-stu-id="b972d-178">ownProperties</span></span> <br/> <i><span data-ttu-id="b972d-179">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-179">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-180">true の場合、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="b972d-180">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-181">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="b972d-181">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="b972d-182">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-182">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="b972d-183">試験的。</span><span class="sxs-lookup"><span data-stu-id="b972d-183">Experimental.</span></span> </b></span><span data-ttu-id="b972d-184">true の場合、アクセサー プロパティ (getter/setter を使用) のみを返します。内部プロパティも返されません。</span><span class="sxs-lookup"><span data-stu-id="b972d-184">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-185">戻り値</span><span class="sxs-lookup"><span data-stu-id="b972d-185">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-186">result</span><span class="sxs-lookup"><span data-stu-id="b972d-186">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="b972d-187">オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b972d-187">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="b972d-188">イベント</span><span class="sxs-lookup"><span data-stu-id="b972d-188">Events</span></span>

### <span data-ttu-id="b972d-189">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="b972d-189">executionContextsCleared</span></span>
<span data-ttu-id="b972d-190">ブラウザーですべての executionContexts がクリアされた場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-190">Issued when all executionContexts were cleared in browser</span></span>


---

### <span data-ttu-id="b972d-191">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="b972d-191">exceptionThrown</span></span>
<span data-ttu-id="b972d-192">例外がスローされ、処理されない場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-192">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-193">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b972d-193">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-194">timestamp</span><span class="sxs-lookup"><span data-stu-id="b972d-194">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="b972d-195">例外のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="b972d-195">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-196">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="b972d-196">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="b972d-197">型</span><span class="sxs-lookup"><span data-stu-id="b972d-197">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="b972d-198">ScriptId</span><span class="sxs-lookup"><span data-stu-id="b972d-198">ScriptId</span></span> `string`

<span data-ttu-id="b972d-199">一意のスクリプト識別子。</span><span class="sxs-lookup"><span data-stu-id="b972d-199">Unique script identifier.</span></span>


---

### <a name="remoteobjectid"></a> <span data-ttu-id="b972d-200">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="b972d-200">RemoteObjectId</span></span> `string`

<span data-ttu-id="b972d-201">一意のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="b972d-201">Unique object identifier.</span></span>


---

### <a name="unserializablevalue"></a> <span data-ttu-id="b972d-202">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="b972d-202">UnserializableValue</span></span> `string`

<span data-ttu-id="b972d-203">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="b972d-203">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="b972d-204">使用できる値</span><span class="sxs-lookup"><span data-stu-id="b972d-204">Allowed Values</span></span>
<span data-ttu-id="b972d-205">Infinity、NaN、-Infinity、-0</span><span class="sxs-lookup"><span data-stu-id="b972d-205">Infinity, NaN, -Infinity, -0</span></span>

---

### <a name="remoteobject"></a> <span data-ttu-id="b972d-206">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="b972d-206">RemoteObject</span></span> `object`

<span data-ttu-id="b972d-207">元の JavaScript オブジェクトを参照するミラー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b972d-207">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-208">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-208">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-209">型</span><span class="sxs-lookup"><span data-stu-id="b972d-209">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="b972d-210">有効な値: object、function、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="b972d-210">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="b972d-211">オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="b972d-211">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-212">subtype</span><span class="sxs-lookup"><span data-stu-id="b972d-212">subtype</span></span> <br/> <i><span data-ttu-id="b972d-213">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-213">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="b972d-214">使用できる値: null、error、promise</span><span class="sxs-lookup"><span data-stu-id="b972d-214">Allowed values: null, error, promise</span></span></i></td>
            <td><span data-ttu-id="b972d-215">オブジェクトサブタイプのヒント。</span><span class="sxs-lookup"><span data-stu-id="b972d-215">Object subtype hint.</span></span> <span data-ttu-id="b972d-216">型の値 <code>object</code> にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="b972d-216">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-217">className</span><span class="sxs-lookup"><span data-stu-id="b972d-217">className</span></span> <br/> <i><span data-ttu-id="b972d-218">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-218">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-219">オブジェクト クラス (コンストラクター) 名。</span><span class="sxs-lookup"><span data-stu-id="b972d-219">Object class (constructor) name.</span></span> <span data-ttu-id="b972d-220">型の値 <code>object</code> にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="b972d-220">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-221">value</span><span class="sxs-lookup"><span data-stu-id="b972d-221">value</span></span> <br/> <i><span data-ttu-id="b972d-222">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-222">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="b972d-223">プリミティブ値または JSON 値の場合のリモート オブジェクト値 (要求された場合)。</span><span class="sxs-lookup"><span data-stu-id="b972d-223">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-224">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="b972d-224">unserializableValue</span></span> <br/> <i><span data-ttu-id="b972d-225">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-225">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="b972d-226">JSON 文字列化できないプリミティブ値には、次の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b972d-226">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="b972d-227">が、このプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="b972d-227">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-228">description</span><span class="sxs-lookup"><span data-stu-id="b972d-228">description</span></span> <br/> <i><span data-ttu-id="b972d-229">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-229">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-230">オブジェクトの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="b972d-230">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-231">objectId</span><span class="sxs-lookup"><span data-stu-id="b972d-231">objectId</span></span> <br/> <i><span data-ttu-id="b972d-232">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-232">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="b972d-233">一意のオブジェクト識別子 (プリミティブ値以外の場合)。</span><span class="sxs-lookup"><span data-stu-id="b972d-233">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-234">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="b972d-234">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="b972d-235">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-235">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="b972d-236">試験的。</span><span class="sxs-lookup"><span data-stu-id="b972d-236">Experimental.</span></span> </b></span><span data-ttu-id="b972d-237">Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="b972d-237">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="b972d-238">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="b972d-238">PropertyDescriptor</span></span> `object`

<span data-ttu-id="b972d-239">オブジェクト プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="b972d-239">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-240">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-240">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-241">name</span><span class="sxs-lookup"><span data-stu-id="b972d-241">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-242">プロパティ名または記号の説明。</span><span class="sxs-lookup"><span data-stu-id="b972d-242">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-243">value</span><span class="sxs-lookup"><span data-stu-id="b972d-243">value</span></span> <br/> <i><span data-ttu-id="b972d-244">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-244">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-245">プロパティに関連付けられている値。</span><span class="sxs-lookup"><span data-stu-id="b972d-245">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-246">書き込み可能</span><span class="sxs-lookup"><span data-stu-id="b972d-246">writable</span></span> <br/> <i><span data-ttu-id="b972d-247">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-247">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-248">True の 場合は、プロパティに関連付けられている値が変更される可能性があります (データ記述子のみ)。</span><span class="sxs-lookup"><span data-stu-id="b972d-248">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-249">取得</span><span class="sxs-lookup"><span data-stu-id="b972d-249">get</span></span> <br/> <i><span data-ttu-id="b972d-250">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-250">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-251">プロパティの getter として機能する関数、または getter がない場合 (アクセサー記述子 <code>undefined</code> のみ)。</span><span class="sxs-lookup"><span data-stu-id="b972d-251">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-252">set</span><span class="sxs-lookup"><span data-stu-id="b972d-252">set</span></span> <br/> <i><span data-ttu-id="b972d-253">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-253">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-254">プロパティのセッターとして機能する関数、または setter がない場合 (アクセサー <code>undefined</code> 記述子のみ)。</span><span class="sxs-lookup"><span data-stu-id="b972d-254">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-255">構成可能</span><span class="sxs-lookup"><span data-stu-id="b972d-255">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-256">True の 場合は、このプロパティ記述子の型が変更され、対応するオブジェクトからプロパティが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-256">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-257">enumerable</span><span class="sxs-lookup"><span data-stu-id="b972d-257">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-258">True の 場合、このプロパティは、対応するオブジェクトのプロパティの列挙中に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b972d-258">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-259">wasThrown</span><span class="sxs-lookup"><span data-stu-id="b972d-259">wasThrown</span></span> <br/> <i><span data-ttu-id="b972d-260">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-260">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-261">True の 場合は、評価中に結果がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b972d-261">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-262">isOwn</span><span class="sxs-lookup"><span data-stu-id="b972d-262">isOwn</span></span> <br/> <i><span data-ttu-id="b972d-263">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-263">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="b972d-264">True の 場合は、オブジェクトのプロパティが所有されています。</span><span class="sxs-lookup"><span data-stu-id="b972d-264">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-265">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="b972d-265">msReturnValue</span></span> <br/> <i><span data-ttu-id="b972d-266">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-266">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="b972d-267">試験的。</span><span class="sxs-lookup"><span data-stu-id="b972d-267">Experimental.</span></span> </b></span><span data-ttu-id="b972d-268">Microsoft: プロパティが戻り値の場合は True。</span><span class="sxs-lookup"><span data-stu-id="b972d-268">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-269">symbol</span><span class="sxs-lookup"><span data-stu-id="b972d-269">symbol</span></span> <br/> <i><span data-ttu-id="b972d-270">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-270">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-271">プロパティが型の場合、プロパティ シンボル `symbol` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b972d-271">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>

---

### <a name="callargument"></a> <span data-ttu-id="b972d-272">CallArgument</span><span class="sxs-lookup"><span data-stu-id="b972d-272">CallArgument</span></span> `object`

<span data-ttu-id="b972d-273">関数呼び出しの引数を表します。</span><span class="sxs-lookup"><span data-stu-id="b972d-273">Represents function call argument.</span></span> <span data-ttu-id="b972d-274">リモート オブジェクト ID、プリミティブ、読み取りできないプリミティブ値、または <code>objectId</code> <code>value</code> (未定義の場合) どちらも指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b972d-274">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-275">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-275">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-276">value</span><span class="sxs-lookup"><span data-stu-id="b972d-276">value</span></span> <br/> <i><span data-ttu-id="b972d-277">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-277">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="b972d-278">プリミティブ値またはシリアル化可能な javascript オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b972d-278">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-279">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="b972d-279">unserializableValue</span></span> <br/> <i><span data-ttu-id="b972d-280">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-280">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="b972d-281">JSON 文字列化できないプリミティブ値。</span><span class="sxs-lookup"><span data-stu-id="b972d-281">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-282">objectId</span><span class="sxs-lookup"><span data-stu-id="b972d-282">objectId</span></span> <br/> <i><span data-ttu-id="b972d-283">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-283">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="b972d-284">リモート オブジェクト ハンドル。</span><span class="sxs-lookup"><span data-stu-id="b972d-284">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="executioncontextid"></a> <span data-ttu-id="b972d-285">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="b972d-285">ExecutionContextId</span></span> `integer`

<span data-ttu-id="b972d-286">実行コンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="b972d-286">Id of an execution context.</span></span>


---

### <a name="exceptiondetails"></a> <span data-ttu-id="b972d-287">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="b972d-287">ExceptionDetails</span></span> `object`

<span data-ttu-id="b972d-288">スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。</span><span class="sxs-lookup"><span data-stu-id="b972d-288">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-289">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-289">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-290">exceptionId</span><span class="sxs-lookup"><span data-stu-id="b972d-290">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b972d-291">例外 ID。</span><span class="sxs-lookup"><span data-stu-id="b972d-291">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-292">テキスト</span><span class="sxs-lookup"><span data-stu-id="b972d-292">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-293">例外テキスト。利用可能な場合は例外オブジェクトと共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-293">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-294">lineNumber</span><span class="sxs-lookup"><span data-stu-id="b972d-294">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b972d-295">例外の場所の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="b972d-295">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-296">columnNumber</span><span class="sxs-lookup"><span data-stu-id="b972d-296">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b972d-297">例外の場所の列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="b972d-297">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-298">scriptId</span><span class="sxs-lookup"><span data-stu-id="b972d-298">scriptId</span></span> <br/> <i><span data-ttu-id="b972d-299">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-299">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="b972d-300">例外の場所のスクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="b972d-300">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-301">url</span><span class="sxs-lookup"><span data-stu-id="b972d-301">url</span></span> <br/> <i><span data-ttu-id="b972d-302">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-302">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-303">スクリプトが報告されていないときに使用される例外の場所の URL。</span><span class="sxs-lookup"><span data-stu-id="b972d-303">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-304">stackTrace</span><span class="sxs-lookup"><span data-stu-id="b972d-304">stackTrace</span></span> <br/> <i><span data-ttu-id="b972d-305">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-305">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="b972d-306">JavaScript スタック トレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="b972d-306">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-307">exception</span><span class="sxs-lookup"><span data-stu-id="b972d-307">exception</span></span> <br/> <i><span data-ttu-id="b972d-308">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-308">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="b972d-309">Exception オブジェクト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="b972d-309">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-310">executionContextId</span><span class="sxs-lookup"><span data-stu-id="b972d-310">executionContextId</span></span> <br/> <i><span data-ttu-id="b972d-311">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-311">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="b972d-312">例外が発生したコンテキストの識別子。</span><span class="sxs-lookup"><span data-stu-id="b972d-312">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="timestamp"></a> <span data-ttu-id="b972d-313">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="b972d-313">Timestamp</span></span> `integer`

<span data-ttu-id="b972d-314">エポックからのミリ秒単位の値です。</span><span class="sxs-lookup"><span data-stu-id="b972d-314">Number of milliseconds since epoch.</span></span>


---

### <a name="callframe"></a> <span data-ttu-id="b972d-315">CallFrame</span><span class="sxs-lookup"><span data-stu-id="b972d-315">CallFrame</span></span> `object`

<span data-ttu-id="b972d-316">ランタイム エラーとアサーションのスタック エントリ。</span><span class="sxs-lookup"><span data-stu-id="b972d-316">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-317">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-317">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-318">functionName</span><span class="sxs-lookup"><span data-stu-id="b972d-318">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-319">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="b972d-319">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-320">scriptId</span><span class="sxs-lookup"><span data-stu-id="b972d-320">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="b972d-321">JavaScript スクリプト ID。</span><span class="sxs-lookup"><span data-stu-id="b972d-321">JavaScript script id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-322">url</span><span class="sxs-lookup"><span data-stu-id="b972d-322">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-323">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="b972d-323">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-324">lineNumber</span><span class="sxs-lookup"><span data-stu-id="b972d-324">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b972d-325">JavaScript スクリプト行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="b972d-325">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-326">columnNumber</span><span class="sxs-lookup"><span data-stu-id="b972d-326">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="b972d-327">JavaScript スクリプトの列番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="b972d-327">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="stacktrace"></a> <span data-ttu-id="b972d-328">StackTrace</span><span class="sxs-lookup"><span data-stu-id="b972d-328">StackTrace</span></span> `object`

<span data-ttu-id="b972d-329">アサーションまたはエラー メッセージの呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="b972d-329">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b972d-330">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b972d-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b972d-331">description</span><span class="sxs-lookup"><span data-stu-id="b972d-331">description</span></span> <br/> <i><span data-ttu-id="b972d-332">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-332">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b972d-333">このスタック トレースの文字列ラベル。</span><span class="sxs-lookup"><span data-stu-id="b972d-333">String label of this stack trace.</span></span> <span data-ttu-id="b972d-334">非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b972d-334">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-335">callFrames</span><span class="sxs-lookup"><span data-stu-id="b972d-335">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="b972d-336">JavaScript 関数名。</span><span class="sxs-lookup"><span data-stu-id="b972d-336">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b972d-337">parent</span><span class="sxs-lookup"><span data-stu-id="b972d-337">parent</span></span> <br/> <i><span data-ttu-id="b972d-338">オプション</span><span class="sxs-lookup"><span data-stu-id="b972d-338">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="b972d-339">このスタックより前の非同期 JavaScript スタック トレース (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="b972d-339">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>

---
