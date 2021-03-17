---
description: Microsoft Edge DevTools でコードを一時停止できるすべての方法について説明します。
title: Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3d50b7b105aa9a9018ba61e44147f46f3d340079
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439515"
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

# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a><span data-ttu-id="c77b5-104">Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法</span><span class="sxs-lookup"><span data-stu-id="c77b5-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="c77b5-105">ブレークポイントを使用して JavaScript コードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="c77b5-106">このガイドでは、DevTools で使用できるブレークポイントの種類と、使用する時間と各種類の設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="c77b5-107">デバッグ プロセスの実践的なチュートリアルについては [、「Microsoft Edge DevTools][DevtoolsJavascriptIndex]での JavaScript のデバッグの開始」に移動します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-107">For a hands-on tutorial of the debugging process, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <a name="overview-of-when-to-use-each-breakpoint-type"></a><span data-ttu-id="c77b5-108">各ブレークポイントの種類を使用する場合の概要</span><span class="sxs-lookup"><span data-stu-id="c77b5-108">Overview of when to use each breakpoint type</span></span>  

<span data-ttu-id="c77b5-109">最もよく知られているブレークポイントの種類は、コード行です。</span><span class="sxs-lookup"><span data-stu-id="c77b5-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="c77b5-110">ただし、コード行のブレークポイントは、特に場所を正確に知らない場合や、大きなコードベースを使用している場合に設定が非効率的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="c77b5-111">他の種類のブレークポイントを使用する方法と時期を知ることにより、デバッグの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="c77b5-112">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="c77b5-112">Breakpoint Type</span></span> | <span data-ttu-id="c77b5-113">一時停止する場合は、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-113">Use This When You Want To Pause...</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="c77b5-114">コード行</span><span class="sxs-lookup"><span data-stu-id="c77b5-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="c77b5-115">コードの正確な領域。</span><span class="sxs-lookup"><span data-stu-id="c77b5-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="c77b5-116">条件付きコード行</span><span class="sxs-lookup"><span data-stu-id="c77b5-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="c77b5-117">コードの正確な領域で、他の条件が true の場合のみ。</span><span class="sxs-lookup"><span data-stu-id="c77b5-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="c77b5-118">DOM</span><span class="sxs-lookup"><span data-stu-id="c77b5-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="c77b5-119">特定の DOM ノードまたは子ノードを変更または削除するコード。</span><span class="sxs-lookup"><span data-stu-id="c77b5-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="c77b5-120">XHR</span><span class="sxs-lookup"><span data-stu-id="c77b5-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="c77b5-121">XHR URL に文字列パターンが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="c77b5-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="c77b5-122">イベント リスナー</span><span class="sxs-lookup"><span data-stu-id="c77b5-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="c77b5-123">イベントの実行後に実行されるコード (実行など `click` )。</span><span class="sxs-lookup"><span data-stu-id="c77b5-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="c77b5-124">例外</span><span class="sxs-lookup"><span data-stu-id="c77b5-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="c77b5-125">キャッチまたはキャッチされていない例外をスローするコード行で。</span><span class="sxs-lookup"><span data-stu-id="c77b5-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="c77b5-126">機能</span><span class="sxs-lookup"><span data-stu-id="c77b5-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="c77b5-127">特定のコマンド、関数、またはメソッドが実行されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <a name="line-of-code-breakpoints"></a><span data-ttu-id="c77b5-128">コード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-128">Line-of-code breakpoints</span></span>  

<span data-ttu-id="c77b5-129">調査する必要があるコードの正確な領域を知っている場合は、コード行ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="c77b5-130">DevTools は、このコード行を実行する前に常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="c77b5-131">DevTools でコード行ブレークポイントを設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="c77b5-132">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-132">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="c77b5-133">ブレークするコード行を含むファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="c77b5-134">コード行を移動します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="c77b5-135">コード行の左側に行番号列があります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="c77b5-136">選択します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-136">Choose it.</span></span>  <span data-ttu-id="c77b5-137">行番号列の横に赤いアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="コード行ブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="c77b5-139">コード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a><span data-ttu-id="c77b5-140">コード内のコード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-140">Line-of-code breakpoints in your code</span></span>  

