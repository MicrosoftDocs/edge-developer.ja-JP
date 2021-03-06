---
description: デバッガー ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) 参照。  デバッガー ドメインは、JavaScript のデバッグ機能を公開します。  ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
title: デバッガー ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d63408e23fd8912cf617bfefae2b991387b45a38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397679"
---
# <a name="debugger-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="f1d3c-105">デバッガー ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-105">Debugger Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  
  
<span data-ttu-id="f1d3c-106">デバッガー ドメインは、JavaScript のデバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-106">Debugger domain exposes JavaScript debugging capabilities.</span></span>  <span data-ttu-id="f1d3c-107">ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| <span data-ttu-id="f1d3c-108">分類</span><span class="sxs-lookup"><span data-stu-id="f1d3c-108">Classification</span></span> | <span data-ttu-id="f1d3c-109">Members</span><span class="sxs-lookup"><span data-stu-id="f1d3c-109">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="f1d3c-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1d3c-110">Methods</span></span>](#methods) | <span data-ttu-id="f1d3c-111">[](#enable)enable [](#disable), disable , [getPossibleBreakpoints](#getpossiblebreakpoints) [](#pause), [setBreakpointByUrl , setBreakpointByUrl](#setbreakpointbyurl) [](#stepover), [setBreakpoint](#setbreakpoint) [](#setbreakpointsactive), [stepOver](#removebreakpoint), [stepInto](#stepout), stepOut , pause , [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [](#stepinto) [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-111">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |  
| [<span data-ttu-id="f1d3c-112">イベント</span><span class="sxs-lookup"><span data-stu-id="f1d3c-112">Events</span></span>](#events) | <span data-ttu-id="f1d3c-113">[scriptParsed](#scriptparsed), [ブレークポイントResolved](#breakpointresolved), [一時停止](#paused), [再開](#resumed)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-113">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |  
| [<span data-ttu-id="f1d3c-114">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-114">Types</span></span>](#types) | <span data-ttu-id="f1d3c-115">[ブレークポイント Id](#breakpointid)、 [CallFrameId](#callframeid)、 [Location](#location)、 [BreakLocation](#breaklocation)、 [CallFrame](#callframe)、 [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-115">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |  
| [<span data-ttu-id="f1d3c-116">依存関係</span><span class="sxs-lookup"><span data-stu-id="f1d3c-116">Dependencies</span></span>](#dependencies) | [<span data-ttu-id="f1d3c-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f1d3c-117">Runtime</span></span>](./runtime.md) |  

## <a name="methods"></a><span data-ttu-id="f1d3c-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1d3c-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="f1d3c-119">[有効]</span><span class="sxs-lookup"><span data-stu-id="f1d3c-119">enable</span></span>  

<span data-ttu-id="f1d3c-120">指定したページのデバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-120">Enables debugger for the given page.</span></span>  <span data-ttu-id="f1d3c-121">クライアントは、このコマンドの結果を受信するまで、デバッグが有効になっていると見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-121">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="f1d3c-122">[無効]</span><span class="sxs-lookup"><span data-stu-id="f1d3c-122">disable</span></span>  

<span data-ttu-id="f1d3c-123">特定のページのデバッガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-123">Disables debugger for given page.</span></span>  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a><span data-ttu-id="f1d3c-124">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="f1d3c-124">getPossibleBreakpoints</span></span>  

<span data-ttu-id="f1d3c-125">ブレークポイントの可能な場所を返します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-125">Returns possible locations for breakpoint.</span></span>  <span data-ttu-id="f1d3c-126">開始範囲と終了範囲の場所の scriptId は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-126">scriptId in start and end range locations should be the same.</span></span>  

| <span data-ttu-id="f1d3c-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-127">Parameters</span></span> | <span data-ttu-id="f1d3c-128">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-128">Type</span></span> | <span data-ttu-id="f1d3c-129">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-129">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-130">start</span><span class="sxs-lookup"><span data-stu-id="f1d3c-130">start</span></span> | [<span data-ttu-id="f1d3c-131">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-131">Location</span></span>](#location) | <span data-ttu-id="f1d3c-132">範囲の開始位置からブレークポイントの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-132">Start of range to search possible breakpoint locations in.</span></span> |  
| <span data-ttu-id="f1d3c-133">終了</span><span class="sxs-lookup"><span data-stu-id="f1d3c-133">end</span></span> | [<span data-ttu-id="f1d3c-134">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-134">Location</span></span>](#location) | <span data-ttu-id="f1d3c-135">\(excluding\) でブレークポイントの場所を検索する範囲の末尾。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-135">End of range to search possible breakpoint locations in \(excluding\).</span></span>  <span data-ttu-id="f1d3c-136">指定しない場合は、スクリプトの末尾が範囲の末尾として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-136">When not specified, end of scripts is used as end of range.</span></span> |  

| <span data-ttu-id="f1d3c-137">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1d3c-137">Returns</span></span> | <span data-ttu-id="f1d3c-138">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-138">Type</span></span> | <span data-ttu-id="f1d3c-139">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-139">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-140">場所</span><span class="sxs-lookup"><span data-stu-id="f1d3c-140">locations</span></span> | [<span data-ttu-id="f1d3c-141">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="f1d3c-141">BreakLocation</span></span>](#breaklocation) | <span data-ttu-id="f1d3c-142">考えられるブレークポイントの場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-142">List of the possible breakpoint locations.</span></span> |  

---  

### <a name="setbreakpointsactive"></a><span data-ttu-id="f1d3c-143">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="f1d3c-143">setBreakpointsActive</span></span>  

<span data-ttu-id="f1d3c-144">ページ上のすべてのブレークポイントをアクティブ化/非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-144">Activates / deactivates all breakpoints on the page.</span></span>  

| <span data-ttu-id="f1d3c-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-145">Parameters</span></span> | <span data-ttu-id="f1d3c-146">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-146">Type</span></span> | <span data-ttu-id="f1d3c-147">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-147">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-148">active</span><span class="sxs-lookup"><span data-stu-id="f1d3c-148">active</span></span> | `boolean` | <span data-ttu-id="f1d3c-149">ブレークポイントのアクティブな状態の新しい値。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-149">New value for breakpoints active state.</span></span> |  

---  

### <a name="setbreakpointbyurl"></a><span data-ttu-id="f1d3c-150">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="f1d3c-150">setBreakpointByUrl</span></span>  

<span data-ttu-id="f1d3c-151">URL または URL 正規表現で指定された特定の場所に JavaScript ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-151">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span>  <span data-ttu-id="f1d3c-152">このコマンドを発行すると、解析済みのすべてのスクリプトにブレークポイントが解決され、プロパティに返 `locations` されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-152">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in `locations` property.</span></span>  <span data-ttu-id="f1d3c-153">さらに一致するスクリプトの解析により、後続の `breakpointResolved` イベントが発行されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-153">Further matching script parsing will result in subsequent `breakpointResolved` events issued.</span></span>  <span data-ttu-id="f1d3c-154">この論理ブレークポイントは、ページの再読み込みから存続します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-154">This logical breakpoint will survive page reloads.</span></span>  

| <span data-ttu-id="f1d3c-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-155">Parameters</span></span> | <span data-ttu-id="f1d3c-156">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-156">Type</span></span> | <span data-ttu-id="f1d3c-157">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-158">lineNumber</span><span class="sxs-lookup"><span data-stu-id="f1d3c-158">lineNumber</span></span> | `integer` | <span data-ttu-id="f1d3c-159">ブレークポイントを設定する行番号。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-159">Line number to set breakpoint at.</span></span> |  
| <span data-ttu-id="f1d3c-160">url \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-160">url  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-161">ブレークポイントを設定するリソースの URL。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-161">URL of the resources to set breakpoint on.</span></span> |  
| <span data-ttu-id="f1d3c-162">urlRegex \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-162">urlRegex  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-163">ブレークポイントを設定するリソースの URL の正規表現パターン。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-163">Regex pattern for the URLs of the resources to set breakpoints on.</span></span>  <span data-ttu-id="f1d3c-164">指定 `url` するか `urlRegex` 、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-164">Either `url` or `urlRegex` must be specified.</span></span> |  
| <span data-ttu-id="f1d3c-165">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-165">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-166">ブレークポイントを設定する行のオフセットです。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-166">Offset in the line to set breakpoint at.</span></span> |  
| <span data-ttu-id="f1d3c-167">condition \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-167">condition  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-168">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-168">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="f1d3c-169">指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-169">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="f1d3c-170">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1d3c-170">Returns</span></span> | <span data-ttu-id="f1d3c-171">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-171">Type</span></span> | <span data-ttu-id="f1d3c-172">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-172">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-173">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-173">breakpointId</span></span> | [<span data-ttu-id="f1d3c-174">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-174">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="f1d3c-175">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-175">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="f1d3c-176">場所</span><span class="sxs-lookup"><span data-stu-id="f1d3c-176">locations</span></span> | [<span data-ttu-id="f1d3c-177">Location[]</span><span class="sxs-lookup"><span data-stu-id="f1d3c-177">Location[]</span></span>](#location) | <span data-ttu-id="f1d3c-178">追加時にこのブレークポイントが解決された場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-178">List of the locations this breakpoint resolved into upon addition.</span></span> |  

---  

### <a name="setbreakpoint"></a><span data-ttu-id="f1d3c-179">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f1d3c-179">setBreakpoint</span></span>  

<span data-ttu-id="f1d3c-180">特定の場所に JavaScript ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-180">Sets JavaScript breakpoint at a given location.</span></span>  

| <span data-ttu-id="f1d3c-181">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-181">Parameters</span></span> | <span data-ttu-id="f1d3c-182">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-182">Type</span></span> | <span data-ttu-id="f1d3c-183">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-183">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-184">場所</span><span class="sxs-lookup"><span data-stu-id="f1d3c-184">location</span></span> | [<span data-ttu-id="f1d3c-185">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-185">Location</span></span>](#location) | <span data-ttu-id="f1d3c-186">ブレークポイントを設定する場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-186">Location to set breakpoint in.</span></span> |  
| <span data-ttu-id="f1d3c-187">condition \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-187">condition  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-188">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-188">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="f1d3c-189">指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-189">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="f1d3c-190">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1d3c-190">Returns</span></span> | <span data-ttu-id="f1d3c-191">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-191">Type</span></span> | <span data-ttu-id="f1d3c-192">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-192">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-193">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-193">breakpointId</span></span> | [<span data-ttu-id="f1d3c-194">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-194">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="f1d3c-195">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-195">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="f1d3c-196">actualLocation</span><span class="sxs-lookup"><span data-stu-id="f1d3c-196">actualLocation</span></span> | [<span data-ttu-id="f1d3c-197">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-197">Location</span></span>](#location) | <span data-ttu-id="f1d3c-198">このブレークポイントが解決された場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-198">Location this breakpoint resolved into.</span></span> |  

---  

### <a name="removebreakpoint"></a><span data-ttu-id="f1d3c-199">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f1d3c-199">removeBreakpoint</span></span>  

<span data-ttu-id="f1d3c-200">JavaScript ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-200">Removes JavaScript breakpoint.</span></span>  

| <span data-ttu-id="f1d3c-201">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-201">Parameters</span></span> | <span data-ttu-id="f1d3c-202">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-202">Type</span></span> | <span data-ttu-id="f1d3c-203">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-204">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-204">breakpointId</span></span> | [<span data-ttu-id="f1d3c-205">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-205">BreakpointId</span></span>](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a><span data-ttu-id="f1d3c-206">stepOver</span><span class="sxs-lookup"><span data-stu-id="f1d3c-206">stepOver</span></span>  

<span data-ttu-id="f1d3c-207">ステートメントの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-207">Steps over the statement.</span></span>  

&nbsp;  

---  

### <a name="stepinto"></a><span data-ttu-id="f1d3c-208">stepInto</span><span class="sxs-lookup"><span data-stu-id="f1d3c-208">stepInto</span></span>  

<span data-ttu-id="f1d3c-209">関数呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-209">Steps into the function call.</span></span>  

&nbsp;  

---  

### <a name="stepout"></a><span data-ttu-id="f1d3c-210">stepOut</span><span class="sxs-lookup"><span data-stu-id="f1d3c-210">stepOut</span></span>  

<span data-ttu-id="f1d3c-211">関数呼び出しからステップアウトします。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-211">Steps out of the function call.</span></span>  

&nbsp;  

---  

### <a name="pause"></a><span data-ttu-id="f1d3c-212">pause</span><span class="sxs-lookup"><span data-stu-id="f1d3c-212">pause</span></span>  

<span data-ttu-id="f1d3c-213">次の JavaScript ステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-213">Stops on the next JavaScript statement.</span></span>  

&nbsp;  

---  

### <a name="resume"></a><span data-ttu-id="f1d3c-214">resume</span><span class="sxs-lookup"><span data-stu-id="f1d3c-214">resume</span></span>  

<span data-ttu-id="f1d3c-215">JavaScript の実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-215">Resumes JavaScript execution.</span></span>  

&nbsp;  

---  

### <a name="getscriptsource"></a><span data-ttu-id="f1d3c-216">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="f1d3c-216">getScriptSource</span></span>  

<span data-ttu-id="f1d3c-217">指定された ID を持つスクリプトのソースを返します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-217">Returns source for the script with given ID.</span></span>  

| <span data-ttu-id="f1d3c-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-218">Parameters</span></span> | <span data-ttu-id="f1d3c-219">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-219">Type</span></span> | <span data-ttu-id="f1d3c-220">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-220">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-221">scriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-221">scriptId</span></span> | [<span data-ttu-id="f1d3c-222">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-222">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="f1d3c-223">ソースを取得するスクリプトの ID。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-223">ID of the script to get source for.</span></span> |  
| <span data-ttu-id="f1d3c-224">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1d3c-224">Returns</span></span> | <span data-ttu-id="f1d3c-225">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-225">Type</span></span> | <span data-ttu-id="f1d3c-226">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-226">Details</span></span> |  
|<span data-ttu-id="f1d3c-227">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-227">:---</span></span> |<span data-ttu-id="f1d3c-228">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-228">:---</span></span> |<span data-ttu-id="f1d3c-229">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-229">:---</span></span> |  
| <span data-ttu-id="f1d3c-230">scriptSource</span><span class="sxs-lookup"><span data-stu-id="f1d3c-230">scriptSource</span></span> | `string` | <span data-ttu-id="f1d3c-231">スクリプト ソース。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-231">Script source.</span></span> |  

---  

### <a name="setpauseonexceptions"></a><span data-ttu-id="f1d3c-232">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="f1d3c-232">setPauseOnExceptions</span></span>  

<span data-ttu-id="f1d3c-233">例外状態の一時停止を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-233">Defines pause on exceptions state.</span></span>  <span data-ttu-id="f1d3c-234">すべての例外、キャッチされていない例外、または例外なしで停止する設定が可能です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-234">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span>  <span data-ttu-id="f1d3c-235">例外状態の最初の一時停止はです `none` 。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-235">Initial pause on exceptions state is `none`.</span></span>  

| <span data-ttu-id="f1d3c-236">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-236">Parameters</span></span> | <span data-ttu-id="f1d3c-237">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-237">Type</span></span> | <span data-ttu-id="f1d3c-238">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-238">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-239">状態</span><span class="sxs-lookup"><span data-stu-id="f1d3c-239">state</span></span> | `string` | <span data-ttu-id="f1d3c-240">例外モードで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-240">Pause on exceptions mode.</span></span>  <span data-ttu-id="f1d3c-241">使用できる値:  `none` `uncaught` 、、および</span><span class="sxs-lookup"><span data-stu-id="f1d3c-241">Allowed values:  `none`, `uncaught`, and</span></span> `all` |  

---  

### <a name="evaluateoncallframe"></a><span data-ttu-id="f1d3c-242">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="f1d3c-242">evaluateOnCallFrame</span></span>  

<span data-ttu-id="f1d3c-243">指定された呼び出しフレームの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-243">Evaluates expression on a given call frame.</span></span>  

| <span data-ttu-id="f1d3c-244">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-244">Parameters</span></span> | <span data-ttu-id="f1d3c-245">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-245">Type</span></span> | <span data-ttu-id="f1d3c-246">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-246">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-247">callFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-247">callFrameId</span></span> | [<span data-ttu-id="f1d3c-248">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-248">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="f1d3c-249">フレーム識別子を呼び出して評価します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-249">Call frame identifier to evaluate on.</span></span> |  
| <span data-ttu-id="f1d3c-250">式</span><span class="sxs-lookup"><span data-stu-id="f1d3c-250">expression</span></span> | `string` | <span data-ttu-id="f1d3c-251">評価する式。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-251">Expression to evaluate.</span></span> |  
| <span data-ttu-id="f1d3c-252">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1d3c-252">Returns</span></span> | <span data-ttu-id="f1d3c-253">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-253">Type</span></span> | <span data-ttu-id="f1d3c-254">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-254">Details</span></span> |  
|<span data-ttu-id="f1d3c-255">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-255">:---</span></span> |<span data-ttu-id="f1d3c-256">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-256">:---</span></span> |<span data-ttu-id="f1d3c-257">:---</span><span class="sxs-lookup"><span data-stu-id="f1d3c-257">:---</span></span> |  
| <span data-ttu-id="f1d3c-258">result</span><span class="sxs-lookup"><span data-stu-id="f1d3c-258">result</span></span> | [<span data-ttu-id="f1d3c-259">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="f1d3c-259">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="f1d3c-260">評価結果のオブジェクト ラッパー。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-260">Object wrapper for the evaluation result.</span></span> |  

---  

### <a name="setvariablevalue"></a><span data-ttu-id="f1d3c-261">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="f1d3c-261">setVariableValue</span></span>  

<span data-ttu-id="f1d3c-262">呼び出しフレーム内の変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-262">Changes value of variable in a callframe.</span></span>  <span data-ttu-id="f1d3c-263">オブジェクト ベースのスコープはサポートされていないので、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-263">Object-based scopes are not supported and must be mutated manually.</span></span>  

| <span data-ttu-id="f1d3c-264">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-264">Parameters</span></span> | <span data-ttu-id="f1d3c-265">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-265">Type</span></span> | <span data-ttu-id="f1d3c-266">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-266">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-267">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="f1d3c-267">scopeNumber</span></span> | `integer` | <span data-ttu-id="f1d3c-268">スコープ チェーンに記載されている範囲の 0 からベースの数。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-268">0-based number of scope as was listed in scope chain.</span></span>  <span data-ttu-id="f1d3c-269">のみ `local` 、 `closure` および `catch` スコープの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-269">Only `local`, `closure`, and `catch` scope types are allowed.</span></span>  <span data-ttu-id="f1d3c-270">他のスコープは手動で操作できます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-270">Other scopes could be manipulated manually.</span></span> |  
| <span data-ttu-id="f1d3c-271">variableName</span><span class="sxs-lookup"><span data-stu-id="f1d3c-271">variableName</span></span> | `string` | <span data-ttu-id="f1d3c-272">変数名。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-272">Variable name.</span></span> |  
| <span data-ttu-id="f1d3c-273">newValue</span><span class="sxs-lookup"><span data-stu-id="f1d3c-273">newValue</span></span> | [<span data-ttu-id="f1d3c-274">Runtime.CallArgument</span><span class="sxs-lookup"><span data-stu-id="f1d3c-274">Runtime.CallArgument</span></span>](./runtime.md#callargument) | <span data-ttu-id="f1d3c-275">新しい変数値。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-275">New variable value.</span></span> |  
| <span data-ttu-id="f1d3c-276">callFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-276">callFrameId</span></span> | [<span data-ttu-id="f1d3c-277">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-277">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="f1d3c-278">変数を保持する呼び出しフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-278">ID of callframe that holds variable.</span></span> |  

---  

### <a name="setblackboxpatterns"></a><span data-ttu-id="f1d3c-279">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="f1d3c-279">setBlackboxPatterns</span></span>  

<span data-ttu-id="f1d3c-280">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-280">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-281">以前のブラックボックス パターンを渡されたパターンに置き換える。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-281">Replace previous blackbox patterns with passed ones.</span></span>  <span data-ttu-id="f1d3c-282">バックエンドは、パターンの 1 つに一致する URL を持つスクリプトのステップ/一時停止を強制的にスキップします。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-282">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span>  <span data-ttu-id="f1d3c-283">デバッガーは、何回か実行することで、ブラックボックス化されたスクリプトを残して、失敗した場合に最終的に `step in` `step out` 実行を試みます。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-283">The debugger will try to leave blackboxed script by performing `step in` several times, finally resorting to `step out` if unsuccessful.</span></span>  

| <span data-ttu-id="f1d3c-284">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-284">Parameters</span></span> | <span data-ttu-id="f1d3c-285">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-285">Type</span></span> | <span data-ttu-id="f1d3c-286">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-286">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-287">パターン</span><span class="sxs-lookup"><span data-stu-id="f1d3c-287">patterns</span></span> | `string[]` | <span data-ttu-id="f1d3c-288">スクリプトの URL でブラックボックスの状態を確認するために使用される正規表現の配列。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-288">Array of regexps that will be used to check script url for blackbox state.</span></span> |  

---  

### <a name="mssetdebuggerpropertyvalue"></a><span data-ttu-id="f1d3c-289">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="f1d3c-289">msSetDebuggerPropertyValue</span></span>  

<span data-ttu-id="f1d3c-290">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-290">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-291">Microsoft: 指定したデバッガー プロパティを指定した値に設定します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-291">Microsoft:  Sets the specified debugger property to the specified value.</span></span>  

| <span data-ttu-id="f1d3c-292">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-292">Parameters</span></span> | <span data-ttu-id="f1d3c-293">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-293">Type</span></span> | <span data-ttu-id="f1d3c-294">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-294">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-295">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-295">debuggerPropertyId</span></span> | `string` | <span data-ttu-id="f1d3c-296">Microsoft: 設定するプロパティ ID \(つまり、msDebuggerPropertyId\) です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-296">Microsoft: The property ID \(i.e. msDebuggerPropertyId\) to set.</span></span> |  
| <span data-ttu-id="f1d3c-297">newValue</span><span class="sxs-lookup"><span data-stu-id="f1d3c-297">newValue</span></span> | `string` | &nbsp; |  

---  

## <a name="events"></a><span data-ttu-id="f1d3c-298">イベント</span><span class="sxs-lookup"><span data-stu-id="f1d3c-298">Events</span></span>  

### <a name="scriptparsed"></a><span data-ttu-id="f1d3c-299">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="f1d3c-299">scriptParsed</span></span>  

<span data-ttu-id="f1d3c-300">スクリプトの解析時に発生します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-300">Fired when the script is parsed.</span></span>  <span data-ttu-id="f1d3c-301">このイベントは、デバッガーを有効にした時点で、既知のスクリプトおよび未記録のスクリプトに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-301">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>  

| <span data-ttu-id="f1d3c-302">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-302">Parameters</span></span> | <span data-ttu-id="f1d3c-303">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-303">Type</span></span> | <span data-ttu-id="f1d3c-304">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-304">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-305">scriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-305">scriptId</span></span> | [<span data-ttu-id="f1d3c-306">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-306">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="f1d3c-307">解析されたスクリプトの識別子。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-307">Identifier of the script parsed.</span></span> |  
| <span data-ttu-id="f1d3c-308">url</span><span class="sxs-lookup"><span data-stu-id="f1d3c-308">url</span></span> | `string` | <span data-ttu-id="f1d3c-309">解析されたスクリプトの URL または名前 \(if any\)。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-309">URL or name of the script parsed \(if any\).</span></span> |  
| <span data-ttu-id="f1d3c-310">startLine</span><span class="sxs-lookup"><span data-stu-id="f1d3c-310">startLine</span></span> | `integer` | <span data-ttu-id="f1d3c-311">リソース内のスクリプトの行オフセットで、指定された URL \(スクリプト タグ\の場合)。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-311">Line offset of the script within the resource with given URL \(for script tags\).</span></span> |  
| <span data-ttu-id="f1d3c-312">startColumn</span><span class="sxs-lookup"><span data-stu-id="f1d3c-312">startColumn</span></span> | `integer` | <span data-ttu-id="f1d3c-313">指定された URL を持つリソース内のスクリプトの列オフセット。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-313">Column offset of the script within the resource with given URL.</span></span> |  
| <span data-ttu-id="f1d3c-314">endLine</span><span class="sxs-lookup"><span data-stu-id="f1d3c-314">endLine</span></span> | `integer` | <span data-ttu-id="f1d3c-315">スクリプトの最後の行。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-315">Last line of the script.</span></span> |  
| <span data-ttu-id="f1d3c-316">endColumn</span><span class="sxs-lookup"><span data-stu-id="f1d3c-316">endColumn</span></span> | `integer` | <span data-ttu-id="f1d3c-317">スクリプトの最後の行の長さ。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-317">Length of the last line of the script.</span></span> |  
| <span data-ttu-id="f1d3c-318">executionContextId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-318">executionContextId</span></span> | [<span data-ttu-id="f1d3c-319">Runtime.ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-319">Runtime.ExecutionContextId</span></span>](./runtime.md#executioncontextid) | <span data-ttu-id="f1d3c-320">スクリプト作成コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-320">Specifies script creation context.</span></span> |  
| <span data-ttu-id="f1d3c-321">sourceMapURL \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-321">sourceMapURL  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-322">スクリプトに関連付けられたソース マップの URL (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-322">URL of source map associated with script (if any).</span></span> |  
| <span data-ttu-id="f1d3c-323">length \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-323">length  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-324">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-324">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-325">このスクリプトの長さ。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-325">This script length.</span></span> |  
| <span data-ttu-id="f1d3c-326">msParentId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-326">msParentId  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-327">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-327">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-328">これは親ドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-328">This is the parent document ID.</span></span> |  
| <span data-ttu-id="f1d3c-329">msMimeType \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-329">msMimeType  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-330">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-330">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-331">これは MIME の種類です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-331">This is the mime type.</span></span> |  
| <span data-ttu-id="f1d3c-332">msIsDynamicCode \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-332">msIsDynamicCode  \(optional\)</span></span> | `boolean` | <span data-ttu-id="f1d3c-333">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-333">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-334">これは、動的コードであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-334">This indicates whether it is dynamic code.</span></span> |  
| <span data-ttu-id="f1d3c-335">msLongDocumentId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-335">msLongDocumentId  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-336">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-336">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-337">これは長いドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-337">This is the long document ID.</span></span> |  

---  

### <a name="breakpointresolved"></a><span data-ttu-id="f1d3c-338">ブレークポイントResolved</span><span class="sxs-lookup"><span data-stu-id="f1d3c-338">breakpointResolved</span></span>  

<span data-ttu-id="f1d3c-339">ブレークポイントが実際のスクリプトと場所に解決された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-339">Fired when breakpoint is resolved to an actual script and location.</span></span>  

| <span data-ttu-id="f1d3c-340">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-340">Parameters</span></span> | <span data-ttu-id="f1d3c-341">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-341">Type</span></span> | <span data-ttu-id="f1d3c-342">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-342">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-343">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-343">breakpointId</span></span> | [<span data-ttu-id="f1d3c-344">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-344">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="f1d3c-345">ブレークポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-345">Breakpoint unique identifier.</span></span> |  
| <span data-ttu-id="f1d3c-346">場所</span><span class="sxs-lookup"><span data-stu-id="f1d3c-346">location</span></span> | [<span data-ttu-id="f1d3c-347">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-347">Location</span></span>](#location) | <span data-ttu-id="f1d3c-348">実際のブレークポイントの場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-348">Actual breakpoint location.</span></span> |  
| <span data-ttu-id="f1d3c-349">msLength \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-349">msLength  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-350">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-350">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-351">Microsoft: ブレークポイントの場所にあるコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-351">Microsoft:  Length of code \(i.e. number of characters\) at the breakpoint location.</span></span> |  

---  

### <a name="paused"></a><span data-ttu-id="f1d3c-352">paused (一時停止)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-352">paused</span></span>  

<span data-ttu-id="f1d3c-353">ブレークポイントまたは例外のデバッガーが壊れた場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-353">Fired when the debuggers breaks for a breakpoint or exception.</span></span>  

| <span data-ttu-id="f1d3c-354">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d3c-354">Parameters</span></span> | <span data-ttu-id="f1d3c-355">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-355">Type</span></span> | <span data-ttu-id="f1d3c-356">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-356">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-357">callFrames</span><span class="sxs-lookup"><span data-stu-id="f1d3c-357">callFrames</span></span> | [<span data-ttu-id="f1d3c-358">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="f1d3c-358">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="f1d3c-359">デバッガーが停止したスタックを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-359">Call stack the debugger stopped on.</span></span> |  
| <span data-ttu-id="f1d3c-360">理由</span><span class="sxs-lookup"><span data-stu-id="f1d3c-360">reason</span></span> | `string` | <span data-ttu-id="f1d3c-361">理由を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-361">Pause reason.</span></span>  <span data-ttu-id="f1d3c-362">使用できる値:  `breakpoint` `step` `exception` 、、、および</span><span class="sxs-lookup"><span data-stu-id="f1d3c-362">Allowed values:  `breakpoint`, `step`, `exception`, and</span></span> `other` |  
| <span data-ttu-id="f1d3c-363">data \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-363">data  \(optional\)</span></span> | `object` | <span data-ttu-id="f1d3c-364">ブレーク固有の補助プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-364">Object containing break-specific auxiliary properties.</span></span> |  
| <span data-ttu-id="f1d3c-365">hitBreakpoints \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-365">hitBreakpoints  \(optional\)</span></span> | `string[]` | <span data-ttu-id="f1d3c-366">ブレークポイントのヒットの ID</span><span class="sxs-lookup"><span data-stu-id="f1d3c-366">Hit breakpoints IDs</span></span> |  

---  

### <a name="resumed"></a><span data-ttu-id="f1d3c-367">再開</span><span class="sxs-lookup"><span data-stu-id="f1d3c-367">resumed</span></span>  

<span data-ttu-id="f1d3c-368">デバッガーが実行を再開すると発生します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-368">Fired when the debugger resumes execution.</span></span>  

&nbsp;  

---  

## <a name="types"></a><span data-ttu-id="f1d3c-369">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-369">Types</span></span>  

### <a name="breakpointid-string"></a><span data-ttu-id="f1d3c-370">ブレークポイントId 文字列</span><span class="sxs-lookup"><span data-stu-id="f1d3c-370">BreakpointId string</span></span>  

<a name="breakpointid"></a>  

<span data-ttu-id="f1d3c-371">ブレークポイント識別子。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-371">Breakpoint identifier.</span></span>  

&nbsp;  

---  

### <a name="callframeid-string"></a><span data-ttu-id="f1d3c-372">CallFrameId 文字列</span><span class="sxs-lookup"><span data-stu-id="f1d3c-372">CallFrameId string</span></span>  

<a name="callframeid"></a>  

<span data-ttu-id="f1d3c-373">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-373">Call frame identifier.</span></span>  

&nbsp;  

---  

### <a name="location-object"></a><span data-ttu-id="f1d3c-374">Location オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f1d3c-374">Location object</span></span>  

<a name="location"></a>  

<span data-ttu-id="f1d3c-375">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-375">Location in the source code.</span></span>  

| <span data-ttu-id="f1d3c-376">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1d3c-376">Properties</span></span> | <span data-ttu-id="f1d3c-377">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-377">Type</span></span> | <span data-ttu-id="f1d3c-378">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-378">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-379">scriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-379">scriptId</span></span> | [<span data-ttu-id="f1d3c-380">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-380">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="f1d3c-381">で報告されるスクリプト識別子 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-381">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="f1d3c-382">lineNumber</span><span class="sxs-lookup"><span data-stu-id="f1d3c-382">lineNumber</span></span> | `integer` | <span data-ttu-id="f1d3c-383">スクリプト \(0-based\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-383">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="f1d3c-384">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-384">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-385">スクリプト \(0-based\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-385">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="f1d3c-386">msLength</span><span class="sxs-lookup"><span data-stu-id="f1d3c-386">msLength</span></span> | `integer` | <span data-ttu-id="f1d3c-387">Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-387">Microsoft: Length of code \(i.e. number of characters\) at this call frame.</span></span> |  

---  

### <a name="breaklocation-object"></a><span data-ttu-id="f1d3c-388">BreakLocation オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f1d3c-388">BreakLocation object</span></span>  

<a name="breaklocation"></a>  

<span data-ttu-id="f1d3c-389">ソース コード内の場所を壊します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-389">Break location in the source code.</span></span>  

| <span data-ttu-id="f1d3c-390">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1d3c-390">Properties</span></span> | <span data-ttu-id="f1d3c-391">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-391">Type</span></span> | <span data-ttu-id="f1d3c-392">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-392">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-393">scriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-393">scriptId</span></span> | [<span data-ttu-id="f1d3c-394">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-394">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="f1d3c-395">で報告されるスクリプト識別子 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-395">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="f1d3c-396">lineNumber</span><span class="sxs-lookup"><span data-stu-id="f1d3c-396">lineNumber</span></span> | `integer` | <span data-ttu-id="f1d3c-397">スクリプト \(0-based\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-397">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="f1d3c-398">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-398">columnNumber  \(optional\)</span></span> | `integer` | <span data-ttu-id="f1d3c-399">スクリプト \(0-based\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-399">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="f1d3c-400">msLength</span><span class="sxs-lookup"><span data-stu-id="f1d3c-400">msLength</span></span> | `integer` | <span data-ttu-id="f1d3c-401">Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-401">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  
| <span data-ttu-id="f1d3c-402">型 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-402">type  \(optional\)</span></span> | `string` | <span data-ttu-id="f1d3c-403">使用できる値:  `debuggerStatement` `call` 、、および</span><span class="sxs-lookup"><span data-stu-id="f1d3c-403">Allowed values:  `debuggerStatement`, `call`, and</span></span> `return` |  

---  

### <a name="callframe-object"></a><span data-ttu-id="f1d3c-404">CallFrame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f1d3c-404">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="f1d3c-405">JavaScript 呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-405">JavaScript call frame.</span></span>  <span data-ttu-id="f1d3c-406">呼び出しフレームの配列は、呼び出し履歴を形成します。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-406">Array of call frames form the call stack.</span></span>  

| <span data-ttu-id="f1d3c-407">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1d3c-407">Properties</span></span> | <span data-ttu-id="f1d3c-408">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-408">Type</span></span> | <span data-ttu-id="f1d3c-409">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-409">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-410">callFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-410">callFrameId</span></span> | [<span data-ttu-id="f1d3c-411">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="f1d3c-411">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="f1d3c-412">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-412">Call frame identifier.</span></span>  <span data-ttu-id="f1d3c-413">この識別子は、デバッガーが一時停止している間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-413">This identifier is only valid while the debugger is paused.</span></span> |  
| <span data-ttu-id="f1d3c-414">functionName</span><span class="sxs-lookup"><span data-stu-id="f1d3c-414">functionName</span></span> | `string` | <span data-ttu-id="f1d3c-415">この呼び出しフレームで呼び出される JavaScript 関数の名前。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-415">Name of the JavaScript function called on this call frame.</span></span> |  
| <span data-ttu-id="f1d3c-416">functionLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-416">functionLocation  \(optional\)</span></span> | [<span data-ttu-id="f1d3c-417">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-417">Location</span></span>](#location) | <span data-ttu-id="f1d3c-418">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-418">**Experimental**.</span></span>  <span data-ttu-id="f1d3c-419">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-419">Location in the source code.</span></span> |  
| <span data-ttu-id="f1d3c-420">場所</span><span class="sxs-lookup"><span data-stu-id="f1d3c-420">location</span></span> | [<span data-ttu-id="f1d3c-421">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-421">Location</span></span>](#location) | <span data-ttu-id="f1d3c-422">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-422">Location in the source code.</span></span> |  
| <span data-ttu-id="f1d3c-423">url</span><span class="sxs-lookup"><span data-stu-id="f1d3c-423">url</span></span> | `string` | <span data-ttu-id="f1d3c-424">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-424">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="f1d3c-425">scopeChain</span><span class="sxs-lookup"><span data-stu-id="f1d3c-425">scopeChain</span></span> | [<span data-ttu-id="f1d3c-426">Scope[]</span><span class="sxs-lookup"><span data-stu-id="f1d3c-426">Scope[]</span></span>](#scope) | <span data-ttu-id="f1d3c-427">この呼び出しフレームのスコープ チェーン。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-427">Scope chain for this call frame.</span></span> |  
| <span data-ttu-id="f1d3c-428">これ</span><span class="sxs-lookup"><span data-stu-id="f1d3c-428">this</span></span> | [<span data-ttu-id="f1d3c-429">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="f1d3c-429">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | `this` <span data-ttu-id="f1d3c-430">この呼び出しフレームのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-430">object for this call frame.</span></span> |  
| <span data-ttu-id="f1d3c-431">returnValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-431">returnValue  \(optional\)</span></span> | [<span data-ttu-id="f1d3c-432">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="f1d3c-432">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="f1d3c-433">関数が戻り値である場合に返される値。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-433">The value being returned, if the function is at return point.</span></span> |  

---  

### <a name="scope-object"></a><span data-ttu-id="f1d3c-434">Scope オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f1d3c-434">Scope object</span></span>  

<a name="scope"></a>  

<span data-ttu-id="f1d3c-435">スコープの説明。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-435">Scope description.</span></span>  

| <span data-ttu-id="f1d3c-436">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1d3c-436">Properties</span></span> | <span data-ttu-id="f1d3c-437">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-437">Type</span></span> | <span data-ttu-id="f1d3c-438">詳細</span><span class="sxs-lookup"><span data-stu-id="f1d3c-438">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f1d3c-439">型</span><span class="sxs-lookup"><span data-stu-id="f1d3c-439">type</span></span> | `string` | <span data-ttu-id="f1d3c-440">スコープの種類。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-440">Scope type.</span></span>  <span data-ttu-id="f1d3c-441">使用できる値: `global` `local` `with` 、、、、、、、 `closure` `catch` `block` `script` `eval`</span><span class="sxs-lookup"><span data-stu-id="f1d3c-441">Allowed values:  `global`, `local`, `with`, `closure`, `catch`, `block`, `script`, `eval`, and</span></span> `module` |  
| <span data-ttu-id="f1d3c-442">object</span><span class="sxs-lookup"><span data-stu-id="f1d3c-442">object</span></span> | [<span data-ttu-id="f1d3c-443">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="f1d3c-443">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="f1d3c-444">スコープを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-444">Object representing the scope.</span></span>  <span data-ttu-id="f1d3c-445">For and scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as `global` `with` its properties.</span><span class="sxs-lookup"><span data-stu-id="f1d3c-445">For `global` and `with` scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span> |  
| <span data-ttu-id="f1d3c-446">name \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-446">name  \(optional\)</span></span> | `string` | &nbsp; |  
| <span data-ttu-id="f1d3c-447">startLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-447">startLocation  \(optional\)</span></span> | [<span data-ttu-id="f1d3c-448">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-448">Location</span></span>](#location) | <span data-ttu-id="f1d3c-449">スコープが開始するソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-449">Location in the source code where scope starts.</span></span> |  
| <span data-ttu-id="f1d3c-450">endLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="f1d3c-450">endLocation  \(optional\)</span></span> | [<span data-ttu-id="f1d3c-451">Location</span><span class="sxs-lookup"><span data-stu-id="f1d3c-451">Location</span></span>](#location) | <span data-ttu-id="f1d3c-452">スコープが終了するソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="f1d3c-452">Location in the source code where scope ends.</span></span> |  

---  

## <a name="dependencies"></a><span data-ttu-id="f1d3c-453">依存関係</span><span class="sxs-lookup"><span data-stu-id="f1d3c-453">Dependencies</span></span>  

[<span data-ttu-id="f1d3c-454">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f1d3c-454">Runtime</span></span>](./runtime.md)  
