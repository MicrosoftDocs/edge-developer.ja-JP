---
description: デバッガー ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 デバッガー ドメインは、JavaScript のデバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
title: デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 00c410812edd4d11e9904a489955e7fd218a7e5d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398176"
---
# <a name="debugger-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="aec8b-105">デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="aec8b-105">Debugger Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="aec8b-106">デバッガー ドメインは、JavaScript のデバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-106">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="aec8b-107">ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-107">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>

| <span data-ttu-id="aec8b-108">分類</span><span class="sxs-lookup"><span data-stu-id="aec8b-108">Classification</span></span> | <span data-ttu-id="aec8b-109">Members</span><span class="sxs-lookup"><span data-stu-id="aec8b-109">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="aec8b-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="aec8b-110">Methods</span></span>**](#methods) | <span data-ttu-id="aec8b-111">[](#enable)enable [](#disable), disable , [getPossibleBreakpoints](#getpossiblebreakpoints) [](#pause), [setBreakpointByUrl , setBreakpointByUrl](#setbreakpointbyurl) [](#stepover), [setBreakpoint](#setbreakpoint) [](#setbreakpointsactive), [stepOver](#removebreakpoint), [stepInto](#stepout), stepOut , pause , [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [](#stepinto) [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="aec8b-111">[enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint](#setbreakpoint), [removeBreakpoint](#removebreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue)</span></span> |  
| [**<span data-ttu-id="aec8b-112">イベント</span><span class="sxs-lookup"><span data-stu-id="aec8b-112">Events</span></span>**](#events) | <span data-ttu-id="aec8b-113">[scriptParsed](#scriptparsed), [ブレークポイントResolved](#breakpointresolved), [一時停止](#paused), [再開](#resumed)</span><span class="sxs-lookup"><span data-stu-id="aec8b-113">[scriptParsed](#scriptparsed), [breakpointResolved](#breakpointresolved), [paused](#paused), [resumed](#resumed)</span></span> |  
| [**<span data-ttu-id="aec8b-114">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-114">Types</span></span>**](#types) | <span data-ttu-id="aec8b-115">[ブレークポイント Id](#breakpointid)、 [CallFrameId](#callframeid)、 [Location](#location)、 [BreakLocation](#breaklocation)、 [CallFrame](#callframe)、 [Scope](#scope)</span><span class="sxs-lookup"><span data-stu-id="aec8b-115">[BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope)</span></span> |  
| [**<span data-ttu-id="aec8b-116">依存関係</span><span class="sxs-lookup"><span data-stu-id="aec8b-116">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="aec8b-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="aec8b-117">Runtime</span></span>](./runtime.md) |  

## <a name="methods"></a><span data-ttu-id="aec8b-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="aec8b-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="aec8b-119">[有効]</span><span class="sxs-lookup"><span data-stu-id="aec8b-119">enable</span></span>  

<span data-ttu-id="aec8b-120">指定したページのデバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="aec8b-120">Enables debugger for the given page.</span></span> <span data-ttu-id="aec8b-121">クライアントは、このコマンドの結果を受信するまで、デバッグが有効になっていると見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec8b-121">Clients should not assume that the debugging has been enabled until the result for this command is received.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="aec8b-122">[無効]</span><span class="sxs-lookup"><span data-stu-id="aec8b-122">disable</span></span>  

<span data-ttu-id="aec8b-123">特定のページのデバッガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aec8b-123">Disables debugger for given page.</span></span>  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a><span data-ttu-id="aec8b-124">getPossibleBreakpoints</span><span class="sxs-lookup"><span data-stu-id="aec8b-124">getPossibleBreakpoints</span></span>  

<span data-ttu-id="aec8b-125">ブレークポイントの可能な場所を返します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-125">Returns possible locations for breakpoint.</span></span> <span data-ttu-id="aec8b-126">開始範囲と終了範囲の場所の scriptId は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec8b-126">scriptId in start and end range locations should be the same.</span></span>  

| <span data-ttu-id="aec8b-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-127">Parameters</span></span> | <span data-ttu-id="aec8b-128">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-128">Type</span></span> | <span data-ttu-id="aec8b-129">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-129">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-130">start</span><span class="sxs-lookup"><span data-stu-id="aec8b-130">start</span></span> | [<span data-ttu-id="aec8b-131">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-131">Location</span></span>](#location) | <span data-ttu-id="aec8b-132">範囲の開始位置からブレークポイントの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-132">Start of range to search possible breakpoint locations in.</span></span> |  
| <span data-ttu-id="aec8b-133">終了</span><span class="sxs-lookup"><span data-stu-id="aec8b-133">end</span></span> | [<span data-ttu-id="aec8b-134">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-134">Location</span></span>](#location) | <span data-ttu-id="aec8b-135">\(excluding\) でブレークポイントの場所を検索する範囲の末尾。</span><span class="sxs-lookup"><span data-stu-id="aec8b-135">End of range to search possible breakpoint locations in \(excluding\).</span></span>  <span data-ttu-id="aec8b-136">指定しない場合は、スクリプトの末尾が範囲の末尾として使用されます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-136">When not specified, end of scripts is used as end of range.</span></span> |  

| <span data-ttu-id="aec8b-137">戻り値</span><span class="sxs-lookup"><span data-stu-id="aec8b-137">Returns</span></span> | <span data-ttu-id="aec8b-138">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-138">Type</span></span> | <span data-ttu-id="aec8b-139">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-139">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-140">場所</span><span class="sxs-lookup"><span data-stu-id="aec8b-140">locations</span></span> | [<span data-ttu-id="aec8b-141">BreakLocation</span><span class="sxs-lookup"><span data-stu-id="aec8b-141">BreakLocation</span></span>](#breaklocation) | <span data-ttu-id="aec8b-142">考えられるブレークポイントの場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="aec8b-142">List of the possible breakpoint locations.</span></span> |  

---  

### <a name="setbreakpointsactive"></a><span data-ttu-id="aec8b-143">setBreakpointsActive</span><span class="sxs-lookup"><span data-stu-id="aec8b-143">setBreakpointsActive</span></span>  

<span data-ttu-id="aec8b-144">ページ上のすべてのブレークポイントをアクティブ化/非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-144">Activates / deactivates all breakpoints on the page.</span></span>  

| <span data-ttu-id="aec8b-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-145">Parameters</span></span> | <span data-ttu-id="aec8b-146">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-146">Type</span></span> | <span data-ttu-id="aec8b-147">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-147">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-148">active</span><span class="sxs-lookup"><span data-stu-id="aec8b-148">active</span></span> | `boolean` | <span data-ttu-id="aec8b-149">ブレークポイントのアクティブな状態の新しい値。</span><span class="sxs-lookup"><span data-stu-id="aec8b-149">New value for breakpoints active state.</span></span> | 

---  

### <a name="setbreakpointbyurl"></a><span data-ttu-id="aec8b-150">setBreakpointByUrl</span><span class="sxs-lookup"><span data-stu-id="aec8b-150">setBreakpointByUrl</span></span>  

<span data-ttu-id="aec8b-151">URL または URL 正規表現で指定された特定の場所に JavaScript ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-151">Sets JavaScript breakpoint at given location specified either by URL or URL regex.</span></span>  <span data-ttu-id="aec8b-152">このコマンドを発行すると、解析済みのすべてのスクリプトにブレークポイントが解決され、プロパティに返 `locations` されます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-152">Once this command is issued, all existing parsed scripts will have breakpoints resolved and returned in `locations` property.</span></span>  <span data-ttu-id="aec8b-153">さらに一致するスクリプトの解析により、後続の `breakpointResolved` イベントが発行されます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-153">Further matching script parsing will result in subsequent `breakpointResolved` events issued.</span></span>  <span data-ttu-id="aec8b-154">この論理ブレークポイントは、ページの再読み込みから存続します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-154">This logical breakpoint will survive page reloads.</span></span>  

| <span data-ttu-id="aec8b-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-155">Parameters</span></span> | <span data-ttu-id="aec8b-156">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-156">Type</span></span> | <span data-ttu-id="aec8b-157">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-158">lineNumber</span><span class="sxs-lookup"><span data-stu-id="aec8b-158">lineNumber</span></span> | `integer` | <span data-ttu-id="aec8b-159">ブレークポイントを設定する行番号。</span><span class="sxs-lookup"><span data-stu-id="aec8b-159">Line number to set breakpoint at.</span></span> | 
| <span data-ttu-id="aec8b-160">url \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-160">url \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-161">ブレークポイントを設定するリソースの URL。</span><span class="sxs-lookup"><span data-stu-id="aec8b-161">URL of the resources to set breakpoint on.</span></span> |  
| <span data-ttu-id="aec8b-162">urlRegex \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-162">urlRegex \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-163">ブレークポイントを設定するリソースの URL の正規表現パターン。</span><span class="sxs-lookup"><span data-stu-id="aec8b-163">Regex pattern for the URLs of the resources to set breakpoints on.</span></span>  <span data-ttu-id="aec8b-164">指定 `url` するか `urlRegex` 、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec8b-164">Either `url` or `urlRegex` must be specified.</span></span> |  
| <span data-ttu-id="aec8b-165">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-165">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-166">ブレークポイントを設定する行のオフセットです。</span><span class="sxs-lookup"><span data-stu-id="aec8b-166">Offset in the line to set breakpoint at.</span></span> |  
| <span data-ttu-id="aec8b-167">condition \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-167">condition \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-168">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="aec8b-168">Expression to use as a breakpoint condition.</span></span> <span data-ttu-id="aec8b-169">指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-169">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="aec8b-170">戻り値</span><span class="sxs-lookup"><span data-stu-id="aec8b-170">Returns</span></span> | <span data-ttu-id="aec8b-171">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-171">Type</span></span> | <span data-ttu-id="aec8b-172">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-172">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-173">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-173">breakpointId</span></span> | [<span data-ttu-id="aec8b-174">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-174">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="aec8b-175">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="aec8b-175">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="aec8b-176">場所</span><span class="sxs-lookup"><span data-stu-id="aec8b-176">locations</span></span> | [<span data-ttu-id="aec8b-177">Location[]</span><span class="sxs-lookup"><span data-stu-id="aec8b-177">Location[]</span></span>](#location) | <span data-ttu-id="aec8b-178">追加時にこのブレークポイントが解決された場所の一覧。</span><span class="sxs-lookup"><span data-stu-id="aec8b-178">List of the locations this breakpoint resolved into upon addition.</span></span> |  

---  

### <a name="setbreakpoint"></a><span data-ttu-id="aec8b-179">setBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aec8b-179">setBreakpoint</span></span>  

<span data-ttu-id="aec8b-180">特定の場所に JavaScript ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-180">Sets JavaScript breakpoint at a given location.</span></span>  

| <span data-ttu-id="aec8b-181">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-181">Parameters</span></span> | <span data-ttu-id="aec8b-182">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-182">Type</span></span> | <span data-ttu-id="aec8b-183">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-183">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-184">場所</span><span class="sxs-lookup"><span data-stu-id="aec8b-184">location</span></span> | [<span data-ttu-id="aec8b-185">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-185">Location</span></span>](#location) | <span data-ttu-id="aec8b-186">ブレークポイントを設定する場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-186">Location to set breakpoint in.</span></span> |  
| <span data-ttu-id="aec8b-187">condition \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-187">condition \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-188">ブレークポイント条件として使用する式。</span><span class="sxs-lookup"><span data-stu-id="aec8b-188">Expression to use as a breakpoint condition.</span></span>  <span data-ttu-id="aec8b-189">指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-189">When specified, debugger will only stop on the breakpoint if this expression evaluates to true.</span></span> |  

| <span data-ttu-id="aec8b-190">戻り値</span><span class="sxs-lookup"><span data-stu-id="aec8b-190">Returns</span></span> | <span data-ttu-id="aec8b-191">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-191">Type</span></span> | <span data-ttu-id="aec8b-192">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-192">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-193">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-193">breakpointId</span></span> | [<span data-ttu-id="aec8b-194">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-194">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="aec8b-195">追加の参照用に作成されたブレークポイントの ID。</span><span class="sxs-lookup"><span data-stu-id="aec8b-195">ID of the created breakpoint for further reference.</span></span> |  
| <span data-ttu-id="aec8b-196">actualLocation</span><span class="sxs-lookup"><span data-stu-id="aec8b-196">actualLocation</span></span> | [<span data-ttu-id="aec8b-197">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-197">Location</span></span>](#location) | <span data-ttu-id="aec8b-198">このブレークポイントが解決された場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-198">Location this breakpoint resolved into.</span></span> |  

---  

### <a name="removebreakpoint"></a><span data-ttu-id="aec8b-199">removeBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aec8b-199">removeBreakpoint</span></span>  

<span data-ttu-id="aec8b-200">JavaScript ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-200">Removes JavaScript breakpoint.</span></span>  

| <span data-ttu-id="aec8b-201">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-201">Parameters</span></span> | <span data-ttu-id="aec8b-202">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-202">Type</span></span> | <span data-ttu-id="aec8b-203">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-204">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-204">breakpointId</span></span> | [<span data-ttu-id="aec8b-205">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-205">BreakpointId</span></span>](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a><span data-ttu-id="aec8b-206">stepOver</span><span class="sxs-lookup"><span data-stu-id="aec8b-206">stepOver</span></span>  

<span data-ttu-id="aec8b-207">ステートメントの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-207">Steps over the statement.</span></span>  

&nbsp;  

---  

### <a name="stepinto"></a><span data-ttu-id="aec8b-208">stepInto</span><span class="sxs-lookup"><span data-stu-id="aec8b-208">stepInto</span></span>  

<span data-ttu-id="aec8b-209">関数呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-209">Steps into the function call.</span></span>  

&nbsp;  

---  

### <a name="stepout"></a><span data-ttu-id="aec8b-210">stepOut</span><span class="sxs-lookup"><span data-stu-id="aec8b-210">stepOut</span></span>  

<span data-ttu-id="aec8b-211">関数呼び出しからステップアウトします。</span><span class="sxs-lookup"><span data-stu-id="aec8b-211">Steps out of the function call.</span></span>  

&nbsp;  

---  

### <a name="pause"></a><span data-ttu-id="aec8b-212">pause</span><span class="sxs-lookup"><span data-stu-id="aec8b-212">pause</span></span>  

<span data-ttu-id="aec8b-213">次の JavaScript ステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-213">Stops on the next JavaScript statement.</span></span>  

&nbsp;  

---  

### <a name="resume"></a><span data-ttu-id="aec8b-214">resume</span><span class="sxs-lookup"><span data-stu-id="aec8b-214">resume</span></span>  

<span data-ttu-id="aec8b-215">JavaScript の実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-215">Resumes JavaScript execution.</span></span>  

&nbsp;  

---  

### <a name="getscriptsource"></a><span data-ttu-id="aec8b-216">getScriptSource</span><span class="sxs-lookup"><span data-stu-id="aec8b-216">getScriptSource</span></span>  

<span data-ttu-id="aec8b-217">指定された ID を持つスクリプトのソースを返します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-217">Returns source for the script with given id.</span></span>  

| <span data-ttu-id="aec8b-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-218">Parameters</span></span> | <span data-ttu-id="aec8b-219">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-219">Type</span></span> | <span data-ttu-id="aec8b-220">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-220">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-221">scriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-221">scriptId</span></span> | [<span data-ttu-id="aec8b-222">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-222">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="aec8b-223">ソースを取得するスクリプトの ID。</span><span class="sxs-lookup"><span data-stu-id="aec8b-223">ID of the script to get source for.</span></span> |  

| <span data-ttu-id="aec8b-224">戻り値</span><span class="sxs-lookup"><span data-stu-id="aec8b-224">Returns</span></span> | <span data-ttu-id="aec8b-225">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-225">Type</span></span> | <span data-ttu-id="aec8b-226">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-226">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-227">scriptSource</span><span class="sxs-lookup"><span data-stu-id="aec8b-227">scriptSource</span></span> | `string` | <span data-ttu-id="aec8b-228">スクリプト ソース。</span><span class="sxs-lookup"><span data-stu-id="aec8b-228">Script source.</span></span> | 

---  

### <a name="setpauseonexceptions"></a><span data-ttu-id="aec8b-229">setPauseOnExceptions</span><span class="sxs-lookup"><span data-stu-id="aec8b-229">setPauseOnExceptions</span></span>  

<span data-ttu-id="aec8b-230">例外状態の一時停止を定義します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-230">Defines pause on exceptions state.</span></span>  <span data-ttu-id="aec8b-231">すべての例外、キャッチされていない例外、または例外なしで停止する設定が可能です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-231">Can be set to stop on all exceptions, uncaught exceptions or no exceptions.</span></span>  <span data-ttu-id="aec8b-232">例外状態の最初の一時停止はです `none` 。</span><span class="sxs-lookup"><span data-stu-id="aec8b-232">Initial pause on exceptions state is `none`.</span></span>  

| <span data-ttu-id="aec8b-233">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-233">Parameters</span></span> | <span data-ttu-id="aec8b-234">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-234">Type</span></span> | <span data-ttu-id="aec8b-235">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-235">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-236">状態</span><span class="sxs-lookup"><span data-stu-id="aec8b-236">state</span></span> | `string` | <span data-ttu-id="aec8b-237">例外モードで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-237">Pause on exceptions mode.</span></span>  <span data-ttu-id="aec8b-238">使用できる値:  `none` `uncaught` 、 、</span><span class="sxs-lookup"><span data-stu-id="aec8b-238">Allowed values:  `none`, `uncaught`,</span></span> `all` |  

---  

### <a name="evaluateoncallframe"></a><span data-ttu-id="aec8b-239">evaluateOnCallFrame</span><span class="sxs-lookup"><span data-stu-id="aec8b-239">evaluateOnCallFrame</span></span>  

<span data-ttu-id="aec8b-240">指定された呼び出しフレームの式を評価します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-240">Evaluates expression on a given call frame.</span></span>  

| <span data-ttu-id="aec8b-241">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-241">Parameters</span></span> | <span data-ttu-id="aec8b-242">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-242">Type</span></span> | <span data-ttu-id="aec8b-243">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-243">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-244">callFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-244">callFrameId</span></span> | [<span data-ttu-id="aec8b-245">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-245">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="aec8b-246">フレーム識別子を呼び出して評価します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-246">Call frame identifier to evaluate on.</span></span> |  
| <span data-ttu-id="aec8b-247">式</span><span class="sxs-lookup"><span data-stu-id="aec8b-247">expression</span></span> | `string` | <span data-ttu-id="aec8b-248">評価する式。</span><span class="sxs-lookup"><span data-stu-id="aec8b-248">Expression to evaluate.</span></span> | 

| <span data-ttu-id="aec8b-249">戻り値</span><span class="sxs-lookup"><span data-stu-id="aec8b-249">Returns</span></span> | <span data-ttu-id="aec8b-250">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-250">Type</span></span> | <span data-ttu-id="aec8b-251">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-251">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-252">result</span><span class="sxs-lookup"><span data-stu-id="aec8b-252">result</span></span> | [<span data-ttu-id="aec8b-253">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="aec8b-253">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="aec8b-254">評価結果のオブジェクト ラッパー。</span><span class="sxs-lookup"><span data-stu-id="aec8b-254">Object wrapper for the evaluation result.</span></span> |  

---  

### <a name="setvariablevalue"></a><span data-ttu-id="aec8b-255">setVariableValue</span><span class="sxs-lookup"><span data-stu-id="aec8b-255">setVariableValue</span></span>  

<span data-ttu-id="aec8b-256">呼び出しフレーム内の変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-256">Changes value of variable in a callframe.</span></span>  <span data-ttu-id="aec8b-257">オブジェクト ベースのスコープはサポートされていないので、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec8b-257">Object-based scopes are not supported and must be mutated manually.</span></span>  

| <span data-ttu-id="aec8b-258">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-258">Parameters</span></span> | <span data-ttu-id="aec8b-259">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-259">Type</span></span> | <span data-ttu-id="aec8b-260">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-260">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-261">scopeNumber</span><span class="sxs-lookup"><span data-stu-id="aec8b-261">scopeNumber</span></span> | `integer` | <span data-ttu-id="aec8b-262">スコープ チェーンに記載されている範囲の 0 からベースの数。</span><span class="sxs-lookup"><span data-stu-id="aec8b-262">0-based number of scope as was listed in scope chain.</span></span>  <span data-ttu-id="aec8b-263">のみ `local` 、 `closure` および `catch` スコープの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-263">Only `local`, `closure`, and `catch` scope types are allowed.</span></span>  <span data-ttu-id="aec8b-264">他のスコープは手動で操作できます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-264">Other scopes could be manipulated manually.</span></span> | 
| <span data-ttu-id="aec8b-265">variableName</span><span class="sxs-lookup"><span data-stu-id="aec8b-265">variableName</span></span> | `string` | <span data-ttu-id="aec8b-266">変数名。</span><span class="sxs-lookup"><span data-stu-id="aec8b-266">Variable name.</span></span> | 
| <span data-ttu-id="aec8b-267">newValue</span><span class="sxs-lookup"><span data-stu-id="aec8b-267">newValue</span></span> | [<span data-ttu-id="aec8b-268">Runtime.CallArgument</span><span class="sxs-lookup"><span data-stu-id="aec8b-268">Runtime.CallArgument</span></span>](./runtime.md#callargument) | <span data-ttu-id="aec8b-269">新しい変数値。</span><span class="sxs-lookup"><span data-stu-id="aec8b-269">New variable value.</span></span> |  
| <span data-ttu-id="aec8b-270">callFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-270">callFrameId</span></span> | [<span data-ttu-id="aec8b-271">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-271">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="aec8b-272">変数を保持する呼び出しフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="aec8b-272">ID of callframe that holds variable.</span></span> |  

---  

### <a name="setblackboxpatterns"></a><span data-ttu-id="aec8b-273">setBlackboxPatterns</span><span class="sxs-lookup"><span data-stu-id="aec8b-273">setBlackboxPatterns</span></span>  

<span data-ttu-id="aec8b-274">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-274">**Experimental**.</span></span>  <span data-ttu-id="aec8b-275">以前のブラックボックス パターンを渡されたパターンに置き換える。</span><span class="sxs-lookup"><span data-stu-id="aec8b-275">Replace previous blackbox patterns with passed ones.</span></span>  <span data-ttu-id="aec8b-276">バックエンドは、パターンの 1 つに一致する URL を持つスクリプトのステップ/一時停止を強制的にスキップします。</span><span class="sxs-lookup"><span data-stu-id="aec8b-276">Forces backend to skip stepping/pausing in scripts with url matching one of the patterns.</span></span>  <span data-ttu-id="aec8b-277">デバッガーは、'step in' を何度も実行してブラックボックス化されたスクリプトを残し、失敗した場合は最後に "ステップアウト" に進みます。</span><span class="sxs-lookup"><span data-stu-id="aec8b-277">The debugger will try to leave blackboxed script by performing 'step in' several times, finally resorting to 'step out' if unsuccessful.</span></span>  


| <span data-ttu-id="aec8b-278">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-278">Parameters</span></span> | <span data-ttu-id="aec8b-279">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-279">Type</span></span> | <span data-ttu-id="aec8b-280">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-280">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-281">パターン</span><span class="sxs-lookup"><span data-stu-id="aec8b-281">patterns</span></span> | `string[]` | <span data-ttu-id="aec8b-282">スクリプトの URL でブラックボックスの状態を確認するために使用される正規表現の配列。</span><span class="sxs-lookup"><span data-stu-id="aec8b-282">Array of regexps that will be used to check script url for blackbox state.</span></span> | 

---  

### <a name="mssetdebuggerpropertyvalue"></a><span data-ttu-id="aec8b-283">msSetDebuggerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="aec8b-283">msSetDebuggerPropertyValue</span></span>  

<span data-ttu-id="aec8b-284">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-284">**Experimental**.</span></span>  <span data-ttu-id="aec8b-285">Microsoft: 指定したデバッガー プロパティを指定した値に設定します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-285">Microsoft: Sets the specified debugger property to the specified value.</span></span>  

| <span data-ttu-id="aec8b-286">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-286">Parameters</span></span> | <span data-ttu-id="aec8b-287">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-287">Type</span></span> | <span data-ttu-id="aec8b-288">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-288">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-289">debuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="aec8b-289">debuggerPropertyId</span></span> | <span data-ttu-id="aec8b-290">文字列</span><span class="sxs-lookup"><span data-stu-id="aec8b-290">string</span></span> | <span data-ttu-id="aec8b-291">Microsoft: 設定するプロパティ ID \(すなわち `msDebuggerPropertyId` \) です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-291">Microsoft:  The property id \(i.e. `msDebuggerPropertyId`\) to set.</span></span> | 
| <span data-ttu-id="aec8b-292">newValue</span><span class="sxs-lookup"><span data-stu-id="aec8b-292">newValue</span></span> | `string` | &nbsp; |  

---  

## <a name="events"></a><span data-ttu-id="aec8b-293">イベント</span><span class="sxs-lookup"><span data-stu-id="aec8b-293">Events</span></span>  

### <a name="scriptparsed"></a><span data-ttu-id="aec8b-294">scriptParsed</span><span class="sxs-lookup"><span data-stu-id="aec8b-294">scriptParsed</span></span>  

<span data-ttu-id="aec8b-295">スクリプトの解析時に発生します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-295">Fired when the script is parsed.</span></span> <span data-ttu-id="aec8b-296">このイベントは、デバッガーを有効にした時点で、既知のスクリプトおよび未記録のスクリプトに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-296">This event is also fired for all known and uncollected scripts upon enabling debugger.</span></span>  

| <span data-ttu-id="aec8b-297">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-297">Parameters</span></span> | <span data-ttu-id="aec8b-298">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-298">Type</span></span> | <span data-ttu-id="aec8b-299">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-299">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-300">scriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-300">scriptId</span></span> | [<span data-ttu-id="aec8b-301">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-301">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="aec8b-302">解析されたスクリプトの識別子。</span><span class="sxs-lookup"><span data-stu-id="aec8b-302">Identifier of the script parsed.</span></span> |  
| <span data-ttu-id="aec8b-303">url</span><span class="sxs-lookup"><span data-stu-id="aec8b-303">url</span></span> | `string` | <span data-ttu-id="aec8b-304">解析されたスクリプトの URL または名前 \(if any\)。</span><span class="sxs-lookup"><span data-stu-id="aec8b-304">URL or name of the script parsed \(if any\).</span></span> | 
| <span data-ttu-id="aec8b-305">startLine</span><span class="sxs-lookup"><span data-stu-id="aec8b-305">startLine</span></span> | `integer` | <span data-ttu-id="aec8b-306">リソース内のスクリプトの行オフセットで、指定された URL \(スクリプト タグ\の場合)。</span><span class="sxs-lookup"><span data-stu-id="aec8b-306">Line offset of the script within the resource with given URL \(for script tags\).</span></span> | 
| <span data-ttu-id="aec8b-307">startColumn</span><span class="sxs-lookup"><span data-stu-id="aec8b-307">startColumn</span></span> | `integer` | <span data-ttu-id="aec8b-308">指定された URL を持つリソース内のスクリプトの列オフセット。</span><span class="sxs-lookup"><span data-stu-id="aec8b-308">Column offset of the script within the resource with given URL.</span></span> | 
| <span data-ttu-id="aec8b-309">endLine</span><span class="sxs-lookup"><span data-stu-id="aec8b-309">endLine</span></span> | `integer` | <span data-ttu-id="aec8b-310">スクリプトの最後の行。</span><span class="sxs-lookup"><span data-stu-id="aec8b-310">Last line of the script.</span></span> | 
| <span data-ttu-id="aec8b-311">endColumn</span><span class="sxs-lookup"><span data-stu-id="aec8b-311">endColumn</span></span> | `integer` | <span data-ttu-id="aec8b-312">スクリプトの最後の行の長さ。</span><span class="sxs-lookup"><span data-stu-id="aec8b-312">Length of the last line of the script.</span></span> | 
| <span data-ttu-id="aec8b-313">executionContextId</span><span class="sxs-lookup"><span data-stu-id="aec8b-313">executionContextId</span></span> | [<span data-ttu-id="aec8b-314">Runtime.ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="aec8b-314">Runtime.ExecutionContextId</span></span>](./runtime.md#executioncontextid) | <span data-ttu-id="aec8b-315">スクリプト作成コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-315">Specifies script creation context.</span></span> |  
| <span data-ttu-id="aec8b-316">sourceMapURL \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-316">sourceMapURL \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-317">スクリプトに関連付けられたソース マップの URL (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="aec8b-317">URL of source map associated with script (if any).</span></span> |  
| <span data-ttu-id="aec8b-318">length \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-318">length \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-319">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-319">**Experimental**.</span></span>  <span data-ttu-id="aec8b-320">このスクリプトの長さ。</span><span class="sxs-lookup"><span data-stu-id="aec8b-320">This script length.</span></span> |  
| <span data-ttu-id="aec8b-321">msParentId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-321">msParentId \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-322">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-322">**Experimental**.</span></span>  <span data-ttu-id="aec8b-323">これは親ドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-323">This is the parent document ID.</span></span> |  
| <span data-ttu-id="aec8b-324">msMimeType \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-324">msMimeType \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-325">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-325">**Experimental**.</span></span>  <span data-ttu-id="aec8b-326">これは MIME の種類です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-326">This is the mime type.</span></span> |  
| <span data-ttu-id="aec8b-327">msIsDynamicCode \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-327">msIsDynamicCode \(optional\)</span></span> | `boolean` | <span data-ttu-id="aec8b-328">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-328">**Experimental**.</span></span>  <span data-ttu-id="aec8b-329">これは、動的コードであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-329">This indicates whether it is dynamic code.</span></span> |  
| <span data-ttu-id="aec8b-330">msLongDocumentId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-330">msLongDocumentId \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-331">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-331">**Experimental**.</span></span>  <span data-ttu-id="aec8b-332">これは長いドキュメント ID です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-332">This is the long document ID.</span></span> |  

---  

### <a name="breakpointresolved"></a><span data-ttu-id="aec8b-333">ブレークポイントResolved</span><span class="sxs-lookup"><span data-stu-id="aec8b-333">breakpointResolved</span></span>  

<span data-ttu-id="aec8b-334">ブレークポイントが実際のスクリプトと場所に解決された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-334">Fired when breakpoint is resolved to an actual script and location.</span></span>  

| <span data-ttu-id="aec8b-335">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-335">Parameters</span></span> | <span data-ttu-id="aec8b-336">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-336">Type</span></span> | <span data-ttu-id="aec8b-337">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-337">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-338">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-338">breakpointId</span></span> | [<span data-ttu-id="aec8b-339">ブレークポイントId</span><span class="sxs-lookup"><span data-stu-id="aec8b-339">BreakpointId</span></span>](#breakpointid) | <span data-ttu-id="aec8b-340">ブレークポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="aec8b-340">Breakpoint unique identifier.</span></span> |  
| <span data-ttu-id="aec8b-341">場所</span><span class="sxs-lookup"><span data-stu-id="aec8b-341">location</span></span> | [<span data-ttu-id="aec8b-342">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-342">Location</span></span>](#location) | <span data-ttu-id="aec8b-343">実際のブレークポイントの場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-343">Actual breakpoint location.</span></span> |  
| <span data-ttu-id="aec8b-344">msLength \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-344">msLength \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-345">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-345">**Experimental**.</span></span>  <span data-ttu-id="aec8b-346">Microsoft: ブレークポイントの場所にあるコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-346">Microsoft:  Length of code \(i.e. number of characters\) at the breakpoint location.</span></span> |  

---  

### <a name="paused"></a><span data-ttu-id="aec8b-347">paused (一時停止)</span><span class="sxs-lookup"><span data-stu-id="aec8b-347">paused</span></span>  

<span data-ttu-id="aec8b-348">ブレークポイントまたは例外のデバッガーが壊れた場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-348">Fired when the debuggers breaks for a breakpoint or exception.</span></span>  

| <span data-ttu-id="aec8b-349">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec8b-349">Parameters</span></span> | <span data-ttu-id="aec8b-350">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-350">Type</span></span> | <span data-ttu-id="aec8b-351">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-351">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-352">callFrames</span><span class="sxs-lookup"><span data-stu-id="aec8b-352">callFrames</span></span> | [<span data-ttu-id="aec8b-353">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="aec8b-353">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="aec8b-354">デバッガーが停止したスタックを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-354">Call stack the debugger stopped on.</span></span> |  
| <span data-ttu-id="aec8b-355">理由</span><span class="sxs-lookup"><span data-stu-id="aec8b-355">reason</span></span> | `string` |  <span data-ttu-id="aec8b-356">理由を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-356">Pause reason.</span></span>  <span data-ttu-id="aec8b-357">使用できる値:  `breakpoint` `step` `exception` `other` 、、、、、、</span><span class="sxs-lookup"><span data-stu-id="aec8b-357">Allowed values:  `breakpoint`, `step`, `exception`, `other`, and</span></span> `EventListener` |  
| <span data-ttu-id="aec8b-358">data \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-358">data \(optional\)</span></span> | `object` | <span data-ttu-id="aec8b-359">ブレーク固有の補助プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aec8b-359">Object containing break-specific auxiliary properties.</span></span> |  
| <span data-ttu-id="aec8b-360">hitBreakpoints \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-360">hitBreakpoints \(optional\)</span></span> | `string[]` | <span data-ttu-id="aec8b-361">ブレークポイントのヒットの ID</span><span class="sxs-lookup"><span data-stu-id="aec8b-361">Hit breakpoints IDs</span></span> |  
| <span data-ttu-id="aec8b-362">asyncStackTrace \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-362">asyncStackTrace \(optional\)</span></span> | `StackTrace` | <span data-ttu-id="aec8b-363">JavaScript async スタック トレース。</span><span class="sxs-lookup"><span data-stu-id="aec8b-363">JavaScript async stack trace.</span></span> |  

---  

### <a name="resumed"></a><span data-ttu-id="aec8b-364">再開</span><span class="sxs-lookup"><span data-stu-id="aec8b-364">resumed</span></span>  

<span data-ttu-id="aec8b-365">デバッガーが実行を再開すると発生します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-365">Fired when the debugger resumes execution.</span></span>  

&nbsp;  

---  

## <a name="types"></a><span data-ttu-id="aec8b-366">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-366">Types</span></span>  

### <a name="breakpointid-string"></a><span data-ttu-id="aec8b-367">ブレークポイントId 文字列</span><span class="sxs-lookup"><span data-stu-id="aec8b-367">BreakpointId string</span></span>  

<a name="breakpointid"></a>  

<span data-ttu-id="aec8b-368">ブレークポイント識別子。</span><span class="sxs-lookup"><span data-stu-id="aec8b-368">Breakpoint identifier.</span></span>  

&nbsp;  

---  

### <a name="callframeid-string"></a><span data-ttu-id="aec8b-369">CallFrameId 文字列</span><span class="sxs-lookup"><span data-stu-id="aec8b-369">CallFrameId string</span></span>  

<a name="callframeid"></a>  

<span data-ttu-id="aec8b-370">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="aec8b-370">Call frame identifier.</span></span>  

&nbsp;  

---  

### <a name="location-object"></a><span data-ttu-id="aec8b-371">Location オブジェクト</span><span class="sxs-lookup"><span data-stu-id="aec8b-371">Location object</span></span>  

<a name="location"></a>  

<span data-ttu-id="aec8b-372">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-372">Location in the source code.</span></span>  

| <span data-ttu-id="aec8b-373">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aec8b-373">Properties</span></span> | <span data-ttu-id="aec8b-374">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-374">Type</span></span> | <span data-ttu-id="aec8b-375">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-375">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-376">scriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-376">scriptId</span></span> | [<span data-ttu-id="aec8b-377">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-377">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="aec8b-378">で報告されるスクリプト識別子 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="aec8b-378">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="aec8b-379">lineNumber</span><span class="sxs-lookup"><span data-stu-id="aec8b-379">lineNumber</span></span> | `integer` | <span data-ttu-id="aec8b-380">スクリプト \(0-based\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="aec8b-380">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="aec8b-381">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-381">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-382">スクリプト \(0-based\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="aec8b-382">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="aec8b-383">msLength</span><span class="sxs-lookup"><span data-stu-id="aec8b-383">msLength</span></span> | `integer` | <span data-ttu-id="aec8b-384">Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-384">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  

---  

### <a name="breaklocation-object"></a><span data-ttu-id="aec8b-385">BreakLocation オブジェクト</span><span class="sxs-lookup"><span data-stu-id="aec8b-385">BreakLocation object</span></span>  

<a name="breaklocation"></a>  

<span data-ttu-id="aec8b-386">ソース コード内の場所を壊します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-386">Break location in the source code.</span></span>  

| <span data-ttu-id="aec8b-387">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aec8b-387">Properties</span></span> | <span data-ttu-id="aec8b-388">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-388">Type</span></span> | <span data-ttu-id="aec8b-389">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-389">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-390">scriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-390">scriptId</span></span> | [<span data-ttu-id="aec8b-391">Runtime.ScriptId</span><span class="sxs-lookup"><span data-stu-id="aec8b-391">Runtime.ScriptId</span></span>](./runtime.md#scriptid) | <span data-ttu-id="aec8b-392">で報告されるスクリプト識別子 `Debugger.scriptParsed` 。</span><span class="sxs-lookup"><span data-stu-id="aec8b-392">Script identifier as reported in the `Debugger.scriptParsed`.</span></span> |  
| <span data-ttu-id="aec8b-393">lineNumber</span><span class="sxs-lookup"><span data-stu-id="aec8b-393">lineNumber</span></span> | `integer` | <span data-ttu-id="aec8b-394">スクリプト \(0-based\) の行番号。</span><span class="sxs-lookup"><span data-stu-id="aec8b-394">Line number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="aec8b-395">columnNumber \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-395">columnNumber \(optional\)</span></span> | `integer` | <span data-ttu-id="aec8b-396">スクリプト \(0-based\) の列番号。</span><span class="sxs-lookup"><span data-stu-id="aec8b-396">Column number in the script \(0-based\).</span></span> |  
| <span data-ttu-id="aec8b-397">msLength</span><span class="sxs-lookup"><span data-stu-id="aec8b-397">msLength</span></span> | `integer` | <span data-ttu-id="aec8b-398">Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-398">Microsoft:  Length of code \(i.e. number of characters\) at this call frame.</span></span> |  
| <span data-ttu-id="aec8b-399">型 \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-399">type \(optional\)</span></span> | `string` | <span data-ttu-id="aec8b-400">使用できる値: debuggerStatement、呼び出し、返します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-400">Allowed values: debuggerStatement, call, return.</span></span> |  

---  

### <a name="callframe-object"></a><span data-ttu-id="aec8b-401">CallFrame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="aec8b-401">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="aec8b-402">JavaScript 呼び出しフレーム。</span><span class="sxs-lookup"><span data-stu-id="aec8b-402">JavaScript call frame.</span></span> <span data-ttu-id="aec8b-403">呼び出しフレームの配列は、呼び出し履歴を形成します。</span><span class="sxs-lookup"><span data-stu-id="aec8b-403">Array of call frames form the call stack.</span></span>  

| <span data-ttu-id="aec8b-404">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aec8b-404">Properties</span></span> | <span data-ttu-id="aec8b-405">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-405">Type</span></span> | <span data-ttu-id="aec8b-406">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-406">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-407">callFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-407">callFrameId</span></span> | [<span data-ttu-id="aec8b-408">CallFrameId</span><span class="sxs-lookup"><span data-stu-id="aec8b-408">CallFrameId</span></span>](#callframeid) | <span data-ttu-id="aec8b-409">呼び出しフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="aec8b-409">Call frame identifier.</span></span>  <span data-ttu-id="aec8b-410">この識別子は、デバッガーが一時停止している間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="aec8b-410">This identifier is only valid while the debugger is paused.</span></span> |  
| <span data-ttu-id="aec8b-411">functionName</span><span class="sxs-lookup"><span data-stu-id="aec8b-411">functionName</span></span> | `string` | <span data-ttu-id="aec8b-412">この呼び出しフレームで呼び出される JavaScript 関数の名前。</span><span class="sxs-lookup"><span data-stu-id="aec8b-412">Name of the JavaScript function called on this call frame.</span></span> |  
| <span data-ttu-id="aec8b-413">functionLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-413">functionLocation \(optional\)</span></span> | [<span data-ttu-id="aec8b-414">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-414">Location</span></span>](#location) | <span data-ttu-id="aec8b-415">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="aec8b-415">**Experimental**.</span></span>  <span data-ttu-id="aec8b-416">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-416">Location in the source code.</span></span> |  
| <span data-ttu-id="aec8b-417">場所</span><span class="sxs-lookup"><span data-stu-id="aec8b-417">location</span></span> | [<span data-ttu-id="aec8b-418">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-418">Location</span></span>](#location) | <span data-ttu-id="aec8b-419">ソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-419">Location in the source code.</span></span> |  
| <span data-ttu-id="aec8b-420">url</span><span class="sxs-lookup"><span data-stu-id="aec8b-420">url</span></span> | `string` | <span data-ttu-id="aec8b-421">JavaScript スクリプト名または URL。</span><span class="sxs-lookup"><span data-stu-id="aec8b-421">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="aec8b-422">scopeChain</span><span class="sxs-lookup"><span data-stu-id="aec8b-422">scopeChain</span></span> | [<span data-ttu-id="aec8b-423">Scope[]</span><span class="sxs-lookup"><span data-stu-id="aec8b-423">Scope[]</span></span>](#scope) | <span data-ttu-id="aec8b-424">この呼び出しフレームのスコープ チェーン。</span><span class="sxs-lookup"><span data-stu-id="aec8b-424">Scope chain for this call frame.</span></span> |  
| <span data-ttu-id="aec8b-425">これ</span><span class="sxs-lookup"><span data-stu-id="aec8b-425">this</span></span> | [<span data-ttu-id="aec8b-426">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="aec8b-426">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | `this` <span data-ttu-id="aec8b-427">この呼び出しフレームのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aec8b-427">object for this call frame.</span></span> |  
| <span data-ttu-id="aec8b-428">returnValue \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-428">returnValue \(optional\)</span></span> | [<span data-ttu-id="aec8b-429">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="aec8b-429">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="aec8b-430">関数が戻り値である場合に返される値。</span><span class="sxs-lookup"><span data-stu-id="aec8b-430">The value being returned, if the function is at return point.</span></span> |  

---  

### <a name="scope-object"></a><span data-ttu-id="aec8b-431">Scope オブジェクト</span><span class="sxs-lookup"><span data-stu-id="aec8b-431">Scope object</span></span>  

<a name="scope"></a>  

<span data-ttu-id="aec8b-432">スコープの説明。</span><span class="sxs-lookup"><span data-stu-id="aec8b-432">Scope description.</span></span>  

| <span data-ttu-id="aec8b-433">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aec8b-433">Properties</span></span> | <span data-ttu-id="aec8b-434">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-434">Type</span></span> | <span data-ttu-id="aec8b-435">詳細</span><span class="sxs-lookup"><span data-stu-id="aec8b-435">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aec8b-436">型</span><span class="sxs-lookup"><span data-stu-id="aec8b-436">type</span></span> | `string` | <span data-ttu-id="aec8b-437">スコープの種類。</span><span class="sxs-lookup"><span data-stu-id="aec8b-437">Scope type.</span></span>  <span data-ttu-id="aec8b-438">使用できる値: `global` `local` `with` 、、、、、、、、、、 `closure` `catch` `block` `script` `eval` `module`</span><span class="sxs-lookup"><span data-stu-id="aec8b-438">Allowed values:  `global`, `local`, `with`, `closure`, `catch`, `block`, `script`, `eval`, `module`, and</span></span> `return` |  
| <span data-ttu-id="aec8b-439">object</span><span class="sxs-lookup"><span data-stu-id="aec8b-439">object</span></span> | [<span data-ttu-id="aec8b-440">Runtime.RemoteObject</span><span class="sxs-lookup"><span data-stu-id="aec8b-440">Runtime.RemoteObject</span></span>](./runtime.md#remoteobject) | <span data-ttu-id="aec8b-441">スコープを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aec8b-441">Object representing the scope.</span></span>  <span data-ttu-id="aec8b-442">For and scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as `global` `with` its properties.</span><span class="sxs-lookup"><span data-stu-id="aec8b-442">For `global` and `with` scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</span></span> |  
| <span data-ttu-id="aec8b-443">name \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-443">name \(optional\)</span></span> | `string` | &nbsp; |  
| <span data-ttu-id="aec8b-444">startLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-444">startLocation \(optional\)</span></span> | [<span data-ttu-id="aec8b-445">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-445">Location</span></span>](#location) | <span data-ttu-id="aec8b-446">スコープが開始するソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-446">Location in the source code where scope starts.</span></span> |  
| <span data-ttu-id="aec8b-447">endLocation \(optional\)</span><span class="sxs-lookup"><span data-stu-id="aec8b-447">endLocation \(optional\)</span></span> | [<span data-ttu-id="aec8b-448">Location</span><span class="sxs-lookup"><span data-stu-id="aec8b-448">Location</span></span>](#location) | <span data-ttu-id="aec8b-449">スコープが終了するソース コード内の場所。</span><span class="sxs-lookup"><span data-stu-id="aec8b-449">Location in the source code where scope ends.</span></span> |  

---  

## <a name="dependencies"></a><span data-ttu-id="aec8b-450">依存関係</span><span class="sxs-lookup"><span data-stu-id="aec8b-450">Dependencies</span></span>  

[<span data-ttu-id="aec8b-451">ランタイム</span><span class="sxs-lookup"><span data-stu-id="aec8b-451">Runtime</span></span>](./runtime.md)  