<span data-ttu-id="c77b5-141">コードから `debugger` メソッドを実行して、その行を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="c77b5-142">これは、DevTools [](#line-of-code-breakpoints)UI ではなく、コードでブレークポイントが設定されている点を除き、コード行ブレークポイントと同じです。</span><span class="sxs-lookup"><span data-stu-id="c77b5-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a><span data-ttu-id="c77b5-143">条件付きコード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-143">Conditional line-of-code breakpoints</span></span>  

<span data-ttu-id="c77b5-144">調査する必要があるコードの正確な領域がわかっているが、他の条件が true の場合にのみ一時停止する場合は、条件付きコード行ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="c77b5-145">条件付きコード行ブレークポイントを設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="c77b5-146">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-146">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="c77b5-147">ブレークするコード行を含むファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="c77b5-148">コード行を移動します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="c77b5-149">コード行の左側に行番号列があります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="c77b5-150">行番号にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-150">Hover on the line number and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="c77b5-151">[条件付 **きブレークポイントの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-151">Choose **Add conditional breakpoint**.</span></span>  <span data-ttu-id="c77b5-152">コード行の下にダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="c77b5-153">ダイアログに条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="c77b5-154">ブレークポイント `Enter` をアクティブ化する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-154">Select `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="c77b5-155">行番号列の横にあるアイコン。</span><span class="sxs-lookup"><span data-stu-id="c77b5-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件付きコード行ブレークポイント" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="c77b5-157">条件付きコード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a><span data-ttu-id="c77b5-158">コード行ブレークポイントの管理</span><span class="sxs-lookup"><span data-stu-id="c77b5-158">Manage line-of-code breakpoints</span></span>  

<span data-ttu-id="c77b5-159">[ブレークポイント **] ウィンドウを使用** して、1 つの場所からコード行ブレークポイントを無効または削除します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="[ブレークポイント] パネル" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="c77b5-161">[ **ブレークポイント]** パネル</span><span class="sxs-lookup"><span data-stu-id="c77b5-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="c77b5-162">エントリの横にあるチェック ボックスをオンにして、そのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c77b5-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="c77b5-163">エントリにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、そのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-163">Hover on an entry and open the contextual menu \(right-click\) to remove that breakpoint.</span></span>  
*   <span data-ttu-id="c77b5-164">[ブレークポイント] ウィンドウの任意の **場所** にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開いてすべてのブレークポイントを非アクティブ化するか、すべてのブレークポイントを無効にするか、すべてのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-164">Hover anywhere in the **Breakpoints** pane and open the contextual menu \(right-click\) to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="c77b5-165">すべてのブレークポイントを無効にした場合は、各ブレークポイントのチェックを外すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="c77b5-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="c77b5-166">すべてのブレークポイントを非アクティブ化すると、DevTools は、すべてのコード行ブレークポイントを無視するように指示しますが、有効な状態を維持して、各ブレークポイントを再アクティブ化する場合と同じ状態になります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="[ブレークポイント] ウィンドウで非アクティブ化されたブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="c77b5-168">[ブレークポイント] ウィンドウで **非アクティブ化された** ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a><span data-ttu-id="c77b5-169">DOM の変更ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-169">DOM change breakpoints</span></span>  

<span data-ttu-id="c77b5-170">DOM ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="c77b5-171">DOM 変更ブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c77b5-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="c77b5-172">[要素] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-172">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="c77b5-173">ブレークポイントを設定する要素を移動します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="c77b5-174">要素にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-174">Hover on the element and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="c77b5-175">[ブレーク]**をポイントし**、[サブツリーの変更 **] 、[\*\*\*\*属性の変更]**、または [ノードの削除]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-175">Hover on **Break on**, then choose **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="DOM 変更ブレークポイントを作成するためのコンテキスト メニュー" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="c77b5-177">DOM 変更ブレークポイントを作成するためのコンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="c77b5-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a><span data-ttu-id="c77b5-178">DOM 変更ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="c77b5-178">Types of DOM change breakpoints</span></span>  

*   <span data-ttu-id="c77b5-179">**サブツリーの変更**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-179">**Subtree modifications**.</span></span>  <span data-ttu-id="c77b5-180">現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="c77b5-181">子ノード属性の変更、または現在選択されているノードに対する変更ではトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="c77b5-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="c77b5-182">**属性の変更**: 現在選択されているノードで属性が追加または削除された場合、または属性値が変更された場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="c77b5-183">**ノードの削除**: 現在選択されているノードが削除されるとトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <a name="xhrfetch-breakpoints"></a><span data-ttu-id="c77b5-184">XHR/Fetch ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-184">XHR/Fetch breakpoints</span></span>  

<span data-ttu-id="c77b5-185">XHR の要求 URL に指定された文字列が含まれている場合は、XHR ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="c77b5-186">DevTools は、XHR がメソッドを実行するコード行で一時停止 `send()` します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="c77b5-187">この機能は、フェッチ [API 要求でも][MDNFetchApi] 機能します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="c77b5-188">これが役に立つ例の 1 つは、Web ページが正しくない URL を要求し、要求が正しくない原因となっている AJAX または Fetch ソース コードをすばやく見つける場合です。</span><span class="sxs-lookup"><span data-stu-id="c77b5-188">One example of when this is helpful is when your webpage is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="c77b5-189">XHR ブレークポイントを設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="c77b5-190">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-190">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="c77b5-191">**[XHR ブレークポイント] パネルを展開**します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-191">Expand the **XHR Breakpoints** panel.</span></span>  
1.  <span data-ttu-id="c77b5-192">[ブレークポイント **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-192">Choose **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="c77b5-193">折りたたむ文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="c77b5-194">この文字列が XHR 要求 URL の任意の場所に存在する場合、DevTools は一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="c77b5-195">選択 `Enter` して確認します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-195">Select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="XHR ブレークポイントの作成" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="c77b5-197">XHR ブレークポイントの作成</span><span class="sxs-lookup"><span data-stu-id="c77b5-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a><span data-ttu-id="c77b5-198">イベント リスナーのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-198">Event listener breakpoints</span></span>  

<span data-ttu-id="c77b5-199">イベントが発生した後に実行されるイベント リスナー コードで一時停止する場合は、イベント リスナー ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="c77b5-200">すべてのマウス イベントなど、イベントのカテゴリなどの特定のイベント `click` を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="c77b5-201">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-201">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="c77b5-202">[イベント リスナー **ブレークポイント] パネルを展開** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-202">Expand the **Event Listener Breakpoints** panel.</span></span>  <span data-ttu-id="c77b5-203">DevTools には、Animation などのイベント カテゴリの一覧が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="c77b5-204">これらのカテゴリのいずれかを確認して、そのカテゴリのイベントが発生するたびに一時停止するか、カテゴリを展開して特定のイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="イベント リスナーブレークポイントの作成" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="c77b5-206">イベント リスナーブレークポイントの作成</span><span class="sxs-lookup"><span data-stu-id="c77b5-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a><span data-ttu-id="c77b5-207">例外ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-207">Exception breakpoints</span></span>  

<span data-ttu-id="c77b5-208">キャッチまたはキャッチされていない例外をスローするコード行で一時停止する場合は、例外ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="c77b5-209">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-209">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="c77b5-210">[ **例外時に一時停止** する] \( ![ [例外の一時停止 ](../media/pause-on-exceptions-icon.msft.png) ] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-210">Choose **Pause on exceptions** \(![Pause on exceptions](../media/pause-on-exceptions-icon.msft.png)\).</span></span>  <span data-ttu-id="c77b5-211">有効にすると、アイコンが青色に変わります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="[例外時に一時停止] ボタン" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="c77b5-213">[ **例外時に一時停止]** ボタン</span><span class="sxs-lookup"><span data-stu-id="c77b5-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c77b5-214">**省略可能です**。</span><span class="sxs-lookup"><span data-stu-id="c77b5-214">**Optional**.</span></span>  <span data-ttu-id="c77b5-215">キャッチされていない **例外に** 加えて、キャッチされた例外でも一時停止する場合は、[キャッチ例外の一時停止] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c77b5-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="キャッチされない例外で一時停止" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="c77b5-217">キャッチされない例外で一時停止</span><span class="sxs-lookup"><span data-stu-id="c77b5-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <a name="function-breakpoints"></a><span data-ttu-id="c77b5-218">関数のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="c77b5-218">Function breakpoints</span></span>  

<span data-ttu-id="c77b5-219">特定の関数が実行されるたびに一時停止する場合は、デバッグするコマンド、関数、またはメソッドがあるメソッド `debug(method)` `method` を実行します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="c77b5-220">コード (ステートメント `debug()` など) に挿入するか `console.log()` 、DevTools コンソールからメソッドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="c77b5-221">は、関数の最初 [の行](#line-of-code-breakpoints) にコード行ブレークポイントを設定するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="c77b5-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a><span data-ttu-id="c77b5-222">ターゲット関数がスコープ内にあるか確認する</span><span class="sxs-lookup"><span data-stu-id="c77b5-222">Make sure the target function is in scope</span></span>  

<span data-ttu-id="c77b5-223">DevTools は、デバッグする関数がスコープ内にない `ReferenceError` 場合に a をスローします。</span><span class="sxs-lookup"><span data-stu-id="c77b5-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

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

<span data-ttu-id="c77b5-224">DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあるのを確認するのが `debug()` 難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="c77b5-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="c77b5-225">1 つの戦略を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="c77b5-226">関数が [スコープ内にある場所に](#line-of-code-breakpoints) コード行ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="c77b5-227">ブレークポイントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="c77b5-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="c77b5-228">コードがコード行ブレークポイントで一時停止されている間 `debug()` 、DevTools コンソールでメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77b5-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c77b5-229">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c77b5-229">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "FETCH API |MDN"  

> [!NOTE]
> <span data-ttu-id="c77b5-232">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c77b5-232">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c77b5-233">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c77b5-233">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c77b5-235">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c77b5-235">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
