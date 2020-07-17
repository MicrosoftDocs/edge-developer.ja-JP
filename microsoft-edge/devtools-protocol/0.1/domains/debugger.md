---
description: デバッガードメインの参照。 デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
title: デバッガドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1e76d17e5dfbe39ba61c7cb45a4e88b9fd223068
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882955"
---
# <span data-ttu-id="e987d-105">デバッガドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="e987d-105">Debugger Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  
  
<span data-ttu-id="e987d-106">デバッガードメインは、JavaScript のデバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="e987d-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="e987d-107">これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e987d-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="e987d-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="e987d-108">Methods</span></span>**](#methods) | <span data-ttu-id="e987d-109">[有効化](#enable)、[無効化](#disable)、 [getstepOut ブレークポイント](#getpossiblebreakpoints)、 [setbreakpointsactive](#setbreakpointsactive)、 [setbreakpointsactive](#setbreakpointbyurl)、 [setブレークポイント](#setbreakpoint)、 [removebreakpoint](#pause) [、curve、](#stepover) [stepinto](#stepinto)、 [removebreakpoint ポイント](#removebreakpoint)、[履歴書](#resume)、 [getpossiblebreakpoints](#getscriptsource)、 [setPauseOnExceptions](#setpauseonexceptions)、 [evalu](#evaluateoncallframe) [、](#stepout) [setblackboxpatterns](#setblackboxpatterns) [、](#setvariablevalue) [mssetデバッガ propertyvalue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="e987d-109">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |
| [**<span data-ttu-id="e987d-110">イベント</span><span class="sxs-lookup"><span data-stu-id="e987d-110">Events</span></span>**](#events) | <span data-ttu-id="e987d-111">[Scriptparsed 解析](#scriptparsed)、 [breakpointresolved 解決](#breakpointresolved)、[一時停止](#paused)、[再開](#resumed)</span><span class="sxs-lookup"><span data-stu-id="e987d-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |
| [**<span data-ttu-id="e987d-112">型</span><span class="sxs-lookup"><span data-stu-id="e987d-112">Types</span></span>**](#types) | <span data-ttu-id="e987d-113">[Breakpointid](#breakpointid)、[呼び出しフレーム id](#callframeid)、[位置](#location)、 [breaklocation](#breaklocation)、 [callframe](#callframe)、[スコープ](#scope)</span><span class="sxs-lookup"><span data-stu-id="e987d-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |
| [**<span data-ttu-id="e987d-114">依存関係</span><span class="sxs-lookup"><span data-stu-id="e987d-114">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="e987d-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e987d-115">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="e987d-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="e987d-116">Methods</span></span>

### <span data-ttu-id="e987d-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="e987d-117">enable</span></span>
<span data-ttu-id="e987d-118">指定したページに対してデバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e987d-118">Enables debugger for the given page.</span></span> <span data-ttu-id="e987d-119">クライアントは、このコマンドの結果が受信されるまで、デバッグが有効になっていると想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e987d-119">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>


---

### <span data-ttu-id="e987d-120">[無効]</span><span class="sxs-lookup"><span data-stu-id="e987d-120">disable</span></span>
<span data-ttu-id="e987d-121">指定されたページのデバッガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e987d-121">Disables debugger for given page.</span></span>


---

### <span data-ttu-id="e987d-122">Getのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e987d-122">getPossibleBreakpoints</span></span>
<span data-ttu-id="e987d-123">ブレークポイントで可能な場所を返します。</span><span class="sxs-lookup"><span data-stu-id="e987d-123">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="e987d-124">開始と終了の範囲の場所の scriptId は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e987d-124">scriptId in start and end range locations should be the same.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-125">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-126">start</span><span class="sxs-lookup"><span data-stu-id="e987d-126">start</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-127">範囲の先頭から、ブレークポイントの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="e987d-127">Start of range to search possible breakpoint locations in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-128">終了</span><span class="sxs-lookup"><span data-stu-id="e987d-128">end</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-129">[範囲の終わり] は、使用可能なブレークポイントの場所 (除外) を検索します。</span><span class="sxs-lookup"><span data-stu-id="e987d-129">End of range to search possible breakpoint locations in (excluding).</span></span> <span data-ttu-id="e987d-130">指定しない場合、スクリプトの末尾が範囲の末尾として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e987d-130">When not specified, end of scripts is used as end of range.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-131">返し</span><span class="sxs-lookup"><span data-stu-id="e987d-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-132">場所</span><span class="sxs-lookup"><span data-stu-id="e987d-132">locations</span></span></td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td><span data-ttu-id="e987d-133">可能なブレークポイントの場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="e987d-133">List of the possible breakpoint locations.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-134">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="e987d-134">setBreakpointsActive</span></span>
<span data-ttu-id="e987d-135">ページのすべてのブレークポイントをアクティブ化または非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="e987d-135">Activates / deactivates all breakpoints on the page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-136">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-137">active</span><span class="sxs-lookup"><span data-stu-id="e987d-137">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e987d-138">ブレークポイントのアクティブな状態の新しい値。</span><span class="sxs-lookup"><span data-stu-id="e987d-138">New value for breakpoints active state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-139">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="e987d-139">setBreakpointByUrl</span></span>
<span data-ttu-id="e987d-140">URL または URL regex で指定された場所に JavaScript のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="e987d-140">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span> <span data-ttu-id="e987d-141">このコマンドを発行すると、既に解析されているすべてのスクリプトのブレークポイントが解決され、プロパティに返され <code>locations</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e987d-141">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in <code>locations</code> property.</span></span> <span data-ttu-id="e987d-142">さらに一致するスクリプトの解析により、後続のイベントが発行され <code>breakpointResolved</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e987d-142">Further matching script parsing will result in subsequent <code>breakpointResolved</code> events issued.</span></span> <span data-ttu-id="e987d-143">この論理ブレークポイントは、ページの読み込みを維持します。</span><span class="sxs-lookup"><span data-stu-id="e987d-143">This logical breakpoint will survive page reloads.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-144">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-145">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e987d-145">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-146">ブレークポイントを設定する行番号。</span><span class="sxs-lookup"><span data-stu-id="e987d-146">Line number to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-147">url</span><span class="sxs-lookup"><span data-stu-id="e987d-147">url</span></span> <br/> <i><span data-ttu-id="e987d-148">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-148">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-149">ブレークポイントを設定するリソースの URL です。</span><span class="sxs-lookup"><span data-stu-id="e987d-149">URL of the resources to set breakpoint on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-150">urlRegex</span><span class="sxs-lookup"><span data-stu-id="e987d-150">urlRegex</span></span> <br/> <i><span data-ttu-id="e987d-151">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-151">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-152">ブレークポイントを設定するリソースの Url の Regex パターン。</span><span class="sxs-lookup"><span data-stu-id="e987d-152">Regex pattern for the URLs of the resources to set breakpoints on.</span></span> <span data-ttu-id="e987d-153"><code>url</code>またはどちらか <code>urlRegex</code> を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e987d-153">Either <code>url</code> or <code>urlRegex</code> must be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-154">列番号</span><span class="sxs-lookup"><span data-stu-id="e987d-154">columnNumber</span></span> <br/> <i><span data-ttu-id="e987d-155">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-155">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-156">ブレークポイントを設定する行のオフセット。</span><span class="sxs-lookup"><span data-stu-id="e987d-156">Offset in the line to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-157">条件</span><span class="sxs-lookup"><span data-stu-id="e987d-157">condition</span></span> <br/> <i><span data-ttu-id="e987d-158">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-158">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-159">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="e987d-159">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="e987d-160">指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="e987d-160">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-161">返し</span><span class="sxs-lookup"><span data-stu-id="e987d-161">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-162">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e987d-162">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="e987d-163">追加で参照するために作成したブレークポイントの Id です。</span><span class="sxs-lookup"><span data-stu-id="e987d-163">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-164">場所</span><span class="sxs-lookup"><span data-stu-id="e987d-164">locations</span></span></td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td><span data-ttu-id="e987d-165">このブレークポイントが追加されたときに解決される場所の一覧です。</span><span class="sxs-lookup"><span data-stu-id="e987d-165">List of the locations this breakpoint resolved into upon addition.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-166">setBreakpoint ポイント</span><span class="sxs-lookup"><span data-stu-id="e987d-166">setBreakpoint</span></span>
<span data-ttu-id="e987d-167">JavaScript のブレークポイントを特定の場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="e987d-167">Sets JavaScript breakpoint at a given location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-168">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-168">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-169">元</span><span class="sxs-lookup"><span data-stu-id="e987d-169">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-170">ブレークポイントを設定する場所。</span><span class="sxs-lookup"><span data-stu-id="e987d-170">Location to set breakpoint in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-171">条件</span><span class="sxs-lookup"><span data-stu-id="e987d-171">condition</span></span> <br/> <i><span data-ttu-id="e987d-172">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-172">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-173">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="e987d-173">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="e987d-174">指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="e987d-174">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-175">返し</span><span class="sxs-lookup"><span data-stu-id="e987d-175">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-176">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e987d-176">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="e987d-177">追加で参照するために作成したブレークポイントの Id です。</span><span class="sxs-lookup"><span data-stu-id="e987d-177">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-178">作動時の割り当て</span><span class="sxs-lookup"><span data-stu-id="e987d-178">actualLocation</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-179">このブレークポイントが解決される場所。</span><span class="sxs-lookup"><span data-stu-id="e987d-179">Location this breakpoint resolved into.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-180">removeBreakpoint ポイント</span><span class="sxs-lookup"><span data-stu-id="e987d-180">removeBreakpoint</span></span>
<span data-ttu-id="e987d-181">JavaScript のブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="e987d-181">Removes JavaScript breakpoint.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-182">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-182">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-183">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e987d-183">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-184">パス</span><span class="sxs-lookup"><span data-stu-id="e987d-184">stepOver</span></span>
<span data-ttu-id="e987d-185">ステートメントの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e987d-185">Steps over the statement.</span></span>


---

### <span data-ttu-id="e987d-186">ステップイン</span><span class="sxs-lookup"><span data-stu-id="e987d-186">stepInto</span></span>
<span data-ttu-id="e987d-187">関数呼び出しの手順。</span><span class="sxs-lookup"><span data-stu-id="e987d-187">Steps into the function call.</span></span>


---

### <span data-ttu-id="e987d-188">stepOut</span><span class="sxs-lookup"><span data-stu-id="e987d-188">stepOut</span></span>
<span data-ttu-id="e987d-189">関数呼び出しの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e987d-189">Steps out of the function call.</span></span>


---

### <span data-ttu-id="e987d-190">pause</span><span class="sxs-lookup"><span data-stu-id="e987d-190">pause</span></span>
<span data-ttu-id="e987d-191">次の JavaScript ステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="e987d-191">Stops on the next JavaScript statement.</span></span>


---

### <span data-ttu-id="e987d-192">resume</span><span class="sxs-lookup"><span data-stu-id="e987d-192">resume</span></span>
<span data-ttu-id="e987d-193">JavaScript の実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="e987d-193">Resumes JavaScript execution.</span></span>


---

### <span data-ttu-id="e987d-194">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="e987d-194">getScriptSource</span></span>
<span data-ttu-id="e987d-195">指定された id のスクリプトのソースを返します。</span><span class="sxs-lookup"><span data-stu-id="e987d-195">Returns source for the script with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-196">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-196">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-197">scriptId</span><span class="sxs-lookup"><span data-stu-id="e987d-197">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="e987d-198">ソースを取得するスクリプトの Id です。</span><span class="sxs-lookup"><span data-stu-id="e987d-198">Id of the script to get source for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-199">返し</span><span class="sxs-lookup"><span data-stu-id="e987d-199">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-200">scriptSource</span><span class="sxs-lookup"><span data-stu-id="e987d-200">scriptSource</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-201">スクリプトソース。</span><span class="sxs-lookup"><span data-stu-id="e987d-201">Script source.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-202">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="e987d-202">setPauseOnExceptions</span></span>
<span data-ttu-id="e987d-203">例外の状態に対する一時停止を定義します。</span><span class="sxs-lookup"><span data-stu-id="e987d-203">Defines pause on exceptions state.</span></span> <span data-ttu-id="e987d-204">すべての例外、不明な例外、または例外を停止するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e987d-204">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span> <span data-ttu-id="e987d-205">例外の状態での最初の一時停止 <code>none</code> 。</span><span class="sxs-lookup"><span data-stu-id="e987d-205">Initial pause on exceptions state is <code>none</code>.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-207">州</span><span class="sxs-lookup"><span data-stu-id="e987d-207">state</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="e987d-208">許可される値: なし、不明、すべて</span><span class="sxs-lookup"><span data-stu-id="e987d-208">Allowed values: none, uncaught, all</span></span></i></td>
            <td><span data-ttu-id="e987d-209">例外モードで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="e987d-209">Pause on exceptions mode.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-210">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="e987d-210">evaluateOnCallFrame</span></span>
<span data-ttu-id="e987d-211">指定した呼び出しフレームで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="e987d-211">Evaluates expression on a given call frame.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-212">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-212">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-213">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="e987d-213">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="e987d-214">を評価するために、フレーム識別子を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e987d-214">Call frame identifier to evaluate on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-215">expression</span><span class="sxs-lookup"><span data-stu-id="e987d-215">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-216">評価する式。</span><span class="sxs-lookup"><span data-stu-id="e987d-216">Expression to evaluate.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-217">返し</span><span class="sxs-lookup"><span data-stu-id="e987d-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-218">より</span><span class="sxs-lookup"><span data-stu-id="e987d-218">result</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="e987d-219">評価結果のオブジェクトラッパー。</span><span class="sxs-lookup"><span data-stu-id="e987d-219">Object wrapper for the evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-220">Set変数値</span><span class="sxs-lookup"><span data-stu-id="e987d-220">setVariableValue</span></span>
<span data-ttu-id="e987d-221">Callframe の変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="e987d-221">Changes value of variable in a callframe.</span></span> <span data-ttu-id="e987d-222">オブジェクトベースのスコープはサポートされていないため、手動で手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e987d-222">Object-based scopes are not supported and must be mutated manually.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-223">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-223">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-224">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="e987d-224">scopeNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-225">0ベースのスコープの数がスコープチェーンに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="e987d-225">0-based number of scope as was listed in scope chain.</span></span> <span data-ttu-id="e987d-226">"Local"、"クロージャ"、"catch" のスコープ型のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e987d-226">Only 'local', 'closure' and 'catch' scope types are allowed.</span></span> <span data-ttu-id="e987d-227">その他のスコープは手動で操作できます。</span><span class="sxs-lookup"><span data-stu-id="e987d-227">Other scopes could be manipulated manually.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-228">variableName</span><span class="sxs-lookup"><span data-stu-id="e987d-228">variableName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-229">変数名。</span><span class="sxs-lookup"><span data-stu-id="e987d-229">Variable name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-230">newValue</span><span class="sxs-lookup"><span data-stu-id="e987d-230">newValue</span></span></td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td><span data-ttu-id="e987d-231">新しい変数値。</span><span class="sxs-lookup"><span data-stu-id="e987d-231">New variable value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-232">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="e987d-232">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="e987d-233">変数を保持する callframe の Id です。</span><span class="sxs-lookup"><span data-stu-id="e987d-233">Id of callframe that holds variable.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-234">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="e987d-234">setBlackboxPatterns</span></span>
<span><b><span data-ttu-id="e987d-235">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-235">Experimental.</span></span> </b></span><span data-ttu-id="e987d-236">前の blackbox パターンを、渡されたものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e987d-236">Replace previous blackbox patterns with passed ones.</span></span> <span data-ttu-id="e987d-237">すべてのパターンに一致する url を持つスクリプトのステップ/一時停止をスキップするようにバックエンドに強制します。</span><span class="sxs-lookup"><span data-stu-id="e987d-237">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span> <span data-ttu-id="e987d-238">デバッガーは、"ステップイン" を複数回実行して、ブラックボックススクリプトを終了しようとします。最後に、失敗した場合は、"ステップアウト" に従います。</span><span class="sxs-lookup"><span data-stu-id="e987d-238">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-240">傾向</span><span class="sxs-lookup"><span data-stu-id="e987d-240">patterns</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="e987d-241">Blackbox の状態のスクリプト url を確認するために使用される regexps の配列です。</span><span class="sxs-lookup"><span data-stu-id="e987d-241">Array of regexps that will be used to check script url for blackbox state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-242">Mssetデバッガ Propertyvalue</span><span class="sxs-lookup"><span data-stu-id="e987d-242">msSetDebuggerPropertyValue</span></span>
<span><b><span data-ttu-id="e987d-243">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-243">Experimental.</span></span> </b></span><span data-ttu-id="e987d-244">Microsoft: 指定された debugger プロパティを指定された値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e987d-244">Microsoft: Sets the specified debugger property to the specified value.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-245">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-246">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="e987d-246">debuggerPropertyId</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-247">Microsoft: プロパティ id (msDebuggerPropertyId など) を設定します。</span><span class="sxs-lookup"><span data-stu-id="e987d-247">Microsoft: The property id (i.e. msDebuggerPropertyId) to set.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-248">newValue</span><span class="sxs-lookup"><span data-stu-id="e987d-248">newValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="e987d-249">イベント</span><span class="sxs-lookup"><span data-stu-id="e987d-249">Events</span></span>

### <span data-ttu-id="e987d-250">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="e987d-250">scriptParsed</span></span>
<span data-ttu-id="e987d-251">スクリプトの解析時に発生します。</span><span class="sxs-lookup"><span data-stu-id="e987d-251">Fired when the script is parsed.</span></span> <span data-ttu-id="e987d-252">このイベントは、デバッガーを有効にしているときに、既知の収集されていないすべてのスクリプトに対しても発生します。</span><span class="sxs-lookup"><span data-stu-id="e987d-252">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-253">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-254">scriptId</span><span class="sxs-lookup"><span data-stu-id="e987d-254">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="e987d-255">解析されたスクリプトの識別子。</span><span class="sxs-lookup"><span data-stu-id="e987d-255">Identifier of the script parsed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-256">url</span><span class="sxs-lookup"><span data-stu-id="e987d-256">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-257">解析されたスクリプトの URL または名前 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="e987d-257">URL or name of the script parsed (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-258">startLine</span><span class="sxs-lookup"><span data-stu-id="e987d-258">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-259">指定した URL のリソース内のスクリプトの行オフセット (スクリプトタグの場合)。</span><span class="sxs-lookup"><span data-stu-id="e987d-259">Line offset of the script within the resource with given URL (for script tags).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-260">startColumn</span><span class="sxs-lookup"><span data-stu-id="e987d-260">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-261">指定した URL のリソース内のスクリプトの列オフセット。</span><span class="sxs-lookup"><span data-stu-id="e987d-261">Column offset of the script within the resource with given URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-262">endLine</span><span class="sxs-lookup"><span data-stu-id="e987d-262">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-263">スクリプトの最終行。</span><span class="sxs-lookup"><span data-stu-id="e987d-263">Last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-264">endColumn</span><span class="sxs-lookup"><span data-stu-id="e987d-264">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-265">スクリプトの最後の行の長さ。</span><span class="sxs-lookup"><span data-stu-id="e987d-265">Length of the last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="e987d-266">executionContextId</span></span></td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td><span data-ttu-id="e987d-267">スクリプト作成コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="e987d-267">Specifies script creation context.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-268">sourceMapURL</span><span class="sxs-lookup"><span data-stu-id="e987d-268">sourceMapURL</span></span> <br/> <i><span data-ttu-id="e987d-269">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-269">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-270">スクリプト (存在する場合) に関連付けられたソースマップの URL。</span><span class="sxs-lookup"><span data-stu-id="e987d-270">URL of source map associated with script (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-271">全長</span><span class="sxs-lookup"><span data-stu-id="e987d-271">length</span></span> <br/> <i><span data-ttu-id="e987d-272">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-272">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="e987d-273">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-273">Experimental.</span></span> </b></span><span data-ttu-id="e987d-274">このスクリプトの長さ。</span><span class="sxs-lookup"><span data-stu-id="e987d-274">This script length.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-275">msParentId</span><span class="sxs-lookup"><span data-stu-id="e987d-275">msParentId</span></span> <br/> <i><span data-ttu-id="e987d-276">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-276">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="e987d-277">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-277">Experimental.</span></span> </b></span><span data-ttu-id="e987d-278">これは親ドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="e987d-278">This is the parent document ID.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-279">msMimeType</span><span class="sxs-lookup"><span data-stu-id="e987d-279">msMimeType</span></span> <br/> <i><span data-ttu-id="e987d-280">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-280">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="e987d-281">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-281">Experimental.</span></span> </b></span><span data-ttu-id="e987d-282">Mime の種類です。</span><span class="sxs-lookup"><span data-stu-id="e987d-282">This is the mime type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-283">msIsDynamicCode</span><span class="sxs-lookup"><span data-stu-id="e987d-283">msIsDynamicCode</span></span> <br/> <i><span data-ttu-id="e987d-284">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-284">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="e987d-285">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-285">Experimental.</span></span> </b></span><span data-ttu-id="e987d-286">これは、動的コードであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e987d-286">This indicates whether it is dynamic code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-287">msLongDocumentId</span><span class="sxs-lookup"><span data-stu-id="e987d-287">msLongDocumentId</span></span> <br/> <i><span data-ttu-id="e987d-288">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-288">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="e987d-289">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-289">Experimental.</span></span> </b></span><span data-ttu-id="e987d-290">これは長いドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="e987d-290">This is the long document ID.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-291">breakpointResolved 解決</span><span class="sxs-lookup"><span data-stu-id="e987d-291">breakpointResolved</span></span>
<span data-ttu-id="e987d-292">ブレークポイントが実際のスクリプトと場所に解決されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e987d-292">Fired when breakpoint is resolved to an actual script and location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-293">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-293">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-294">breakpointId</span><span class="sxs-lookup"><span data-stu-id="e987d-294">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="e987d-295">ブレークポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e987d-295">Breakpoint unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-296">元</span><span class="sxs-lookup"><span data-stu-id="e987d-296">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-297">実際のブレークポイントの位置。</span><span class="sxs-lookup"><span data-stu-id="e987d-297">Actual breakpoint location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-298">msLength</span><span class="sxs-lookup"><span data-stu-id="e987d-298">msLength</span></span> <br/> <i><span data-ttu-id="e987d-299">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-299">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="e987d-300">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-300">Experimental.</span></span> </b></span><span data-ttu-id="e987d-301">Microsoft: ブレークポイントの場所のコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="e987d-301">Microsoft: Length of code (i.e. number of characters) at the breakpoint location.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-302">paused (一時停止)</span><span class="sxs-lookup"><span data-stu-id="e987d-302">paused</span></span>
<span data-ttu-id="e987d-303">デバッガーがブレークポイントまたは例外のために中断したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e987d-303">Fired when the debuggers breaks for a breakpoint or exception.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-304">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e987d-304">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-305">callFrames</span><span class="sxs-lookup"><span data-stu-id="e987d-305">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="e987d-306">呼び出しスタックが停止しました。</span><span class="sxs-lookup"><span data-stu-id="e987d-306">Call stack the debugger stopped on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-307">から</span><span class="sxs-lookup"><span data-stu-id="e987d-307">reason</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="e987d-308">許可される値: ブレークポイント、ステップ、例外、その他</span><span class="sxs-lookup"><span data-stu-id="e987d-308">Allowed values: breakpoint, step, exception, other</span></span></i></td>
            <td><span data-ttu-id="e987d-309">一時停止理由。</span><span class="sxs-lookup"><span data-stu-id="e987d-309">Pause reason.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-310">data</span><span class="sxs-lookup"><span data-stu-id="e987d-310">data</span></span> <br/> <i><span data-ttu-id="e987d-311">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-311">optional</span></span></i></td>
            <td><code class="flyout">object</code></td>
            <td><span data-ttu-id="e987d-312">ブレーク固有の補助プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e987d-312">Object containing break-specific auxiliary properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-313">ヒットブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e987d-313">hitBreakpoints</span></span> <br/> <i><span data-ttu-id="e987d-314">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-314">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="e987d-315">ブレークポイント Id のヒット</span><span class="sxs-lookup"><span data-stu-id="e987d-315">Hit breakpoints IDs</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e987d-316">復帰</span><span class="sxs-lookup"><span data-stu-id="e987d-316">resumed</span></span>
<span data-ttu-id="e987d-317">デバッガーの実行を再開したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e987d-317">Fired when the debugger resumes execution.</span></span>


---

## <span data-ttu-id="e987d-318">型</span><span class="sxs-lookup"><span data-stu-id="e987d-318">Types</span></span>

### <a name="breakpointid"></a> <span data-ttu-id="e987d-319">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="e987d-319">BreakpointId</span></span> `string`

<span data-ttu-id="e987d-320">ブレークポイント識別子。</span><span class="sxs-lookup"><span data-stu-id="e987d-320">Breakpoint identifier.</span></span>


---

### <a name="callframeid"></a> <span data-ttu-id="e987d-321">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="e987d-321">CallFrameId</span></span> `string`

<span data-ttu-id="e987d-322">通話フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="e987d-322">Call frame identifier.</span></span>


---

### <a name="location"></a> <span data-ttu-id="e987d-323">位置情報</span><span class="sxs-lookup"><span data-stu-id="e987d-323">Location</span></span> `object`

<span data-ttu-id="e987d-324">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="e987d-324">Location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-325">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e987d-325">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-326">scriptId</span><span class="sxs-lookup"><span data-stu-id="e987d-326">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="e987d-327">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="e987d-327">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-328">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e987d-328">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-329">スクリプト内の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="e987d-329">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-330">列番号</span><span class="sxs-lookup"><span data-stu-id="e987d-330">columnNumber</span></span> <br/> <i><span data-ttu-id="e987d-331">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-331">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-332">スクリプトの列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="e987d-332">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-333">msLength</span><span class="sxs-lookup"><span data-stu-id="e987d-333">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-334">Microsoft: この呼び出しフレームのコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="e987d-334">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> <span data-ttu-id="e987d-335">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="e987d-335">BreakLocation</span></span> `object`

<span data-ttu-id="e987d-336">ソースコード内の位置を中断します。</span><span class="sxs-lookup"><span data-stu-id="e987d-336">Break location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-337">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e987d-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-338">scriptId</span><span class="sxs-lookup"><span data-stu-id="e987d-338">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="e987d-339">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="e987d-339">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-340">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e987d-340">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-341">スクリプト内の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="e987d-341">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-342">列番号</span><span class="sxs-lookup"><span data-stu-id="e987d-342">columnNumber</span></span> <br/> <i><span data-ttu-id="e987d-343">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-343">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-344">スクリプトの列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="e987d-344">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-345">msLength</span><span class="sxs-lookup"><span data-stu-id="e987d-345">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e987d-346">Microsoft: この呼び出しフレームのコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="e987d-346">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-347">型</span><span class="sxs-lookup"><span data-stu-id="e987d-347">type</span></span> <br/> <i><span data-ttu-id="e987d-348">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-348">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-349">指定可能な値: デバッガステートメント、call、return。</span><span class="sxs-lookup"><span data-stu-id="e987d-349">Allowed values: debuggerStatement, call, return.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> <span data-ttu-id="e987d-350">CallFrame</span><span class="sxs-lookup"><span data-stu-id="e987d-350">CallFrame</span></span> `object`

<span data-ttu-id="e987d-351">JavaScript 呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="e987d-351">JavaScript call frame.</span></span> <span data-ttu-id="e987d-352">コールスタックは、呼び出しフレームの配列によって形成されます。</span><span class="sxs-lookup"><span data-stu-id="e987d-352">Array of call frames form the call stack.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-353">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e987d-353">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-354">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="e987d-354">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="e987d-355">通話フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="e987d-355">Call frame identifier.</span></span> <span data-ttu-id="e987d-356">この識別子は、デバッガーが一時停止されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e987d-356">This identifier is only valid while the debugger is paused.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-357">functionName</span><span class="sxs-lookup"><span data-stu-id="e987d-357">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-358">この呼び出しフレームで呼び出される JavaScript 関数の名前。</span><span class="sxs-lookup"><span data-stu-id="e987d-358">Name of the JavaScript function called on this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-359">関数の場所</span><span class="sxs-lookup"><span data-stu-id="e987d-359">functionLocation</span></span> <br/> <i><span data-ttu-id="e987d-360">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-360">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b><span data-ttu-id="e987d-361">的.</span><span class="sxs-lookup"><span data-stu-id="e987d-361">Experimental.</span></span> </b></span><span data-ttu-id="e987d-362">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="e987d-362">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-363">元</span><span class="sxs-lookup"><span data-stu-id="e987d-363">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-364">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="e987d-364">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-365">url</span><span class="sxs-lookup"><span data-stu-id="e987d-365">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e987d-366">JavaScript スクリプト名または url。</span><span class="sxs-lookup"><span data-stu-id="e987d-366">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-367">scopeChain</span><span class="sxs-lookup"><span data-stu-id="e987d-367">scopeChain</span></span></td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td><span data-ttu-id="e987d-368">この呼び出しフレームのスコープチェーン。</span><span class="sxs-lookup"><span data-stu-id="e987d-368">Scope chain for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-369">これ</span><span class="sxs-lookup"><span data-stu-id="e987d-369">this</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> <span data-ttu-id="e987d-370">この呼び出しフレームのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e987d-370">object for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-371">戻り</span><span class="sxs-lookup"><span data-stu-id="e987d-371">returnValue</span></span> <br/> <i><span data-ttu-id="e987d-372">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-372">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="e987d-373">返される値 (関数が戻り値の位置にある場合)。</span><span class="sxs-lookup"><span data-stu-id="e987d-373">The value being returned, if the function is at return point.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> <span data-ttu-id="e987d-374">適用範囲</span><span class="sxs-lookup"><span data-stu-id="e987d-374">Scope</span></span> `object`

<span data-ttu-id="e987d-375">スコープの説明。</span><span class="sxs-lookup"><span data-stu-id="e987d-375">Scope description.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e987d-376">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e987d-376">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e987d-377">型</span><span class="sxs-lookup"><span data-stu-id="e987d-377">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="e987d-378">許可される値: global、local、with、クロージャ、catch、block、script、eval、module</span><span class="sxs-lookup"><span data-stu-id="e987d-378">Allowed values: global, local, with, closure, catch, block, script, eval, module</span></span></i></td>
            <td><span data-ttu-id="e987d-379">スコープ型。</span><span class="sxs-lookup"><span data-stu-id="e987d-379">Scope type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-380">object</span><span class="sxs-lookup"><span data-stu-id="e987d-380">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="e987d-381">スコープを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e987d-381">Object representing the scope.</span></span> <span data-ttu-id="e987d-382"><code>global</code>And スコープは実際のオブジェクトを表し、スコープ <code>with</code> の残りの部分については、スコープ変数をプロパティとして列挙する人為的な一時的なオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e987d-382">For <code>global</code> and <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-383">name</span><span class="sxs-lookup"><span data-stu-id="e987d-383">name</span></span> <br/> <i><span data-ttu-id="e987d-384">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-384">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-385">startLocation</span><span class="sxs-lookup"><span data-stu-id="e987d-385">startLocation</span></span> <br/> <i><span data-ttu-id="e987d-386">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-386">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-387">スコープが開始されるソースコード内の場所</span><span class="sxs-lookup"><span data-stu-id="e987d-387">Location in the source code where scope starts</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e987d-388">endLocation</span><span class="sxs-lookup"><span data-stu-id="e987d-388">endLocation</span></span> <br/> <i><span data-ttu-id="e987d-389">オプション</span><span class="sxs-lookup"><span data-stu-id="e987d-389">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="e987d-390">スコープが終了するソースコード内の場所</span><span class="sxs-lookup"><span data-stu-id="e987d-390">Location in the source code where scope ends</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="e987d-391">依存関係</span><span class="sxs-lookup"><span data-stu-id="e987d-391">Dependencies</span></span>

[<span data-ttu-id="e987d-392">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e987d-392">Runtime</span></span>](runtime.md)