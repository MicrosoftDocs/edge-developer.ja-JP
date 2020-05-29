---
title: Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2afa4b7dbe96b65747ec17b147f0a82c16efa288
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581804"
---
<!-- Copyright Kayce Basques 
   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at
       https://www.apache.org/licenses/LICENSE-2.0
   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  







# <span data-ttu-id="f6b3f-103">Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法</span><span class="sxs-lookup"><span data-stu-id="f6b3f-103">How To Pause Your Code With Breakpoints In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="f6b3f-104">ブレークポイントを使用して JavaScript コードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-104">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="f6b3f-105">このガイドでは、DevTools で利用できる各種類のブレークポイントと、それぞれの種類の設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-105">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="f6b3f-106">デバッグプロセスの実践的なチュートリアルについては、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevtoolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-106">For a hands-on tutorial of the debugging process, see [Get Started with Debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <span data-ttu-id="f6b3f-107">各ブレークポイントの種類を使用する状況の概要</span><span class="sxs-lookup"><span data-stu-id="f6b3f-107">Overview of when to use each breakpoint type</span></span>   

<span data-ttu-id="f6b3f-108">最もよく知られているブレークポイントの種類は、コード行です。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-108">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="f6b3f-109">ただし、行コードのブレークポイントを設定するのは効率的ではありません。特に、正確な場所がわからない場合や、大規模なコードベースを使用している場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-109">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="f6b3f-110">他の種類のブレークポイントを使用する方法とタイミングを理解することで、デバッグ時に時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-110">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="f6b3f-111">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="f6b3f-111">Breakpoint Type</span></span> | <span data-ttu-id="f6b3f-112">一時停止するときに使用する...</span><span class="sxs-lookup"><span data-stu-id="f6b3f-112">Use This When You Want To Pause...</span></span>  |  
|:--- |:--- |  
| [<span data-ttu-id="f6b3f-113">行コード</span><span class="sxs-lookup"><span data-stu-id="f6b3f-113">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="f6b3f-114">コードの正確な領域。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-114">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="f6b3f-115">条件行コード</span><span class="sxs-lookup"><span data-stu-id="f6b3f-115">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="f6b3f-116">コードの正確な領域で、他の条件が true の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-116">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="f6b3f-117">DOM</span><span class="sxs-lookup"><span data-stu-id="f6b3f-117">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="f6b3f-118">特定の DOM ノードまたは子を変更または削除するコード。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-118">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="f6b3f-119">XHR</span><span class="sxs-lookup"><span data-stu-id="f6b3f-119">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="f6b3f-120">XHR URL に文字列パターンが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-120">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="f6b3f-121">イベントリスナー</span><span class="sxs-lookup"><span data-stu-id="f6b3f-121">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="f6b3f-122">イベント (、など) の後で実行されるコードの `click` 場合。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-122">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="f6b3f-123">エラー</span><span class="sxs-lookup"><span data-stu-id="f6b3f-123">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="f6b3f-124">キャッチされた、またはキャッチされない例外をスローするコード行。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-124">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="f6b3f-125">機能</span><span class="sxs-lookup"><span data-stu-id="f6b3f-125">Function</span></span>](#function-breakpoints) | <span data-ttu-id="f6b3f-126">特定のコマンド、関数、またはメソッドを実行するたび。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-126">Whenever a specific command, function, or method is run.</span></span>  |  

## <span data-ttu-id="f6b3f-127">行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-127">Line-of-code breakpoints</span></span>   

<span data-ttu-id="f6b3f-128">調査が必要なコードの正確な領域がわかっている場合は、コード行のブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-128">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="f6b3f-129">このコード行が実行される前に、DevTools は**常に**一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-129">DevTools **always** pauses before this line of code is run.</span></span>  

<span data-ttu-id="f6b3f-130">DevTools で行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-130">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="f6b3f-131">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-131">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-132">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-132">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="f6b3f-133">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-133">Go the line of code.</span></span>  
1.  <span data-ttu-id="f6b3f-134">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-134">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="f6b3f-135">それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-135">Click on it.</span></span>  <span data-ttu-id="f6b3f-136">[行番号] 列の横に赤いアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-136">A red icon appears next to the line number column.</span></span>  

> ##### <span data-ttu-id="f6b3f-137">図 1</span><span class="sxs-lookup"><span data-stu-id="f6b3f-137">Figure 1</span></span>  
> <span data-ttu-id="f6b3f-138">行30に設定されるコード行のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-138">A line-of-code breakpoint set on line 30</span></span>  
> ![行コードのブレークポイント][ImageLocBreakpoint]  

### <span data-ttu-id="f6b3f-140">コードの行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-140">Line-of-code breakpoints in your code</span></span>   

<span data-ttu-id="f6b3f-141">コードからメソッドを実行して、 `debugger` その行にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="f6b3f-142">これは、コード内にブレーク[ポイント](#line-of-code-breakpoints)が設定されている点を除いて、コード内にブレークポイントが設定されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <span data-ttu-id="f6b3f-143">条件行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-143">Conditional line-of-code breakpoints</span></span>   

<span data-ttu-id="f6b3f-144">調査が必要なコードの正確な領域がわかっているが、その他の条件が true の場合にのみ一時停止する必要がある場合は、条件付きコードのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="f6b3f-145">条件行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="f6b3f-146">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-146">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-147">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="f6b3f-148">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="f6b3f-149">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="f6b3f-150">行番号を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-150">Right-click the line number.</span></span>  
1.  <span data-ttu-id="f6b3f-151">[**条件付きブレークポイントの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-151">Select **Add conditional breakpoint**.</span></span>  <span data-ttu-id="f6b3f-152">ダイアログがコード行の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="f6b3f-153">ダイアログに条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="f6b3f-154">を押して `Enter` 、ブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-154">Press `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="f6b3f-155">[行番号] 列の横にあるアイコン。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-155">An icon next to the line number column.</span></span>  

> ##### <span data-ttu-id="f6b3f-156">図 2</span><span class="sxs-lookup"><span data-stu-id="f6b3f-156">Figure 2</span></span>  
> <span data-ttu-id="f6b3f-157">行34に設定される条件付き行のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-157">A conditional line-of-code breakpoint set on line 34</span></span>  
> ![条件行コードのブレークポイント][ImageConditionalLocBreakpoint]  

### <span data-ttu-id="f6b3f-159">行コードのブレークポイントを管理する</span><span class="sxs-lookup"><span data-stu-id="f6b3f-159">Manage line-of-code breakpoints</span></span>   

<span data-ttu-id="f6b3f-160">[**ブレークポイント**] ウィンドウを使用して、1つの場所から行コードのブレークポイントを無効化または削除します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-160">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

> ##### <span data-ttu-id="f6b3f-161">図 3</span><span class="sxs-lookup"><span data-stu-id="f6b3f-161">Figure 3</span></span>  
> <span data-ttu-id="f6b3f-162">2つのコードのブレークポイントが表示された [**ブレークポイント**] パネル。1行に1つの `16` 行にある `get-started.js`</span><span class="sxs-lookup"><span data-stu-id="f6b3f-162">The **Breakpoints** panel showing two line-of-code breakpoints: one on line `16` of `get-started.js`, another on line</span></span> `33`  
> ![[ブレークポイント] パネル][ImageBreakpointsPanel]  

*   <span data-ttu-id="f6b3f-164">エントリの横にあるチェックボックスをオンにして、そのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-164">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="f6b3f-165">エントリを右クリックして、そのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-165">Right-click an entry to remove that breakpoint.</span></span>  
*   <span data-ttu-id="f6b3f-166">[**ブレークポイント**] ウィンドウ内の任意の場所を右クリックして、すべてのブレークポイントを非アクティブ化、すべてのブレークポイントの無効化、すべてのブレークポイントの削除を行います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-166">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="f6b3f-167">すべてのブレークポイントを無効にすることは、それぞれのチェックをオフにすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-167">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="f6b3f-168">すべてのブレークポイントを非アクティブ化するには、すべてのコードのブレークポイントを無視するように DevTools を使用しますが、それぞれのブレークポイントを再アクティブ化するときと同じ状態になるように、有効な状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-168">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  

> ##### <span data-ttu-id="f6b3f-169">図 4</span><span class="sxs-lookup"><span data-stu-id="f6b3f-169">Figure 4</span></span>  
> <span data-ttu-id="f6b3f-170">[**ブレークポイント**] ウィンドウの非アクティブになっているブレークポイントが無効になり、透明になる</span><span class="sxs-lookup"><span data-stu-id="f6b3f-170">Deactivated breakpoints in the **Breakpoints** pane are disabled and transparent</span></span>  
> ![[ブレークポイント] ウィンドウのブレークダウンの無効化][ImageDeactivatedBreakpoints]  

## <span data-ttu-id="f6b3f-172">DOM 変更のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-172">DOM change breakpoints</span></span>   

<span data-ttu-id="f6b3f-173">Dom ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-173">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="f6b3f-174">DOM 変更のブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-174">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="f6b3f-175">[**要素**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-175">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-176">ブレークポイントを設定する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-176">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="f6b3f-177">要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-177">Right-click the element.</span></span>  
1.  <span data-ttu-id="f6b3f-178">[**中断] の上に**カーソルを合わせ、[**サブツリーの変更**]、[属性の**変更**]、または [**ノードの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-178">Hover over **Break on**, then select **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  

> ##### <span data-ttu-id="f6b3f-179">図 5</span><span class="sxs-lookup"><span data-stu-id="f6b3f-179">Figure 5</span></span>  
> <span data-ttu-id="f6b3f-180">DOM 変更ブレークポイントを作成するためのコンテキストメニュー</span><span class="sxs-lookup"><span data-stu-id="f6b3f-180">The context menu for creating a DOM change breakpoint</span></span>  
> ![DOM 変更ブレークポイントを作成するためのコンテキストメニュー][ImageDomChangeBreakpoint]  

### <span data-ttu-id="f6b3f-182">DOM の種類の変更ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-182">Types of DOM change breakpoints</span></span>   

*   <span data-ttu-id="f6b3f-183">**サブツリーの変更**。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-183">**Subtree modifications**.</span></span>  <span data-ttu-id="f6b3f-184">現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-184">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="f6b3f-185">子ノードの属性の変更、または現在選択されているノードへの変更に対してトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-185">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  

*   <span data-ttu-id="f6b3f-186">**属性の変更**: 現在選択されているノードの属性が追加または削除されたとき、または属性値が変更されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-186">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  

*   <span data-ttu-id="f6b3f-187">**ノードの削除**: 現在選択されているノードが削除されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-187">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  

## <span data-ttu-id="f6b3f-188">XHR/Fetch のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-188">XHR/Fetch breakpoints</span></span>   

<span data-ttu-id="f6b3f-189">XHR の要求 URL に指定された文字列が含まれている場合に中断する場合は、XHR ブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-189">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="f6b3f-190">DevTools は、XHR がメソッドを実行しているコード行で一時停止し `send()` ます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-190">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="f6b3f-191">この機能は、 [FETCH API][MDNFetchApi]要求でも動作します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-191">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="f6b3f-192">これが役に立つ場合の1つの例として、ページで正しくない URL が要求されていることがわかっていて、誤った要求を引き起こしている AJAX またはフェッチソースコードをすばやく見つける必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-192">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="f6b3f-193">XHR のブレークポイントを設定するには:</span><span class="sxs-lookup"><span data-stu-id="f6b3f-193">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="f6b3f-194">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-194">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-195">[ **Xhr のブレークポイント**] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-195">Expand the **XHR Breakpoints** pane.</span></span>  
1.  <span data-ttu-id="f6b3f-196">[**ブレークポイントの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-196">Click **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="f6b3f-197">改ページする文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-197">Enter the string which you want to break on.</span></span>  <span data-ttu-id="f6b3f-198">DevTools は、この文字列が XHR 要求 URL の任意の場所にある場合に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-198">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="f6b3f-199">を押して `Enter` 確認します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-199">Press `Enter` to confirm.</span></span>  

> ##### <span data-ttu-id="f6b3f-200">図 6</span><span class="sxs-lookup"><span data-stu-id="f6b3f-200">Figure 6</span></span>  
> <span data-ttu-id="f6b3f-201">URL に含まれるすべての要求に対して**Xhr**ブレークポイントで xhr ブレークポイントを作成する `org`</span><span class="sxs-lookup"><span data-stu-id="f6b3f-201">Creating an XHR breakpoint in the **XHR Breakpoints** for any request that contains `org` in the URL</span></span>  
> ![XHR ブレークポイントの作成][ImageXhrBreakpoint]  

## <span data-ttu-id="f6b3f-203">イベントリスナーのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-203">Event listener breakpoints</span></span> 

<span data-ttu-id="f6b3f-204">イベントが発生した後に実行されるイベントリスナーコードで一時停止する場合は、イベントリスナーのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-204">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="f6b3f-205">[ `click` すべてのマウスイベント] などのイベントのカテゴリやカテゴリなどの特定のイベントを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-205">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="f6b3f-206">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-206">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-207">[**イベントリスナーのブレークポイント**] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-207">Expand the **Event Listener Breakpoints** pane.</span></span>  <span data-ttu-id="f6b3f-208">[DevTools] は、**アニメーション**などのイベントカテゴリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-208">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="f6b3f-209">いずれかのカテゴリをチェックして、そのカテゴリのイベントが発生したときに一時停止するか、カテゴリを展開して特定のイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-209">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  

> ##### <span data-ttu-id="f6b3f-210">図 7</span><span class="sxs-lookup"><span data-stu-id="f6b3f-210">Figure 7</span></span>  
> <span data-ttu-id="f6b3f-211">のイベントリスナーのブレークポイントの作成</span><span class="sxs-lookup"><span data-stu-id="f6b3f-211">Creating an event listener breakpoint for</span></span> `deviceorientation`  
> ![イベントリスナーのブレークポイントの作成][ImageEventListenerBreakpoint]  

## <span data-ttu-id="f6b3f-213">例外のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-213">Exception breakpoints</span></span>   

<span data-ttu-id="f6b3f-214">キャッチまたはキャッチされない例外をスローするコード行で一時停止する場合は、例外のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-214">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="f6b3f-215">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-215">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="f6b3f-216">[例外に対して例外を一時停止する]**を**クリックし ![ ][ImagePauseOnExceptionsIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-216">Click **Pause on exceptions** ![Pause on exceptions][ImagePauseOnExceptionsIcon].</span></span>  <span data-ttu-id="f6b3f-217">有効にすると、アイコンが青色に変わります。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-217">The icon turns blue when enabled.</span></span>  
    
    > ##### <span data-ttu-id="f6b3f-218">図 8</span><span class="sxs-lookup"><span data-stu-id="f6b3f-218">Figure 8</span></span>  
    > <span data-ttu-id="f6b3f-219">**[例外時に一時停止**] ボタン</span><span class="sxs-lookup"><span data-stu-id="f6b3f-219">The **Pause on exceptions** button</span></span>  
    > ![[例外時に一時停止] ボタン][ImagePauseExceptionsHighlight]  

1.  <span data-ttu-id="f6b3f-221">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-221">**Optional**.</span></span> <span data-ttu-id="f6b3f-222">キャッチされていない例外にも一時停止したい場合は、 **[キャッチした例外を一時停止**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-222">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  

> ##### <span data-ttu-id="f6b3f-223">図 9</span><span class="sxs-lookup"><span data-stu-id="f6b3f-223">Figure 9</span></span>  
> <span data-ttu-id="f6b3f-224">キャッチされていない例外で一時停止</span><span class="sxs-lookup"><span data-stu-id="f6b3f-224">Paused on an uncaught exception</span></span>  
> ![キャッチされていない例外で一時停止][ImageUncaughtException]  

## <span data-ttu-id="f6b3f-226">関数のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="f6b3f-226">Function breakpoints</span></span>   

<span data-ttu-id="f6b3f-227">特定の `debug(method)` `method` 関数が実行されているときに一時停止する必要がある場合は、デバッグするコマンド、関数、またはメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-227">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="f6b3f-228">`debug()`コード (ステートメントなど) に挿入し `console.log()` たり、Devtools コンソールからメソッドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-228">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="f6b3f-229">関数の最初の行に[行コードのブレークポイント](#line-of-code-breakpoints)を設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-229">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <span data-ttu-id="f6b3f-230">ターゲット関数が範囲内にあることを確認する</span><span class="sxs-lookup"><span data-stu-id="f6b3f-230">Make sure the target function is in scope</span></span>   

<span data-ttu-id="f6b3f-231">DevTools は、 `ReferenceError` デバッグする関数がスコープ外であるかどうかをスローします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-231">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

<span data-ttu-id="f6b3f-232">DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあることを確認するのが複雑になり `debug()` ます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-232">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="f6b3f-233">1つの戦略を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-233">Here is one strategy:</span></span>  

1.  <span data-ttu-id="f6b3f-234">関数がスコープ内のどこかにある[行コードのブレークポイント](#line-of-code-breakpoints)を設定します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-234">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="f6b3f-235">ブレークポイントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-235">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="f6b3f-236">コード `debug()` が行のブレークポイントで一時停止されている状態で、DevTools コンソールでこのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-236">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  

 



<!-- image links -->  

[ImagePauseOnExceptionsIcon]: /microsoft-edge/devtools-guide-chromium/media/pause-on-exceptions-icon.msft.png  

[ImageLocBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-breakpoint-30.msft.png "図 1: コード行のブレークポイント"  
[ImageConditionalLocBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-conditional-breakpoint.msft.png "図 2: 条件行コードのブレークポイント"  
[ImageBreakpointsPanel]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-breakpoints-16-33.msft.png "図 3: [ブレークポイント] パネル"  
[ImageDeactivatedBreakpoints]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png "図 4: [ブレークポイント] ウィンドウのブレークポイントの無効化"  
[ImageDomChangeBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-elements-break-on-subtree-modifications.msft.png "図 5: DOM の変更ブレークポイントを作成するためのコンテキストメニュー"  
[ImageXhrBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png "図 6: XHR ブレークポイントを作成する"  
[ImageEventListenerBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png "図 7: イベントリスナーのブレークポイントの作成"  
[ImagePauseExceptionsHighlight]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-pause-on-exceptions.msft.png "図 8: [例外時に一時停止] ボタン"  
[ImageUncaughtException]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-js-paused-on-exception.msft.png "図 9: キャッチされていない例外で一時停止する"  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  

> [!NOTE]
> <span data-ttu-id="f6b3f-248">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-248">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f6b3f-249">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-249">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f6b3f-251">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f6b3f-251">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
