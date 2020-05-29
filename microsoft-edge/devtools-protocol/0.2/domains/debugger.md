---
description: デバッガードメインの参照。 デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
title: デバッガドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: de967b0e067bf43ea07f8975eac7ee7c5a4dfd83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569611"
---
# <span data-ttu-id="1e389-105">ブレーク</span><span class="sxs-lookup"><span data-stu-id="1e389-105">Debugger</span></span>
<span data-ttu-id="1e389-106">デバッガードメインは、JavaScript のデバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="1e389-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="1e389-107">これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1e389-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="1e389-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e389-108">Methods</span></span>**](#methods) | <span data-ttu-id="1e389-109">[有効化](#enable)、[無効化](#disable)、 [getstepOut ブレークポイント](#getpossiblebreakpoints)、 [setbreakpointsactive](#setbreakpointsactive)、 [setbreakpointsactive](#setbreakpointbyurl)、 [setブレークポイント](#setbreakpoint)、 [removebreakpoint](#pause) [、curve、](#stepover) [stepinto](#stepinto)、 [removebreakpoint ポイント](#removebreakpoint)、[履歴書](#resume)、 [getpossiblebreakpoints](#getscriptsource)、 [setPauseOnExceptions](#setpauseonexceptions)、 [evalu](#evaluateoncallframe) [、](#stepout) [setblackboxpatterns](#setblackboxpatterns) [、](#setvariablevalue) [mssetデバッガ propertyvalue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="1e389-109">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |
| [**<span data-ttu-id="1e389-110">イベント</span><span class="sxs-lookup"><span data-stu-id="1e389-110">Events</span></span>**](#events) | <span data-ttu-id="1e389-111">[Scriptparsed 解析](#scriptparsed)、 [breakpointresolved 解決](#breakpointresolved)、[一時停止](#paused)、[再開](#resumed)</span><span class="sxs-lookup"><span data-stu-id="1e389-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |
| [**<span data-ttu-id="1e389-112">型</span><span class="sxs-lookup"><span data-stu-id="1e389-112">Types</span></span>**](#types) | <span data-ttu-id="1e389-113">[Breakpointid](#breakpointid)、[呼び出しフレーム id](#callframeid)、[位置](#location)、 [breaklocation](#breaklocation)、 [callframe](#callframe)、[スコープ](#scope)</span><span class="sxs-lookup"><span data-stu-id="1e389-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |
| [**<span data-ttu-id="1e389-114">依存関係</span><span class="sxs-lookup"><span data-stu-id="1e389-114">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="1e389-115">言語</span><span class="sxs-lookup"><span data-stu-id="1e389-115">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="1e389-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e389-116">Methods</span></span>

### <span data-ttu-id="1e389-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="1e389-117">enable</span></span>
<span data-ttu-id="1e389-118">指定したページに対してデバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e389-118">Enables debugger for the given page.</span></span> <span data-ttu-id="1e389-119">クライアントは、このコマンドの結果が受信されるまで、デバッグが有効になっていると想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1e389-119">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>

</p>

---

### <span data-ttu-id="1e389-120">[無効]</span><span class="sxs-lookup"><span data-stu-id="1e389-120">disable</span></span>
<span data-ttu-id="1e389-121">指定されたページのデバッガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1e389-121">Disables debugger for given page.</span></span>

</p>

---

### <span data-ttu-id="1e389-122">Getのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="1e389-122">getPossibleBreakpoints</span></span>
<span data-ttu-id="1e389-123">ブレークポイントで可能な場所を返します。</span><span class="sxs-lookup"><span data-stu-id="1e389-123">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="1e389-124">開始と終了の範囲の場所の scriptId は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e389-124">scriptId in start and end range locations should be the same.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-125">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-126">start</span><span class="sxs-lookup"><span data-stu-id="1e389-126">start</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-127">範囲の先頭から、ブレークポイントの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="1e389-127">Start of range to search possible breakpoint locations in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-128">終了</span><span class="sxs-lookup"><span data-stu-id="1e389-128">end</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-129">[範囲の終わり] は、使用可能なブレークポイントの場所 (除外) を検索します。</span><span class="sxs-lookup"><span data-stu-id="1e389-129">End of range to search possible breakpoint locations in (excluding).</span></span> <span data-ttu-id="1e389-130">指定しない場合、スクリプトの末尾が範囲の末尾として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e389-130">When not specified, end of scripts is used as end of range.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-131">返し</span><span class="sxs-lookup"><span data-stu-id="1e389-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-132">場所</span><span class="sxs-lookup"><span data-stu-id="1e389-132">locations</span></span></td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td><span data-ttu-id="1e389-133">可能なブレークポイントの場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="1e389-133">List of the possible breakpoint locations.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-134">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="1e389-134">setBreakpointsActive</span></span>
<span data-ttu-id="1e389-135">ページのすべてのブレークポイントをアクティブ化または非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="1e389-135">Activates / deactivates all breakpoints on the page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-136">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-137">active</span><span class="sxs-lookup"><span data-stu-id="1e389-137">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="1e389-138">ブレークポイントのアクティブな状態の新しい値。</span><span class="sxs-lookup"><span data-stu-id="1e389-138">New value for breakpoints active state.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-139">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="1e389-139">setBreakpointByUrl</span></span>
<span data-ttu-id="1e389-140">URL または URL regex で指定された場所に JavaScript のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="1e389-140">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span> <span data-ttu-id="1e389-141">このコマンドを発行すると、既に解析されているすべてのスクリプトのブレークポイントが解決され、プロパティに返され <code>locations</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1e389-141">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in <code>locations</code> property.</span></span> <span data-ttu-id="1e389-142">さらに一致するスクリプトの解析により、後続のイベントが発行され <code>breakpointResolved</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1e389-142">Further matching script parsing will result in subsequent <code>breakpointResolved</code> events issued.</span></span> <span data-ttu-id="1e389-143">この論理ブレークポイントは、ページの読み込みを維持します。</span><span class="sxs-lookup"><span data-stu-id="1e389-143">This logical breakpoint will survive page reloads.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-144">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-145">lineNumber</span><span class="sxs-lookup"><span data-stu-id="1e389-145">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-146">ブレークポイントを設定する行番号。</span><span class="sxs-lookup"><span data-stu-id="1e389-146">Line number to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-147">url</span><span class="sxs-lookup"><span data-stu-id="1e389-147">url</span></span> <br/> <i><span data-ttu-id="1e389-148">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-148">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-149">ブレークポイントを設定するリソースの URL です。</span><span class="sxs-lookup"><span data-stu-id="1e389-149">URL of the resources to set breakpoint on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-150">urlRegex</span><span class="sxs-lookup"><span data-stu-id="1e389-150">urlRegex</span></span> <br/> <i><span data-ttu-id="1e389-151">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-151">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-152">ブレークポイントを設定するリソースの Url の Regex パターン。</span><span class="sxs-lookup"><span data-stu-id="1e389-152">Regex pattern for the URLs of the resources to set breakpoints on.</span></span> <span data-ttu-id="1e389-153"><code>url</code>またはどちらか <code>urlRegex</code> を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e389-153">Either <code>url</code> or <code>urlRegex</code> must be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-154">列番号</span><span class="sxs-lookup"><span data-stu-id="1e389-154">columnNumber</span></span> <br/> <i><span data-ttu-id="1e389-155">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-155">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-156">ブレークポイントを設定する行のオフセット。</span><span class="sxs-lookup"><span data-stu-id="1e389-156">Offset in the line to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-157">条件</span><span class="sxs-lookup"><span data-stu-id="1e389-157">condition</span></span> <br/> <i><span data-ttu-id="1e389-158">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-158">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-159">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="1e389-159">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="1e389-160">指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="1e389-160">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-161">返し</span><span class="sxs-lookup"><span data-stu-id="1e389-161">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-162">breakpointId</span><span class="sxs-lookup"><span data-stu-id="1e389-162">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="1e389-163">追加で参照するために作成したブレークポイントの Id です。</span><span class="sxs-lookup"><span data-stu-id="1e389-163">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-164">場所</span><span class="sxs-lookup"><span data-stu-id="1e389-164">locations</span></span></td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td><span data-ttu-id="1e389-165">このブレークポイントが追加されたときに解決される場所の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1e389-165">List of the locations this breakpoint resolved into upon addition.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-166">setBreakpoint ポイント</span><span class="sxs-lookup"><span data-stu-id="1e389-166">setBreakpoint</span></span>
<span data-ttu-id="1e389-167">JavaScript のブレークポイントを特定の場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e389-167">Sets JavaScript breakpoint at a given location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-168">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-168">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-169">元</span><span class="sxs-lookup"><span data-stu-id="1e389-169">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-170">ブレークポイントを設定する場所。</span><span class="sxs-lookup"><span data-stu-id="1e389-170">Location to set breakpoint in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-171">条件</span><span class="sxs-lookup"><span data-stu-id="1e389-171">condition</span></span> <br/> <i><span data-ttu-id="1e389-172">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-172">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-173">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="1e389-173">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="1e389-174">指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="1e389-174">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-175">返し</span><span class="sxs-lookup"><span data-stu-id="1e389-175">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-176">breakpointId</span><span class="sxs-lookup"><span data-stu-id="1e389-176">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="1e389-177">追加で参照するために作成したブレークポイントの Id です。</span><span class="sxs-lookup"><span data-stu-id="1e389-177">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-178">作動時の割り当て</span><span class="sxs-lookup"><span data-stu-id="1e389-178">actualLocation</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-179">このブレークポイントが解決される場所。</span><span class="sxs-lookup"><span data-stu-id="1e389-179">Location this breakpoint resolved into.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-180">removeBreakpoint ポイント</span><span class="sxs-lookup"><span data-stu-id="1e389-180">removeBreakpoint</span></span>
<span data-ttu-id="1e389-181">JavaScript のブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e389-181">Removes JavaScript breakpoint.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-182">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-182">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-183">breakpointId</span><span class="sxs-lookup"><span data-stu-id="1e389-183">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-184">パス</span><span class="sxs-lookup"><span data-stu-id="1e389-184">stepOver</span></span>
<span data-ttu-id="1e389-185">ステートメントの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e389-185">Steps over the statement.</span></span>

</p>

---

### <span data-ttu-id="1e389-186">ステップイン</span><span class="sxs-lookup"><span data-stu-id="1e389-186">stepInto</span></span>
<span data-ttu-id="1e389-187">関数呼び出しの手順。</span><span class="sxs-lookup"><span data-stu-id="1e389-187">Steps into the function call.</span></span>

</p>

---

### <span data-ttu-id="1e389-188">stepOut</span><span class="sxs-lookup"><span data-stu-id="1e389-188">stepOut</span></span>
<span data-ttu-id="1e389-189">関数呼び出しの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e389-189">Steps out of the function call.</span></span>

</p>

---

### <span data-ttu-id="1e389-190">pause</span><span class="sxs-lookup"><span data-stu-id="1e389-190">pause</span></span>
<span data-ttu-id="1e389-191">次の JavaScript ステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="1e389-191">Stops on the next JavaScript statement.</span></span>

</p>

---

### <span data-ttu-id="1e389-192">resume</span><span class="sxs-lookup"><span data-stu-id="1e389-192">resume</span></span>
<span data-ttu-id="1e389-193">JavaScript の実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="1e389-193">Resumes JavaScript execution.</span></span>

</p>

---

### <span data-ttu-id="1e389-194">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="1e389-194">getScriptSource</span></span>
<span data-ttu-id="1e389-195">指定された id のスクリプトのソースを返します。</span><span class="sxs-lookup"><span data-stu-id="1e389-195">Returns source for the script with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-196">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-196">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-197">scriptId</span><span class="sxs-lookup"><span data-stu-id="1e389-197">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="1e389-198">ソースを取得するスクリプトの Id です。</span><span class="sxs-lookup"><span data-stu-id="1e389-198">Id of the script to get source for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-199">返し</span><span class="sxs-lookup"><span data-stu-id="1e389-199">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-200">scriptSource</span><span class="sxs-lookup"><span data-stu-id="1e389-200">scriptSource</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-201">スクリプトソース。</span><span class="sxs-lookup"><span data-stu-id="1e389-201">Script source.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-202">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="1e389-202">setPauseOnExceptions</span></span>
<span data-ttu-id="1e389-203">例外の状態に対する一時停止を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e389-203">Defines pause on exceptions state.</span></span> <span data-ttu-id="1e389-204">すべての例外、不明な例外、または例外を停止するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="1e389-204">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span> <span data-ttu-id="1e389-205">例外の状態での最初の一時停止 <code>none</code> 。</span><span class="sxs-lookup"><span data-stu-id="1e389-205">Initial pause on exceptions state is <code>none</code>.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-207">州</span><span class="sxs-lookup"><span data-stu-id="1e389-207">state</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="1e389-208">許可される値: なし、不明、すべて</span><span class="sxs-lookup"><span data-stu-id="1e389-208">Allowed values: none, uncaught, all</span></span></i></td>
            <td><span data-ttu-id="1e389-209">例外モードで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="1e389-209">Pause on exceptions mode.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-210">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="1e389-210">evaluateOnCallFrame</span></span>
<span data-ttu-id="1e389-211">指定した呼び出しフレームで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="1e389-211">Evaluates expression on a given call frame.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-212">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-212">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-213">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="1e389-213">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="1e389-214">を評価するために、フレーム識別子を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1e389-214">Call frame identifier to evaluate on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-215">expression</span><span class="sxs-lookup"><span data-stu-id="1e389-215">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-216">評価する式。</span><span class="sxs-lookup"><span data-stu-id="1e389-216">Expression to evaluate.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-217">返し</span><span class="sxs-lookup"><span data-stu-id="1e389-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-218">より</span><span class="sxs-lookup"><span data-stu-id="1e389-218">result</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="1e389-219">評価結果のオブジェクトラッパー。</span><span class="sxs-lookup"><span data-stu-id="1e389-219">Object wrapper for the evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-220">Set変数値</span><span class="sxs-lookup"><span data-stu-id="1e389-220">setVariableValue</span></span>
<span data-ttu-id="1e389-221">Callframe の変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="1e389-221">Changes value of variable in a callframe.</span></span> <span data-ttu-id="1e389-222">オブジェクトベースのスコープはサポートされていないため、手動で手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e389-222">Object-based scopes are not supported and must be mutated manually.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-223">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-223">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-224">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="1e389-224">scopeNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-225">0ベースのスコープの数がスコープチェーンに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="1e389-225">0-based number of scope as was listed in scope chain.</span></span> <span data-ttu-id="1e389-226">"Local"、"クロージャ"、"catch" のスコープ型のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e389-226">Only 'local', 'closure' and 'catch' scope types are allowed.</span></span> <span data-ttu-id="1e389-227">その他のスコープは手動で操作できます。</span><span class="sxs-lookup"><span data-stu-id="1e389-227">Other scopes could be manipulated manually.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-228">variableName</span><span class="sxs-lookup"><span data-stu-id="1e389-228">variableName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-229">変数名。</span><span class="sxs-lookup"><span data-stu-id="1e389-229">Variable name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-230">newValue</span><span class="sxs-lookup"><span data-stu-id="1e389-230">newValue</span></span></td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td><span data-ttu-id="1e389-231">新しい変数値。</span><span class="sxs-lookup"><span data-stu-id="1e389-231">New variable value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-232">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="1e389-232">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="1e389-233">変数を保持する callframe の Id です。</span><span class="sxs-lookup"><span data-stu-id="1e389-233">Id of callframe that holds variable.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-234">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="1e389-234">setBlackboxPatterns</span></span>
<span><b><span data-ttu-id="1e389-235">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-235">Experimental.</span></span> </b></span><span data-ttu-id="1e389-236">前の blackbox パターンを、渡されたものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1e389-236">Replace previous blackbox patterns with passed ones.</span></span> <span data-ttu-id="1e389-237">すべてのパターンに一致する url を持つスクリプトのステップ/一時停止をスキップするようにバックエンドに強制します。</span><span class="sxs-lookup"><span data-stu-id="1e389-237">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span> <span data-ttu-id="1e389-238">デバッガーは、"ステップイン" を複数回実行して、ブラックボックススクリプトを終了しようとします。最後に、失敗した場合は、"ステップアウト" に従います。</span><span class="sxs-lookup"><span data-stu-id="1e389-238">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-240">傾向</span><span class="sxs-lookup"><span data-stu-id="1e389-240">patterns</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="1e389-241">Blackbox の状態のスクリプト url を確認するために使用される regexps の配列です。</span><span class="sxs-lookup"><span data-stu-id="1e389-241">Array of regexps that will be used to check script url for blackbox state.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-242">Mssetデバッガ Propertyvalue</span><span class="sxs-lookup"><span data-stu-id="1e389-242">msSetDebuggerPropertyValue</span></span>
<span><b><span data-ttu-id="1e389-243">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-243">Experimental.</span></span> </b></span><span data-ttu-id="1e389-244">Microsoft: 指定された debugger プロパティを指定された値に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e389-244">Microsoft: Sets the specified debugger property to the specified value.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-245">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-246">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="1e389-246">debuggerPropertyId</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-247">Microsoft: プロパティ id (msDebuggerPropertyId など) を設定します。</span><span class="sxs-lookup"><span data-stu-id="1e389-247">Microsoft: The property id (i.e. msDebuggerPropertyId) to set.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-248">newValue</span><span class="sxs-lookup"><span data-stu-id="1e389-248">newValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="1e389-249">イベント</span><span class="sxs-lookup"><span data-stu-id="1e389-249">Events</span></span>

### <span data-ttu-id="1e389-250">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="1e389-250">scriptParsed</span></span>
<span data-ttu-id="1e389-251">スクリプトの解析時に発生します。</span><span class="sxs-lookup"><span data-stu-id="1e389-251">Fired when the script is parsed.</span></span> <span data-ttu-id="1e389-252">このイベントは、デバッガーを有効にしているときに、既知の収集されていないすべてのスクリプトに対しても発生します。</span><span class="sxs-lookup"><span data-stu-id="1e389-252">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-253">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-254">scriptId</span><span class="sxs-lookup"><span data-stu-id="1e389-254">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="1e389-255">解析されたスクリプトの識別子。</span><span class="sxs-lookup"><span data-stu-id="1e389-255">Identifier of the script parsed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-256">url</span><span class="sxs-lookup"><span data-stu-id="1e389-256">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-257">解析されたスクリプトの URL または名前 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="1e389-257">URL or name of the script parsed (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-258">startLine</span><span class="sxs-lookup"><span data-stu-id="1e389-258">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-259">指定した URL のリソース内のスクリプトの行オフセット (スクリプトタグの場合)。</span><span class="sxs-lookup"><span data-stu-id="1e389-259">Line offset of the script within the resource with given URL (for script tags).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-260">startColumn</span><span class="sxs-lookup"><span data-stu-id="1e389-260">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-261">指定した URL のリソース内のスクリプトの列オフセット。</span><span class="sxs-lookup"><span data-stu-id="1e389-261">Column offset of the script within the resource with given URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-262">endLine</span><span class="sxs-lookup"><span data-stu-id="1e389-262">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-263">スクリプトの最終行。</span><span class="sxs-lookup"><span data-stu-id="1e389-263">Last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-264">endColumn</span><span class="sxs-lookup"><span data-stu-id="1e389-264">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-265">スクリプトの最後の行の長さ。</span><span class="sxs-lookup"><span data-stu-id="1e389-265">Length of the last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="1e389-266">executionContextId</span></span></td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td><span data-ttu-id="1e389-267">スクリプト作成コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e389-267">Specifies script creation context.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-268">sourceMapURL</span><span class="sxs-lookup"><span data-stu-id="1e389-268">sourceMapURL</span></span> <br/> <i><span data-ttu-id="1e389-269">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-269">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-270">スクリプト (存在する場合) に関連付けられたソースマップの URL。</span><span class="sxs-lookup"><span data-stu-id="1e389-270">URL of source map associated with script (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-271">全長</span><span class="sxs-lookup"><span data-stu-id="1e389-271">length</span></span> <br/> <i><span data-ttu-id="1e389-272">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-272">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="1e389-273">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-273">Experimental.</span></span> </b></span><span data-ttu-id="1e389-274">このスクリプトの長さ。</span><span class="sxs-lookup"><span data-stu-id="1e389-274">This script length.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-275">msParentId</span><span class="sxs-lookup"><span data-stu-id="1e389-275">msParentId</span></span> <br/> <i><span data-ttu-id="1e389-276">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-276">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="1e389-277">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-277">Experimental.</span></span> </b></span><span data-ttu-id="1e389-278">これは親ドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="1e389-278">This is the parent document ID.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-279">msMimeType</span><span class="sxs-lookup"><span data-stu-id="1e389-279">msMimeType</span></span> <br/> <i><span data-ttu-id="1e389-280">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-280">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="1e389-281">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-281">Experimental.</span></span> </b></span><span data-ttu-id="1e389-282">Mime の種類です。</span><span class="sxs-lookup"><span data-stu-id="1e389-282">This is the mime type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-283">msIsDynamicCode</span><span class="sxs-lookup"><span data-stu-id="1e389-283">msIsDynamicCode</span></span> <br/> <i><span data-ttu-id="1e389-284">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-284">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="1e389-285">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-285">Experimental.</span></span> </b></span><span data-ttu-id="1e389-286">これは、動的コードであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1e389-286">This indicates whether it is dynamic code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-287">msLongDocumentId</span><span class="sxs-lookup"><span data-stu-id="1e389-287">msLongDocumentId</span></span> <br/> <i><span data-ttu-id="1e389-288">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-288">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="1e389-289">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-289">Experimental.</span></span> </b></span><span data-ttu-id="1e389-290">これは長いドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="1e389-290">This is the long document ID.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-291">breakpointResolved 解決</span><span class="sxs-lookup"><span data-stu-id="1e389-291">breakpointResolved</span></span>
<span data-ttu-id="1e389-292">ブレークポイントが実際のスクリプトと場所に解決されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1e389-292">Fired when breakpoint is resolved to an actual script and location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-293">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-293">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-294">breakpointId</span><span class="sxs-lookup"><span data-stu-id="1e389-294">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="1e389-295">ブレークポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1e389-295">Breakpoint unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-296">元</span><span class="sxs-lookup"><span data-stu-id="1e389-296">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-297">実際のブレークポイントの位置。</span><span class="sxs-lookup"><span data-stu-id="1e389-297">Actual breakpoint location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-298">msLength</span><span class="sxs-lookup"><span data-stu-id="1e389-298">msLength</span></span> <br/> <i><span data-ttu-id="1e389-299">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-299">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="1e389-300">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-300">Experimental.</span></span> </b></span><span data-ttu-id="1e389-301">Microsoft: ブレークポイントの場所のコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="1e389-301">Microsoft: Length of code (i.e. number of characters) at the breakpoint location.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-302">paused (一時停止)</span><span class="sxs-lookup"><span data-stu-id="1e389-302">paused</span></span>
<span data-ttu-id="1e389-303">デバッガーがブレークポイントまたは例外のために中断したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1e389-303">Fired when the debuggers breaks for a breakpoint or exception.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-304">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e389-304">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-305">callFrames</span><span class="sxs-lookup"><span data-stu-id="1e389-305">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="1e389-306">呼び出しスタックが停止しました。</span><span class="sxs-lookup"><span data-stu-id="1e389-306">Call stack the debugger stopped on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-307">から</span><span class="sxs-lookup"><span data-stu-id="1e389-307">reason</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="1e389-308">許可される値: ブレークポイント、ステップ、例外、other、EventListener</span><span class="sxs-lookup"><span data-stu-id="1e389-308">Allowed values: breakpoint, step, exception, other, EventListener</span></span></i></td>
            <td><span data-ttu-id="1e389-309">一時停止理由。</span><span class="sxs-lookup"><span data-stu-id="1e389-309">Pause reason.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-310">data</span><span class="sxs-lookup"><span data-stu-id="1e389-310">data</span></span> <br/> <i><span data-ttu-id="1e389-311">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-311">optional</span></span></i></td>
            <td><code class="flyout">object</code></td>
            <td><span data-ttu-id="1e389-312">ブレーク固有の補助プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e389-312">Object containing break-specific auxiliary properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-313">ヒットブレークポイント</span><span class="sxs-lookup"><span data-stu-id="1e389-313">hitBreakpoints</span></span> <br/> <i><span data-ttu-id="1e389-314">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-314">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="1e389-315">ブレークポイント Id のヒット</span><span class="sxs-lookup"><span data-stu-id="1e389-315">Hit breakpoints IDs</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-316">asyncStackTrace</span><span class="sxs-lookup"><span data-stu-id="1e389-316">asyncStackTrace</span></span> <br/> <i><span data-ttu-id="1e389-317">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-317">optional</span></span></i></td>
            <td><!--  <a href="#stacktrace">  --><code class="flyout">StackTrace</code><!--  </a>  --></td>
            <td><span data-ttu-id="1e389-318">JavaScript async stack trace。</span><span class="sxs-lookup"><span data-stu-id="1e389-318">JavaScript async stack trace.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="1e389-319">復帰</span><span class="sxs-lookup"><span data-stu-id="1e389-319">resumed</span></span>
<span data-ttu-id="1e389-320">デバッガーの実行を再開したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1e389-320">Fired when the debugger resumes execution.</span></span>

</p>

---

## <span data-ttu-id="1e389-321">型</span><span class="sxs-lookup"><span data-stu-id="1e389-321">Types</span></span>

### <a name="breakpointid"></a> <span data-ttu-id="1e389-322">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="1e389-322">BreakpointId</span></span> `string`

<span data-ttu-id="1e389-323">ブレークポイント識別子。</span><span class="sxs-lookup"><span data-stu-id="1e389-323">Breakpoint identifier.</span></span>

</p>

---

### <a name="callframeid"></a> <span data-ttu-id="1e389-324">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="1e389-324">CallFrameId</span></span> `string`

<span data-ttu-id="1e389-325">通話フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="1e389-325">Call frame identifier.</span></span>

</p>

---

### <a name="location"></a> <span data-ttu-id="1e389-326">Location</span><span class="sxs-lookup"><span data-stu-id="1e389-326">Location</span></span> `object`

<span data-ttu-id="1e389-327">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="1e389-327">Location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-328">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e389-328">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-329">scriptId</span><span class="sxs-lookup"><span data-stu-id="1e389-329">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="1e389-330">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="1e389-330">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-331">lineNumber</span><span class="sxs-lookup"><span data-stu-id="1e389-331">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-332">スクリプト内の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="1e389-332">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-333">列番号</span><span class="sxs-lookup"><span data-stu-id="1e389-333">columnNumber</span></span> <br/> <i><span data-ttu-id="1e389-334">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-334">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-335">スクリプトの列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="1e389-335">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-336">msLength</span><span class="sxs-lookup"><span data-stu-id="1e389-336">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-337">Microsoft: この呼び出しフレームのコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="1e389-337">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="breaklocation"></a> <span data-ttu-id="1e389-338">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="1e389-338">BreakLocation</span></span> `object`

<span data-ttu-id="1e389-339">ソースコード内の位置を中断します。</span><span class="sxs-lookup"><span data-stu-id="1e389-339">Break location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-340">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e389-340">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-341">scriptId</span><span class="sxs-lookup"><span data-stu-id="1e389-341">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="1e389-342">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="1e389-342">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-343">lineNumber</span><span class="sxs-lookup"><span data-stu-id="1e389-343">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-344">スクリプト内の行番号 (0 ベース)。</span><span class="sxs-lookup"><span data-stu-id="1e389-344">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-345">列番号</span><span class="sxs-lookup"><span data-stu-id="1e389-345">columnNumber</span></span> <br/> <i><span data-ttu-id="1e389-346">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-346">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-347">スクリプトの列番号 (0 ベース)</span><span class="sxs-lookup"><span data-stu-id="1e389-347">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-348">msLength</span><span class="sxs-lookup"><span data-stu-id="1e389-348">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="1e389-349">Microsoft: この呼び出しフレームのコード長 (文字数)。</span><span class="sxs-lookup"><span data-stu-id="1e389-349">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-350">型</span><span class="sxs-lookup"><span data-stu-id="1e389-350">type</span></span> <br/> <i><span data-ttu-id="1e389-351">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-351">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-352">指定可能な値: デバッガステートメント、call、return。</span><span class="sxs-lookup"><span data-stu-id="1e389-352">Allowed values: debuggerStatement, call, return.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callframe"></a> <span data-ttu-id="1e389-353">CallFrame</span><span class="sxs-lookup"><span data-stu-id="1e389-353">CallFrame</span></span> `object`

<span data-ttu-id="1e389-354">JavaScript 呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="1e389-354">JavaScript call frame.</span></span> <span data-ttu-id="1e389-355">コールスタックは、呼び出しフレームの配列によって形成されます。</span><span class="sxs-lookup"><span data-stu-id="1e389-355">Array of call frames form the call stack.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-356">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e389-356">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-357">Callフレーム Id</span><span class="sxs-lookup"><span data-stu-id="1e389-357">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="1e389-358">通話フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="1e389-358">Call frame identifier.</span></span> <span data-ttu-id="1e389-359">この識別子は、デバッガーが一時停止されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="1e389-359">This identifier is only valid while the debugger is paused.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-360">functionName</span><span class="sxs-lookup"><span data-stu-id="1e389-360">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-361">この呼び出しフレームで呼び出される JavaScript 関数の名前。</span><span class="sxs-lookup"><span data-stu-id="1e389-361">Name of the JavaScript function called on this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-362">関数の場所</span><span class="sxs-lookup"><span data-stu-id="1e389-362">functionLocation</span></span> <br/> <i><span data-ttu-id="1e389-363">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-363">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b><span data-ttu-id="1e389-364">的.</span><span class="sxs-lookup"><span data-stu-id="1e389-364">Experimental.</span></span> </b></span><span data-ttu-id="1e389-365">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="1e389-365">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-366">元</span><span class="sxs-lookup"><span data-stu-id="1e389-366">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-367">ソースコード内の場所。</span><span class="sxs-lookup"><span data-stu-id="1e389-367">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-368">url</span><span class="sxs-lookup"><span data-stu-id="1e389-368">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="1e389-369">JavaScript スクリプト名または url。</span><span class="sxs-lookup"><span data-stu-id="1e389-369">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-370">scopeChain</span><span class="sxs-lookup"><span data-stu-id="1e389-370">scopeChain</span></span></td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td><span data-ttu-id="1e389-371">この呼び出しフレームのスコープチェーン。</span><span class="sxs-lookup"><span data-stu-id="1e389-371">Scope chain for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-372">これ</span><span class="sxs-lookup"><span data-stu-id="1e389-372">this</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> <span data-ttu-id="1e389-373">この呼び出しフレームのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e389-373">object for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-374">戻り</span><span class="sxs-lookup"><span data-stu-id="1e389-374">returnValue</span></span> <br/> <i><span data-ttu-id="1e389-375">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-375">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="1e389-376">返される値 (関数が戻り値の位置にある場合)。</span><span class="sxs-lookup"><span data-stu-id="1e389-376">The value being returned, if the function is at return point.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="scope"></a> <span data-ttu-id="1e389-377">適用範囲</span><span class="sxs-lookup"><span data-stu-id="1e389-377">Scope</span></span> `object`

<span data-ttu-id="1e389-378">スコープの説明。</span><span class="sxs-lookup"><span data-stu-id="1e389-378">Scope description.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="1e389-379">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e389-379">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="1e389-380">型</span><span class="sxs-lookup"><span data-stu-id="1e389-380">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="1e389-381">許可される値: global、local、with、クロージャ、catch、block、script、eval、module、return</span><span class="sxs-lookup"><span data-stu-id="1e389-381">Allowed values: global, local, with, closure, catch, block, script, eval, module, return</span></span></i></td>
            <td><span data-ttu-id="1e389-382">スコープ型。</span><span class="sxs-lookup"><span data-stu-id="1e389-382">Scope type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-383">object</span><span class="sxs-lookup"><span data-stu-id="1e389-383">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="1e389-384">スコープを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e389-384">Object representing the scope.</span></span> <span data-ttu-id="1e389-385"><code>global</code>And スコープは実際のオブジェクトを表し、スコープ <code>with</code> の残りの部分については、スコープ変数をプロパティとして列挙する人為的な一時的なオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="1e389-385">For <code>global</code> and <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-386">name</span><span class="sxs-lookup"><span data-stu-id="1e389-386">name</span></span> <br/> <i><span data-ttu-id="1e389-387">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-387">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-388">startLocation</span><span class="sxs-lookup"><span data-stu-id="1e389-388">startLocation</span></span> <br/> <i><span data-ttu-id="1e389-389">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-389">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-390">スコープが開始されるソースコード内の場所</span><span class="sxs-lookup"><span data-stu-id="1e389-390">Location in the source code where scope starts</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="1e389-391">endLocation</span><span class="sxs-lookup"><span data-stu-id="1e389-391">endLocation</span></span> <br/> <i><span data-ttu-id="1e389-392">オプション</span><span class="sxs-lookup"><span data-stu-id="1e389-392">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="1e389-393">スコープが終了するソースコード内の場所</span><span class="sxs-lookup"><span data-stu-id="1e389-393">Location in the source code where scope ends</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="1e389-394">依存関係</span><span class="sxs-lookup"><span data-stu-id="1e389-394">Dependencies</span></span>

[<span data-ttu-id="1e389-395">言語</span><span class="sxs-lookup"><span data-stu-id="1e389-395">Runtime</span></span>](runtime.md)
