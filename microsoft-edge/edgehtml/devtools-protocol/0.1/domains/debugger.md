---
description: デバッガー ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 デバッガー ドメインは、JavaScript デバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
title: デバッガー ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5160e6e69ec76f8c584f1bdb969464d805c7afa7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234802"
---
# <span data-ttu-id="afdb9-105">デバッガー ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="afdb9-105">Debugger Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  
  
<span data-ttu-id="afdb9-106">デバッガー ドメインは、JavaScript デバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="afdb9-107">ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="afdb9-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="afdb9-108">Methods</span></span>**](#methods) | <span data-ttu-id="afdb9-109">[有効](#enable)、[無効](#disable)、getPossibleBreakpoints、setBreakpointsActive、setBreakpointByUrl、setBreakpoint [、removeBreakpoint](#removebreakpoint) [](#setbreakpointsactive) [](#getpossiblebreakpoints) [](#setbreakpointbyurl) [、stepOver](#stepover) [](#setbreakpoint) [、stepInto](#stepinto) [、stepOut](#stepout) [、pause](#pause) [、resume、getScriptSource](#resume) [、setPauseOnExceptions](#setpauseonexceptions) [、evaluateOnCallFrame](#evaluateoncallframe) [、setVariableValue、setBlackboxPatterns](#setvariablevalue) [、msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue) [](#getscriptsource) [](#setblackboxpatterns)</span><span class="sxs-lookup"><span data-stu-id="afdb9-109">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |
| [**<span data-ttu-id="afdb9-110">イベント</span><span class="sxs-lookup"><span data-stu-id="afdb9-110">Events</span></span>**](#events) | <span data-ttu-id="afdb9-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span><span class="sxs-lookup"><span data-stu-id="afdb9-111">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |
| [**<span data-ttu-id="afdb9-112">型</span><span class="sxs-lookup"><span data-stu-id="afdb9-112">Types</span></span>**](#types) | <span data-ttu-id="afdb9-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="afdb9-113">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |
| [**<span data-ttu-id="afdb9-114">依存関係</span><span class="sxs-lookup"><span data-stu-id="afdb9-114">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="afdb9-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="afdb9-115">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="afdb9-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="afdb9-116">Methods</span></span>

### <span data-ttu-id="afdb9-117">[有効]</span><span class="sxs-lookup"><span data-stu-id="afdb9-117">enable</span></span>
<span data-ttu-id="afdb9-118">指定したページのデバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="afdb9-118">Enables debugger for the given page.</span></span> <span data-ttu-id="afdb9-119">クライアントは、このコマンドの結果を受け取るまでデバッグが有効になっているとは想定しません。</span><span class="sxs-lookup"><span data-stu-id="afdb9-119">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>


---

### <span data-ttu-id="afdb9-120">[無効]</span><span class="sxs-lookup"><span data-stu-id="afdb9-120">disable</span></span>
<span data-ttu-id="afdb9-121">特定のページのデバッガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="afdb9-121">Disables debugger for given page.</span></span>


---

### <span data-ttu-id="afdb9-122">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="afdb9-122">getPossibleBreakpoints</span></span>
<span data-ttu-id="afdb9-123">ブレークポイントの可能性がある場所を返します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-123">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="afdb9-124">開始範囲と終了範囲の場所の scriptId は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="afdb9-124">scriptId in start and end range locations should be the same.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-125">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-126">start</span><span class="sxs-lookup"><span data-stu-id="afdb9-126">start</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-127">ブレークポイントの位置を検索する範囲の開始位置。</span><span class="sxs-lookup"><span data-stu-id="afdb9-127">Start of range to search possible breakpoint locations in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-128">終了</span><span class="sxs-lookup"><span data-stu-id="afdb9-128">end</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-129">(除外する) のブレークポイントの位置を検索する範囲の終了。</span><span class="sxs-lookup"><span data-stu-id="afdb9-129">End of range to search possible breakpoint locations in (excluding).</span></span> <span data-ttu-id="afdb9-130">指定しない場合、スクリプトの終了が範囲の終了として使用されます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-130">When not specified, end of scripts is used as end of range.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-131">戻り値</span><span class="sxs-lookup"><span data-stu-id="afdb9-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-132">locations</span><span class="sxs-lookup"><span data-stu-id="afdb9-132">locations</span></span></td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td><span data-ttu-id="afdb9-133">考えられるブレークポイントの場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="afdb9-133">List of the possible breakpoint locations.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-134">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="afdb9-134">setBreakpointsActive</span></span>
<span data-ttu-id="afdb9-135">ページ上のすべてのブレークポイントをアクティブ化/非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-135">Activates / deactivates all breakpoints on the page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-136">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-137">active</span><span class="sxs-lookup"><span data-stu-id="afdb9-137">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="afdb9-138">アクティブな状態のブレークポイントの新しい値。</span><span class="sxs-lookup"><span data-stu-id="afdb9-138">New value for breakpoints active state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-139">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="afdb9-139">setBreakpointByUrl</span></span>
<span data-ttu-id="afdb9-140">URL または URL regex で指定された特定の場所に JavaScript ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-140">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span> <span data-ttu-id="afdb9-141">このコマンドを発行すると、既存の解析済みスクリプトはすべてブレークポイントが解決され、プロパティで返 <code>locations</code> されます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-141">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in <code>locations</code> property.</span></span> <span data-ttu-id="afdb9-142">さらに一致するスクリプト解析では、後続の <code>breakpointResolved</code> イベントが発行されます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-142">Further matching script parsing will result in subsequent <code>breakpointResolved</code> events issued.</span></span> <span data-ttu-id="afdb9-143">この論理的なブレークポイントは、ページの再読み込み後に残ります。</span><span class="sxs-lookup"><span data-stu-id="afdb9-143">This logical breakpoint will survive page reloads.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-144">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-145">lineNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-145">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-146">ブレークポイントを設定する行番号です。</span><span class="sxs-lookup"><span data-stu-id="afdb9-146">Line number to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-147">url</span><span class="sxs-lookup"><span data-stu-id="afdb9-147">url</span></span> <br/> <i><span data-ttu-id="afdb9-148">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-148">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-149">ブレークポイントを設定するリソースの URL。</span><span class="sxs-lookup"><span data-stu-id="afdb9-149">URL of the resources to set breakpoint on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-150">urlRegex</span><span class="sxs-lookup"><span data-stu-id="afdb9-150">urlRegex</span></span> <br/> <i><span data-ttu-id="afdb9-151">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-151">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-152">ブレークポイントを設定するリソースの URL の正規表現パターン。</span><span class="sxs-lookup"><span data-stu-id="afdb9-152">Regex pattern for the URLs of the resources to set breakpoints on.</span></span> <span data-ttu-id="afdb9-153">指定 <code>url</code> するか <code>urlRegex</code> 、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afdb9-153">Either <code>url</code> or <code>urlRegex</code> must be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-154">columnNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-154">columnNumber</span></span> <br/> <i><span data-ttu-id="afdb9-155">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-155">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-156">ブレークポイントを設定する行のオフセット位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-156">Offset in the line to set breakpoint at.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-157">condition</span><span class="sxs-lookup"><span data-stu-id="afdb9-157">condition</span></span> <br/> <i><span data-ttu-id="afdb9-158">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-158">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-159">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="afdb9-159">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="afdb9-160">指定した場合、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-160">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-161">戻り値</span><span class="sxs-lookup"><span data-stu-id="afdb9-161">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-162">breakpointId</span><span class="sxs-lookup"><span data-stu-id="afdb9-162">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="afdb9-163">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="afdb9-163">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-164">locations</span><span class="sxs-lookup"><span data-stu-id="afdb9-164">locations</span></span></td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td><span data-ttu-id="afdb9-165">このブレークポイントが追加時に解決された場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="afdb9-165">List of the locations this breakpoint resolved into upon addition.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-166">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="afdb9-166">setBreakpoint</span></span>
<span data-ttu-id="afdb9-167">特定の場所に JavaScript のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-167">Sets JavaScript breakpoint at a given location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-168">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-168">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-169">location</span><span class="sxs-lookup"><span data-stu-id="afdb9-169">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-170">ブレークポイントを設定する場所。</span><span class="sxs-lookup"><span data-stu-id="afdb9-170">Location to set breakpoint in.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-171">condition</span><span class="sxs-lookup"><span data-stu-id="afdb9-171">condition</span></span> <br/> <i><span data-ttu-id="afdb9-172">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-172">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-173">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="afdb9-173">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="afdb9-174">指定した場合、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-174">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-175">戻り値</span><span class="sxs-lookup"><span data-stu-id="afdb9-175">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-176">breakpointId</span><span class="sxs-lookup"><span data-stu-id="afdb9-176">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="afdb9-177">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="afdb9-177">Id of the created breakpoint for further reference.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-178">actualLocation</span><span class="sxs-lookup"><span data-stu-id="afdb9-178">actualLocation</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-179">このブレークポイントが解決された場所。</span><span class="sxs-lookup"><span data-stu-id="afdb9-179">Location this breakpoint resolved into.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-180">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="afdb9-180">removeBreakpoint</span></span>
<span data-ttu-id="afdb9-181">JavaScript ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-181">Removes JavaScript breakpoint.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-182">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-182">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-183">breakpointId</span><span class="sxs-lookup"><span data-stu-id="afdb9-183">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-184">stepOver</span><span class="sxs-lookup"><span data-stu-id="afdb9-184">stepOver</span></span>
<span data-ttu-id="afdb9-185">ステートメントをステップオーバーします。</span><span class="sxs-lookup"><span data-stu-id="afdb9-185">Steps over the statement.</span></span>


---

### <span data-ttu-id="afdb9-186">stepInto</span><span class="sxs-lookup"><span data-stu-id="afdb9-186">stepInto</span></span>
<span data-ttu-id="afdb9-187">関数呼び出しにステップ します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-187">Steps into the function call.</span></span>


---

### <span data-ttu-id="afdb9-188">stepOut</span><span class="sxs-lookup"><span data-stu-id="afdb9-188">stepOut</span></span>
<span data-ttu-id="afdb9-189">関数呼び出しからステップ アウトします。</span><span class="sxs-lookup"><span data-stu-id="afdb9-189">Steps out of the function call.</span></span>


---

### <span data-ttu-id="afdb9-190">pause</span><span class="sxs-lookup"><span data-stu-id="afdb9-190">pause</span></span>
<span data-ttu-id="afdb9-191">次の JavaScript ステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-191">Stops on the next JavaScript statement.</span></span>


---

### <span data-ttu-id="afdb9-192">resume</span><span class="sxs-lookup"><span data-stu-id="afdb9-192">resume</span></span>
<span data-ttu-id="afdb9-193">JavaScript の実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-193">Resumes JavaScript execution.</span></span>


---

### <span data-ttu-id="afdb9-194">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="afdb9-194">getScriptSource</span></span>
<span data-ttu-id="afdb9-195">指定された ID を持つスクリプトのソースを返します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-195">Returns source for the script with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-196">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-196">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-197">scriptId</span><span class="sxs-lookup"><span data-stu-id="afdb9-197">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="afdb9-198">ソースを取得するスクリプトの ID。</span><span class="sxs-lookup"><span data-stu-id="afdb9-198">Id of the script to get source for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-199">戻り値</span><span class="sxs-lookup"><span data-stu-id="afdb9-199">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-200">scriptSource</span><span class="sxs-lookup"><span data-stu-id="afdb9-200">scriptSource</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-201">スクリプト ソース。</span><span class="sxs-lookup"><span data-stu-id="afdb9-201">Script source.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-202">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="afdb9-202">setPauseOnExceptions</span></span>
<span data-ttu-id="afdb9-203">例外状態での一時停止を定義します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-203">Defines pause on exceptions state.</span></span> <span data-ttu-id="afdb9-204">すべての例外、キャッチされていない例外、または例外がない場合に停止を設定できます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-204">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span> <span data-ttu-id="afdb9-205">例外の状態での最初の一時停止は次です <code>none</code> 。</span><span class="sxs-lookup"><span data-stu-id="afdb9-205">Initial pause on exceptions state is <code>none</code>.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-207">state</span><span class="sxs-lookup"><span data-stu-id="afdb9-207">state</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="afdb9-208">使用できる値: none、uncaught、all</span><span class="sxs-lookup"><span data-stu-id="afdb9-208">Allowed values: none, uncaught, all</span></span></i></td>
            <td><span data-ttu-id="afdb9-209">例外モードで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-209">Pause on exceptions mode.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-210">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="afdb9-210">evaluateOnCallFrame</span></span>
<span data-ttu-id="afdb9-211">特定の呼び出しフレームの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-211">Evaluates expression on a given call frame.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-212">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-212">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-213">callFrameId</span><span class="sxs-lookup"><span data-stu-id="afdb9-213">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="afdb9-214">評価するコール フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-214">Call frame identifier to evaluate on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-215">式</span><span class="sxs-lookup"><span data-stu-id="afdb9-215">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-216">評価する式。</span><span class="sxs-lookup"><span data-stu-id="afdb9-216">Expression to evaluate.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-217">戻り値</span><span class="sxs-lookup"><span data-stu-id="afdb9-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-218">result</span><span class="sxs-lookup"><span data-stu-id="afdb9-218">result</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="afdb9-219">評価結果のオブジェクト ラッパー。</span><span class="sxs-lookup"><span data-stu-id="afdb9-219">Object wrapper for the evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-220">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="afdb9-220">setVariableValue</span></span>
<span data-ttu-id="afdb9-221">呼び出しフレーム内の変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-221">Changes value of variable in a callframe.</span></span> <span data-ttu-id="afdb9-222">オブジェクト ベースのスコープはサポートされていないので、手動でミュートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="afdb9-222">Object-based scopes are not supported and must be mutated manually.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-223">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-223">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-224">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-224">scopeNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-225">スコープ チェーンにリストされた 0 からスコープの数。</span><span class="sxs-lookup"><span data-stu-id="afdb9-225">0-based number of scope as was listed in scope chain.</span></span> <span data-ttu-id="afdb9-226">スコープの種類は 'local'、'closure' および 'catch' のみです。</span><span class="sxs-lookup"><span data-stu-id="afdb9-226">Only 'local', 'closure' and 'catch' scope types are allowed.</span></span> <span data-ttu-id="afdb9-227">他のスコープは手動で操作できます。</span><span class="sxs-lookup"><span data-stu-id="afdb9-227">Other scopes could be manipulated manually.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-228">variableName</span><span class="sxs-lookup"><span data-stu-id="afdb9-228">variableName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-229">変数名。</span><span class="sxs-lookup"><span data-stu-id="afdb9-229">Variable name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-230">newValue</span><span class="sxs-lookup"><span data-stu-id="afdb9-230">newValue</span></span></td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td><span data-ttu-id="afdb9-231">新しい変数値。</span><span class="sxs-lookup"><span data-stu-id="afdb9-231">New variable value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-232">callFrameId</span><span class="sxs-lookup"><span data-stu-id="afdb9-232">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="afdb9-233">変数を保持する呼び出しフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="afdb9-233">Id of callframe that holds variable.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-234">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="afdb9-234">setBlackboxPatterns</span></span>
<span><b><span data-ttu-id="afdb9-235">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-235">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-236">以前のブラックボックス パターンを渡されたパターンに置き換える。</span><span class="sxs-lookup"><span data-stu-id="afdb9-236">Replace previous blackbox patterns with passed ones.</span></span> <span data-ttu-id="afdb9-237">パターンの 1 つと一致する URL を持つスクリプトで、ステップ/一時停止をスキップするバックエンドを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-237">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span> <span data-ttu-id="afdb9-238">デバッガーは、何度か 'ステップ イン' を実行してブラックボックス 化されたスクリプトを残し、失敗した場合は最後に "ステップ アウト" を実行します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-238">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-240">patterns</span><span class="sxs-lookup"><span data-stu-id="afdb9-240">patterns</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="afdb9-241">スクリプト URL でブラックボックスの状態を確認するために使用される regexps の配列。</span><span class="sxs-lookup"><span data-stu-id="afdb9-241">Array of regexps that will be used to check script url for blackbox state.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-242">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="afdb9-242">msSetDebuggerPropertyValue</span></span>
<span><b><span data-ttu-id="afdb9-243">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-243">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-244">Microsoft: 指定されたデバッガー プロパティを指定された値に設定します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-244">Microsoft: Sets the specified debugger property to the specified value.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-245">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-246">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="afdb9-246">debuggerPropertyId</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-247">Microsoft: 設定するプロパティ ID (つまり、msDebuggerPropertyId)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-247">Microsoft: The property id (i.e. msDebuggerPropertyId) to set.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-248">newValue</span><span class="sxs-lookup"><span data-stu-id="afdb9-248">newValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="afdb9-249">イベント</span><span class="sxs-lookup"><span data-stu-id="afdb9-249">Events</span></span>

### <span data-ttu-id="afdb9-250">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="afdb9-250">scriptParsed</span></span>
<span data-ttu-id="afdb9-251">スクリプトが解析された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-251">Fired when the script is parsed.</span></span> <span data-ttu-id="afdb9-252">このイベントは、デバッガーを有効にした時点で、既知のすべてのスクリプトと未検出のスクリプトに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-252">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-253">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-254">scriptId</span><span class="sxs-lookup"><span data-stu-id="afdb9-254">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="afdb9-255">解析されたスクリプトの識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-255">Identifier of the script parsed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-256">url</span><span class="sxs-lookup"><span data-stu-id="afdb9-256">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-257">解析されたスクリプトの URL または名前 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-257">URL or name of the script parsed (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-258">startLine</span><span class="sxs-lookup"><span data-stu-id="afdb9-258">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-259">指定された URL を持つリソース内のスクリプトの行オフセット (スクリプト タグの場合)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-259">Line offset of the script within the resource with given URL (for script tags).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-260">startColumn</span><span class="sxs-lookup"><span data-stu-id="afdb9-260">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-261">指定された URL を持つリソース内のスクリプトの列オフセット。</span><span class="sxs-lookup"><span data-stu-id="afdb9-261">Column offset of the script within the resource with given URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-262">endLine</span><span class="sxs-lookup"><span data-stu-id="afdb9-262">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-263">スクリプトの最後の行。</span><span class="sxs-lookup"><span data-stu-id="afdb9-263">Last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-264">endColumn</span><span class="sxs-lookup"><span data-stu-id="afdb9-264">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-265">スクリプトの最後の行の長さ。</span><span class="sxs-lookup"><span data-stu-id="afdb9-265">Length of the last line of the script.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="afdb9-266">executionContextId</span></span></td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td><span data-ttu-id="afdb9-267">スクリプト作成コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-267">Specifies script creation context.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-268">sourceMapURL</span><span class="sxs-lookup"><span data-stu-id="afdb9-268">sourceMapURL</span></span> <br/> <i><span data-ttu-id="afdb9-269">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-269">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-270">スクリプトに関連付けられているソース マップの URL (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-270">URL of source map associated with script (if any).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-271">length</span><span class="sxs-lookup"><span data-stu-id="afdb9-271">length</span></span> <br/> <i><span data-ttu-id="afdb9-272">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-272">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="afdb9-273">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-273">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-274">このスクリプトの長さ。</span><span class="sxs-lookup"><span data-stu-id="afdb9-274">This script length.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-275">msParentId</span><span class="sxs-lookup"><span data-stu-id="afdb9-275">msParentId</span></span> <br/> <i><span data-ttu-id="afdb9-276">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-276">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="afdb9-277">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-277">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-278">これは親ドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="afdb9-278">This is the parent document ID.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-279">msMimeType</span><span class="sxs-lookup"><span data-stu-id="afdb9-279">msMimeType</span></span> <br/> <i><span data-ttu-id="afdb9-280">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-280">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="afdb9-281">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-281">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-282">これは MIME タイプです。</span><span class="sxs-lookup"><span data-stu-id="afdb9-282">This is the mime type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-283">msIsDynamicCode</span><span class="sxs-lookup"><span data-stu-id="afdb9-283">msIsDynamicCode</span></span> <br/> <i><span data-ttu-id="afdb9-284">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-284">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="afdb9-285">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-285">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-286">これは、動的コードかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-286">This indicates whether it is dynamic code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-287">msLongDocumentId</span><span class="sxs-lookup"><span data-stu-id="afdb9-287">msLongDocumentId</span></span> <br/> <i><span data-ttu-id="afdb9-288">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-288">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="afdb9-289">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-289">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-290">これは長いドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="afdb9-290">This is the long document ID.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-291">breakpointResolved</span><span class="sxs-lookup"><span data-stu-id="afdb9-291">breakpointResolved</span></span>
<span data-ttu-id="afdb9-292">ブレークポイントが実際のスクリプトと場所に解決された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-292">Fired when breakpoint is resolved to an actual script and location.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-293">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-293">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-294">breakpointId</span><span class="sxs-lookup"><span data-stu-id="afdb9-294">breakpointId</span></span></td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td><span data-ttu-id="afdb9-295">ブレークポイントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-295">Breakpoint unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-296">location</span><span class="sxs-lookup"><span data-stu-id="afdb9-296">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-297">ブレークポイントの実際の位置。</span><span class="sxs-lookup"><span data-stu-id="afdb9-297">Actual breakpoint location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-298">msLength</span><span class="sxs-lookup"><span data-stu-id="afdb9-298">msLength</span></span> <br/> <i><span data-ttu-id="afdb9-299">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-299">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b><span data-ttu-id="afdb9-300">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-300">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-301">Microsoft: ブレークポイントの位置にあるコードの長さ (文字数) です。</span><span class="sxs-lookup"><span data-stu-id="afdb9-301">Microsoft: Length of code (i.e. number of characters) at the breakpoint location.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-302">paused (一時停止)</span><span class="sxs-lookup"><span data-stu-id="afdb9-302">paused</span></span>
<span data-ttu-id="afdb9-303">ブレークポイントまたは例外のデバッガーが壊れた場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-303">Fired when the debuggers breaks for a breakpoint or exception.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-304">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afdb9-304">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-305">callFrames</span><span class="sxs-lookup"><span data-stu-id="afdb9-305">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="afdb9-306">デバッガーが停止したコール スタック。</span><span class="sxs-lookup"><span data-stu-id="afdb9-306">Call stack the debugger stopped on.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-307">reason</span><span class="sxs-lookup"><span data-stu-id="afdb9-307">reason</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="afdb9-308">使用できる値: ブレークポイント、ステップ、例外、その他</span><span class="sxs-lookup"><span data-stu-id="afdb9-308">Allowed values: breakpoint, step, exception, other</span></span></i></td>
            <td><span data-ttu-id="afdb9-309">一時停止の理由。</span><span class="sxs-lookup"><span data-stu-id="afdb9-309">Pause reason.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-310">data</span><span class="sxs-lookup"><span data-stu-id="afdb9-310">data</span></span> <br/> <i><span data-ttu-id="afdb9-311">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-311">optional</span></span></i></td>
            <td><code class="flyout">object</code></td>
            <td><span data-ttu-id="afdb9-312">ブレーク固有の補助プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="afdb9-312">Object containing break-specific auxiliary properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-313">hitBreakpoints</span><span class="sxs-lookup"><span data-stu-id="afdb9-313">hitBreakpoints</span></span> <br/> <i><span data-ttu-id="afdb9-314">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-314">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="afdb9-315">ヒット ブレークポイントの ID</span><span class="sxs-lookup"><span data-stu-id="afdb9-315">Hit breakpoints IDs</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="afdb9-316">resumed</span><span class="sxs-lookup"><span data-stu-id="afdb9-316">resumed</span></span>
<span data-ttu-id="afdb9-317">デバッガーが実行を再開するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-317">Fired when the debugger resumes execution.</span></span>


---

## <span data-ttu-id="afdb9-318">型</span><span class="sxs-lookup"><span data-stu-id="afdb9-318">Types</span></span>

### <a name="breakpointid"></a> <span data-ttu-id="afdb9-319">BreakpointId</span><span class="sxs-lookup"><span data-stu-id="afdb9-319">BreakpointId</span></span> `string`

<span data-ttu-id="afdb9-320">ブレークポイント識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-320">Breakpoint identifier.</span></span>


---

### <a name="callframeid"></a> <span data-ttu-id="afdb9-321">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="afdb9-321">CallFrameId</span></span> `string`

<span data-ttu-id="afdb9-322">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-322">Call frame identifier.</span></span>


---

### <a name="location"></a> <span data-ttu-id="afdb9-323">位置情報</span><span class="sxs-lookup"><span data-stu-id="afdb9-323">Location</span></span> `object`

<span data-ttu-id="afdb9-324">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="afdb9-324">Location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-325">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afdb9-325">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-326">scriptId</span><span class="sxs-lookup"><span data-stu-id="afdb9-326">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="afdb9-327">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="afdb9-327">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-328">lineNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-328">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-329">スクリプト内の行番号 (0 から開始)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-329">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-330">columnNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-330">columnNumber</span></span> <br/> <i><span data-ttu-id="afdb9-331">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-331">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-332">スクリプト内の列番号 (0 から開始)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-332">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-333">msLength</span><span class="sxs-lookup"><span data-stu-id="afdb9-333">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-334">Microsoft: この呼び出しフレームでのコードの長さ (文字数)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-334">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> <span data-ttu-id="afdb9-335">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="afdb9-335">BreakLocation</span></span> `object`

<span data-ttu-id="afdb9-336">ソース コード内の場所を壊す。</span><span class="sxs-lookup"><span data-stu-id="afdb9-336">Break location in the source code.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-337">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afdb9-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-338">scriptId</span><span class="sxs-lookup"><span data-stu-id="afdb9-338">scriptId</span></span></td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td><span data-ttu-id="afdb9-339">で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</span><span class="sxs-lookup"><span data-stu-id="afdb9-339">Script identifier as reported in the <code>Debugger.scriptParsed</code>.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-340">lineNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-340">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-341">スクリプト内の行番号 (0 から開始)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-341">Line number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-342">columnNumber</span><span class="sxs-lookup"><span data-stu-id="afdb9-342">columnNumber</span></span> <br/> <i><span data-ttu-id="afdb9-343">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-343">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-344">スクリプト内の列番号 (0 から開始)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-344">Column number in the script (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-345">msLength</span><span class="sxs-lookup"><span data-stu-id="afdb9-345">msLength</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="afdb9-346">Microsoft: この呼び出しフレームでのコードの長さ (文字数)。</span><span class="sxs-lookup"><span data-stu-id="afdb9-346">Microsoft: Length of code (i.e. number of characters) at this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-347">型</span><span class="sxs-lookup"><span data-stu-id="afdb9-347">type</span></span> <br/> <i><span data-ttu-id="afdb9-348">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-348">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-349">使用できる値: debuggerStatement、call、return。</span><span class="sxs-lookup"><span data-stu-id="afdb9-349">Allowed values: debuggerStatement, call, return.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> <span data-ttu-id="afdb9-350">CallFrame</span><span class="sxs-lookup"><span data-stu-id="afdb9-350">CallFrame</span></span> `object`

<span data-ttu-id="afdb9-351">JavaScript 呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="afdb9-351">JavaScript call frame.</span></span> <span data-ttu-id="afdb9-352">呼び出しフレームの配列が呼び出し履歴を形成します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-352">Array of call frames form the call stack.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-353">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afdb9-353">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-354">callFrameId</span><span class="sxs-lookup"><span data-stu-id="afdb9-354">callFrameId</span></span></td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td><span data-ttu-id="afdb9-355">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="afdb9-355">Call frame identifier.</span></span> <span data-ttu-id="afdb9-356">この識別子は、デバッガーが一時停止している間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="afdb9-356">This identifier is only valid while the debugger is paused.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-357">functionName</span><span class="sxs-lookup"><span data-stu-id="afdb9-357">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-358">この呼び出しフレームで呼び出される JavaScript 関数の名前。</span><span class="sxs-lookup"><span data-stu-id="afdb9-358">Name of the JavaScript function called on this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-359">functionLocation</span><span class="sxs-lookup"><span data-stu-id="afdb9-359">functionLocation</span></span> <br/> <i><span data-ttu-id="afdb9-360">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-360">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b><span data-ttu-id="afdb9-361">試験的。</span><span class="sxs-lookup"><span data-stu-id="afdb9-361">Experimental.</span></span> </b></span><span data-ttu-id="afdb9-362">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="afdb9-362">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-363">location</span><span class="sxs-lookup"><span data-stu-id="afdb9-363">location</span></span></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-364">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="afdb9-364">Location in the source code.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-365">url</span><span class="sxs-lookup"><span data-stu-id="afdb9-365">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="afdb9-366">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="afdb9-366">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-367">scopeChain</span><span class="sxs-lookup"><span data-stu-id="afdb9-367">scopeChain</span></span></td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td><span data-ttu-id="afdb9-368">この呼び出しフレームのスコープ チェーン。</span><span class="sxs-lookup"><span data-stu-id="afdb9-368">Scope chain for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-369">これ</span><span class="sxs-lookup"><span data-stu-id="afdb9-369">this</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> <span data-ttu-id="afdb9-370">オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="afdb9-370">object for this call frame.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-371">returnValue</span><span class="sxs-lookup"><span data-stu-id="afdb9-371">returnValue</span></span> <br/> <i><span data-ttu-id="afdb9-372">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-372">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="afdb9-373">関数が戻り値の位置にある場合に返される値。</span><span class="sxs-lookup"><span data-stu-id="afdb9-373">The value being returned, if the function is at return point.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> <span data-ttu-id="afdb9-374">適用範囲</span><span class="sxs-lookup"><span data-stu-id="afdb9-374">Scope</span></span> `object`

<span data-ttu-id="afdb9-375">スコープの説明。</span><span class="sxs-lookup"><span data-stu-id="afdb9-375">Scope description.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="afdb9-376">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afdb9-376">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="afdb9-377">型</span><span class="sxs-lookup"><span data-stu-id="afdb9-377">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="afdb9-378">使用できる値: global、local、with、closure、catch、block、script、eval、module</span><span class="sxs-lookup"><span data-stu-id="afdb9-378">Allowed values: global, local, with, closure, catch, block, script, eval, module</span></span></i></td>
            <td><span data-ttu-id="afdb9-379">スコープの種類。</span><span class="sxs-lookup"><span data-stu-id="afdb9-379">Scope type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-380">object</span><span class="sxs-lookup"><span data-stu-id="afdb9-380">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="afdb9-381">範囲を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="afdb9-381">Object representing the scope.</span></span> <span data-ttu-id="afdb9-382">For <code>global</code> および <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span><span class="sxs-lookup"><span data-stu-id="afdb9-382">For <code>global</code> and <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-383">name</span><span class="sxs-lookup"><span data-stu-id="afdb9-383">name</span></span> <br/> <i><span data-ttu-id="afdb9-384">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-384">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-385">startLocation</span><span class="sxs-lookup"><span data-stu-id="afdb9-385">startLocation</span></span> <br/> <i><span data-ttu-id="afdb9-386">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-386">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-387">範囲が開始するソース コード内の場所</span><span class="sxs-lookup"><span data-stu-id="afdb9-387">Location in the source code where scope starts</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="afdb9-388">endLocation</span><span class="sxs-lookup"><span data-stu-id="afdb9-388">endLocation</span></span> <br/> <i><span data-ttu-id="afdb9-389">オプション</span><span class="sxs-lookup"><span data-stu-id="afdb9-389">optional</span></span></i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span data-ttu-id="afdb9-390">範囲が終了するソース コード内の場所</span><span class="sxs-lookup"><span data-stu-id="afdb9-390">Location in the source code where scope ends</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="afdb9-391">依存関係</span><span class="sxs-lookup"><span data-stu-id="afdb9-391">Dependencies</span></span>

[<span data-ttu-id="afdb9-392">ランタイム</span><span class="sxs-lookup"><span data-stu-id="afdb9-392">Runtime</span></span>](runtime.md)
