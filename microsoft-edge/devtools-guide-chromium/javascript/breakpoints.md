---
description: Microsoft Edge DevTools でコードを一時停止できるすべての方法について説明します。
title: Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 95aba99c2cfe87f26704faa20964ace5d2abdf51
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992810"
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







# <span data-ttu-id="a5dc6-104">Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法</span><span class="sxs-lookup"><span data-stu-id="a5dc6-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="a5dc6-105">ブレークポイントを使用して JavaScript コードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="a5dc6-106">このガイドでは、DevTools で利用できる各種類のブレークポイントと、それぞれの種類の設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="a5dc6-107">デバッグプロセスの実践的なチュートリアルについては、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevtoolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-107">For a hands-on tutorial of the debugging process, see [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <span data-ttu-id="a5dc6-108">各ブレークポイントの種類を使用する状況の概要</span><span class="sxs-lookup"><span data-stu-id="a5dc6-108">Overview of when to use each breakpoint type</span></span>   

<span data-ttu-id="a5dc6-109">最もよく知られているブレークポイントの種類は、コード行です。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="a5dc6-110">ただし、行コードのブレークポイントを設定するのは効率的ではありません。特に、正確な場所がわからない場合や、大規模なコードベースを使用している場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="a5dc6-111">他の種類のブレークポイントを使用する方法とタイミングを理解することで、デバッグ時に時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="a5dc6-112">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="a5dc6-112">Breakpoint Type</span></span> | <span data-ttu-id="a5dc6-113">一時停止するときに使用する...</span><span class="sxs-lookup"><span data-stu-id="a5dc6-113">Use This When You Want To Pause...</span></span>  |  
|:--- |:--- |  
| [<span data-ttu-id="a5dc6-114">行コード</span><span class="sxs-lookup"><span data-stu-id="a5dc6-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="a5dc6-115">コードの正確な領域。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="a5dc6-116">条件行コード</span><span class="sxs-lookup"><span data-stu-id="a5dc6-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="a5dc6-117">コードの正確な領域で、他の条件が true の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="a5dc6-118">DOM</span><span class="sxs-lookup"><span data-stu-id="a5dc6-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="a5dc6-119">特定の DOM ノードまたは子を変更または削除するコード。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="a5dc6-120">XHR</span><span class="sxs-lookup"><span data-stu-id="a5dc6-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="a5dc6-121">XHR URL に文字列パターンが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="a5dc6-122">イベントリスナー</span><span class="sxs-lookup"><span data-stu-id="a5dc6-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="a5dc6-123">イベント (、など) の後で実行されるコードの `click` 場合。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="a5dc6-124">エラー</span><span class="sxs-lookup"><span data-stu-id="a5dc6-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="a5dc6-125">キャッチされた、またはキャッチされない例外をスローするコード行。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="a5dc6-126">機能</span><span class="sxs-lookup"><span data-stu-id="a5dc6-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="a5dc6-127">特定のコマンド、関数、またはメソッドを実行するたび。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <span data-ttu-id="a5dc6-128">行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-128">Line-of-code breakpoints</span></span>   

<span data-ttu-id="a5dc6-129">調査が必要なコードの正確な領域がわかっている場合は、コード行のブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="a5dc6-130">このコード行が実行される前に、DevTools は常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="a5dc6-131">DevTools で行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="a5dc6-132">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-132">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-133">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="a5dc6-134">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="a5dc6-135">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="a5dc6-136">それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-136">Click on it.</span></span>  <span data-ttu-id="a5dc6-137">[行番号] 列の横に赤いアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="a5dc6-139">行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="a5dc6-140">コードの行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-140">Line-of-code breakpoints in your code</span></span>   

<span data-ttu-id="a5dc6-141">コードからメソッドを実行して、 `debugger` その行にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="a5dc6-142">これは、コード内にブレーク [ポイント](#line-of-code-breakpoints)が設定されている点を除いて、コード内にブレークポイントが設定されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <span data-ttu-id="a5dc6-143">条件行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-143">Conditional line-of-code breakpoints</span></span>   

<span data-ttu-id="a5dc6-144">調査が必要なコードの正確な領域がわかっているが、その他の条件が true の場合にのみ一時停止する必要がある場合は、条件付きコードのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="a5dc6-145">条件行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="a5dc6-146">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-146">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-147">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="a5dc6-148">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="a5dc6-149">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="a5dc6-150">行番号を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-150">Right-click the line number.</span></span>  
1.  <span data-ttu-id="a5dc6-151">[ **条件付きブレークポイントの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-151">Select **Add conditional breakpoint**.</span></span>  <span data-ttu-id="a5dc6-152">ダイアログがコード行の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="a5dc6-153">ダイアログに条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="a5dc6-154">を押して `Enter` 、ブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-154">Press `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="a5dc6-155">[行番号] 列の横にあるアイコン。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="a5dc6-157">条件行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="a5dc6-158">行コードのブレークポイントを管理する</span><span class="sxs-lookup"><span data-stu-id="a5dc6-158">Manage line-of-code breakpoints</span></span>   

<span data-ttu-id="a5dc6-159">[ **ブレークポイント** ] ウィンドウを使用して、1つの場所から行コードのブレークポイントを無効化または削除します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="[ブレークポイント] パネル" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="a5dc6-161">[ **ブレークポイント** ] パネル</span><span class="sxs-lookup"><span data-stu-id="a5dc6-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="a5dc6-162">エントリの横にあるチェックボックスをオンにして、そのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="a5dc6-163">エントリを右クリックして、そのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-163">Right-click an entry to remove that breakpoint.</span></span>  
*   <span data-ttu-id="a5dc6-164">[ **ブレークポイント** ] ウィンドウ内の任意の場所を右クリックして、すべてのブレークポイントを非アクティブ化、すべてのブレークポイントの無効化、すべてのブレークポイントの削除を行います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-164">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="a5dc6-165">すべてのブレークポイントを無効にすることは、それぞれのチェックをオフにすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="a5dc6-166">すべてのブレークポイントを非アクティブ化するには、すべてのコードのブレークポイントを無視するように DevTools を使用しますが、それぞれのブレークポイントを再アクティブ化するときと同じ状態になるように、有効な状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="[ブレークポイント] ウィンドウのブレークダウンの無効化" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="a5dc6-168">[ **ブレークポイント** ] ウィンドウのブレークダウンの無効化</span><span class="sxs-lookup"><span data-stu-id="a5dc6-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a5dc6-169">DOM 変更のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-169">DOM change breakpoints</span></span>   

<span data-ttu-id="a5dc6-170">Dom ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="a5dc6-171">DOM 変更のブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="a5dc6-172">[ **要素** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-172">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-173">ブレークポイントを設定する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="a5dc6-174">要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-174">Right-click the element.</span></span>  
1.  <span data-ttu-id="a5dc6-175">[ **中断] の上に**カーソルを合わせ、[ **サブツリーの変更**]、[属性の **変更**]、または [ **ノードの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-175">Hover over **Break on**, then select **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="DOM 変更ブレークポイントを作成するためのコンテキストメニュー" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="a5dc6-177">DOM 変更ブレークポイントを作成するためのコンテキストメニュー</span><span class="sxs-lookup"><span data-stu-id="a5dc6-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="a5dc6-178">DOM の種類の変更ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-178">Types of DOM change breakpoints</span></span>   

*   <span data-ttu-id="a5dc6-179">**サブツリーの変更**。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-179">**Subtree modifications**.</span></span>  <span data-ttu-id="a5dc6-180">現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="a5dc6-181">子ノードの属性の変更、または現在選択されているノードへの変更に対してトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="a5dc6-182">**属性の変更**: 現在選択されているノードの属性が追加または削除されたとき、または属性値が変更されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="a5dc6-183">**ノードの削除**: 現在選択されているノードが削除されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <span data-ttu-id="a5dc6-184">XHR/Fetch のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-184">XHR/Fetch breakpoints</span></span>   

<span data-ttu-id="a5dc6-185">XHR の要求 URL に指定された文字列が含まれている場合に中断する場合は、XHR ブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="a5dc6-186">DevTools は、XHR がメソッドを実行しているコード行で一時停止し `send()` ます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="a5dc6-187">この機能は、 [FETCH API][MDNFetchApi] 要求でも動作します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="a5dc6-188">これが役に立つ場合の1つの例として、ページで正しくない URL が要求されていることがわかっていて、誤った要求を引き起こしている AJAX またはフェッチソースコードをすばやく見つける必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-188">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="a5dc6-189">XHR のブレークポイントを設定するには:</span><span class="sxs-lookup"><span data-stu-id="a5dc6-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="a5dc6-190">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-190">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-191">[ **Xhr のブレークポイント** ] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-191">Expand the **XHR Breakpoints** pane.</span></span>  
1.  <span data-ttu-id="a5dc6-192">[ **ブレークポイントの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-192">Click **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="a5dc6-193">改ページする文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="a5dc6-194">DevTools は、この文字列が XHR 要求 URL の任意の場所にある場合に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="a5dc6-195">を押して `Enter` 確認します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-195">Press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="XHR ブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="a5dc6-197">XHR ブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="a5dc6-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a5dc6-198">イベントリスナーのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-198">Event listener breakpoints</span></span> 

<span data-ttu-id="a5dc6-199">イベントが発生した後に実行されるイベントリスナーコードで一時停止する場合は、イベントリスナーのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="a5dc6-200">[ `click` すべてのマウスイベント] などのイベントのカテゴリやカテゴリなどの特定のイベントを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="a5dc6-201">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-201">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-202">[ **イベントリスナーのブレークポイント** ] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-202">Expand the **Event Listener Breakpoints** pane.</span></span>  <span data-ttu-id="a5dc6-203">[DevTools] は、 **アニメーション**などのイベントカテゴリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="a5dc6-204">いずれかのカテゴリをチェックして、そのカテゴリのイベントが発生したときに一時停止するか、カテゴリを展開して特定のイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="イベントリスナーのブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="a5dc6-206">イベントリスナーのブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="a5dc6-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a5dc6-207">例外のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-207">Exception breakpoints</span></span>   

<span data-ttu-id="a5dc6-208">キャッチまたはキャッチされない例外をスローするコード行で一時停止する場合は、例外のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="a5dc6-209">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-209">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="a5dc6-210">[ **例外時に一時停止] を** クリックします (例外がある場合は ![ 一時停止し ][ImagePauseOnExceptionsIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-210">Click **Pause on exceptions** \(![Pause on exceptions][ImagePauseOnExceptionsIcon]\).</span></span>  <span data-ttu-id="a5dc6-211">有効にすると、アイコンが青色に変わります。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="[例外時に一時停止] ボタン" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="a5dc6-213">**[例外時に一時停止**] ボタン</span><span class="sxs-lookup"><span data-stu-id="a5dc6-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a5dc6-214">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-214">**Optional**.</span></span>  <span data-ttu-id="a5dc6-215">キャッチされていない例外にも一時停止したい場合は、 **[キャッチした例外を一時停止** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="キャッチされていない例外で一時停止" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="a5dc6-217">キャッチされていない例外で一時停止</span><span class="sxs-lookup"><span data-stu-id="a5dc6-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a5dc6-218">関数のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a5dc6-218">Function breakpoints</span></span>   

<span data-ttu-id="a5dc6-219">特定の `debug(method)` `method` 関数が実行されているときに一時停止する必要がある場合は、デバッグするコマンド、関数、またはメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="a5dc6-220">`debug()`コード (ステートメントなど) に挿入し `console.log()` たり、Devtools コンソールからメソッドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="a5dc6-221">関数の最初の行に [行コードのブレークポイント](#line-of-code-breakpoints) を設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <span data-ttu-id="a5dc6-222">ターゲット関数が範囲内にあることを確認する</span><span class="sxs-lookup"><span data-stu-id="a5dc6-222">Make sure the target function is in scope</span></span>   

<span data-ttu-id="a5dc6-223">DevTools は、 `ReferenceError` デバッグする関数がスコープ外であるかどうかをスローします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

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

<span data-ttu-id="a5dc6-224">DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあることを確認するのが複雑になり `debug()` ます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="a5dc6-225">1つの戦略を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="a5dc6-226">関数がスコープ内のどこかにある [行コードのブレークポイント](#line-of-code-breakpoints) を設定します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="a5dc6-227">ブレークポイントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="a5dc6-228">コード `debug()` が行のブレークポイントで一時停止されている状態で、DevTools コンソールでこのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
<!---  
 


-->  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要 |Microsoft ドキュメント"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  

> [!NOTE]
> <span data-ttu-id="a5dc6-231">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-231">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a5dc6-232">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-232">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a5dc6-234">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a5dc6-234">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
