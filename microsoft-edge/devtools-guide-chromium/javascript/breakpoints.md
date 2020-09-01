---
title: Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 804e864ee3029a49ba1ef2ac1f2deb61c3ba5ec3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983207"
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







# <span data-ttu-id="e2ed5-103">Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法</span><span class="sxs-lookup"><span data-stu-id="e2ed5-103">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="e2ed5-104">ブレークポイントを使用して JavaScript コードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-104">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="e2ed5-105">このガイドでは、DevTools で利用できる各種類のブレークポイントと、それぞれの種類の設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-105">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="e2ed5-106">デバッグプロセスの実践的なチュートリアルについては、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevtoolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-106">For a hands-on tutorial of the debugging process, see [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <span data-ttu-id="e2ed5-107">各ブレークポイントの種類を使用する状況の概要</span><span class="sxs-lookup"><span data-stu-id="e2ed5-107">Overview of when to use each breakpoint type</span></span>   

<span data-ttu-id="e2ed5-108">最もよく知られているブレークポイントの種類は、コード行です。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-108">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="e2ed5-109">ただし、行コードのブレークポイントを設定するのは効率的ではありません。特に、正確な場所がわからない場合や、大規模なコードベースを使用している場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-109">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="e2ed5-110">他の種類のブレークポイントを使用する方法とタイミングを理解することで、デバッグ時に時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-110">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="e2ed5-111">ブレークポイントの種類</span><span class="sxs-lookup"><span data-stu-id="e2ed5-111">Breakpoint Type</span></span> | <span data-ttu-id="e2ed5-112">一時停止するときに使用する...</span><span class="sxs-lookup"><span data-stu-id="e2ed5-112">Use This When You Want To Pause...</span></span>  |  
|:--- |:--- |  
| [<span data-ttu-id="e2ed5-113">行コード</span><span class="sxs-lookup"><span data-stu-id="e2ed5-113">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="e2ed5-114">コードの正確な領域。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-114">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="e2ed5-115">条件行コード</span><span class="sxs-lookup"><span data-stu-id="e2ed5-115">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="e2ed5-116">コードの正確な領域で、他の条件が true の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-116">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="e2ed5-117">DOM</span><span class="sxs-lookup"><span data-stu-id="e2ed5-117">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="e2ed5-118">特定の DOM ノードまたは子を変更または削除するコード。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-118">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="e2ed5-119">XHR</span><span class="sxs-lookup"><span data-stu-id="e2ed5-119">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="e2ed5-120">XHR URL に文字列パターンが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-120">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="e2ed5-121">イベントリスナー</span><span class="sxs-lookup"><span data-stu-id="e2ed5-121">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="e2ed5-122">イベント (、など) の後で実行されるコードの `click` 場合。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-122">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="e2ed5-123">エラー</span><span class="sxs-lookup"><span data-stu-id="e2ed5-123">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="e2ed5-124">キャッチされた、またはキャッチされない例外をスローするコード行。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-124">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="e2ed5-125">機能</span><span class="sxs-lookup"><span data-stu-id="e2ed5-125">Function</span></span>](#function-breakpoints) | <span data-ttu-id="e2ed5-126">特定のコマンド、関数、またはメソッドを実行するたび。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-126">Whenever a specific command, function, or method is run.</span></span>  |  

## <span data-ttu-id="e2ed5-127">行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-127">Line-of-code breakpoints</span></span>   

<span data-ttu-id="e2ed5-128">調査が必要なコードの正確な領域がわかっている場合は、コード行のブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-128">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="e2ed5-129">このコード行が実行される前に、DevTools は常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-129">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="e2ed5-130">DevTools で行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-130">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="e2ed5-131">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-131">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-132">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-132">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="e2ed5-133">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-133">Go the line of code.</span></span>  
1.  <span data-ttu-id="e2ed5-134">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-134">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="e2ed5-135">それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-135">Click on it.</span></span>  <span data-ttu-id="e2ed5-136">[行番号] 列の横に赤いアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-136">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="e2ed5-138">行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-138">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e2ed5-139">コードの行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-139">Line-of-code breakpoints in your code</span></span>   

<span data-ttu-id="e2ed5-140">コードからメソッドを実行して、 `debugger` その行にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-140">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="e2ed5-141">これは、コード内にブレーク [ポイント](#line-of-code-breakpoints)が設定されている点を除いて、コード内にブレークポイントが設定されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-141">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <span data-ttu-id="e2ed5-142">条件行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-142">Conditional line-of-code breakpoints</span></span>   

<span data-ttu-id="e2ed5-143">調査が必要なコードの正確な領域がわかっているが、その他の条件が true の場合にのみ一時停止する必要がある場合は、条件付きコードのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-143">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="e2ed5-144">条件行コードのブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-144">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="e2ed5-145">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-145">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-146">改ページするコードの行が含まれているファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-146">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="e2ed5-147">コードの行に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-147">Go the line of code.</span></span>  
1.  <span data-ttu-id="e2ed5-148">コード行の左側には、[行番号列を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-148">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="e2ed5-149">行番号を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-149">Right-click the line number.</span></span>  
1.  <span data-ttu-id="e2ed5-150">[ **条件付きブレークポイントの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-150">Select **Add conditional breakpoint**.</span></span>  <span data-ttu-id="e2ed5-151">ダイアログがコード行の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-151">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="e2ed5-152">ダイアログに条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-152">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="e2ed5-153">を押して `Enter` 、ブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-153">Press `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="e2ed5-154">[行番号] 列の横にあるアイコン。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-154">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="e2ed5-156">条件行コードのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-156">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e2ed5-157">行コードのブレークポイントを管理する</span><span class="sxs-lookup"><span data-stu-id="e2ed5-157">Manage line-of-code breakpoints</span></span>   

<span data-ttu-id="e2ed5-158">[ **ブレークポイント** ] ウィンドウを使用して、1つの場所から行コードのブレークポイントを無効化または削除します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-158">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="[ブレークポイント] パネル" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="e2ed5-160">[ **ブレークポイント** ] パネル</span><span class="sxs-lookup"><span data-stu-id="e2ed5-160">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="e2ed5-161">エントリの横にあるチェックボックスをオンにして、そのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-161">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="e2ed5-162">エントリを右クリックして、そのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-162">Right-click an entry to remove that breakpoint.</span></span>  
*   <span data-ttu-id="e2ed5-163">[ **ブレークポイント** ] ウィンドウ内の任意の場所を右クリックして、すべてのブレークポイントを非アクティブ化、すべてのブレークポイントの無効化、すべてのブレークポイントの削除を行います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-163">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="e2ed5-164">すべてのブレークポイントを無効にすることは、それぞれのチェックをオフにすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-164">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="e2ed5-165">すべてのブレークポイントを非アクティブ化するには、すべてのコードのブレークポイントを無視するように DevTools を使用しますが、それぞれのブレークポイントを再アクティブ化するときと同じ状態になるように、有効な状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-165">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="[ブレークポイント] ウィンドウのブレークダウンの無効化" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="e2ed5-167">[ **ブレークポイント** ] ウィンドウのブレークダウンの無効化</span><span class="sxs-lookup"><span data-stu-id="e2ed5-167">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e2ed5-168">DOM 変更のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-168">DOM change breakpoints</span></span>   

<span data-ttu-id="e2ed5-169">Dom ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-169">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="e2ed5-170">DOM 変更のブレークポイントを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-170">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="e2ed5-171">[ **要素** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-171">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-172">ブレークポイントを設定する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-172">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="e2ed5-173">要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-173">Right-click the element.</span></span>  
1.  <span data-ttu-id="e2ed5-174">[ **中断] の上に**カーソルを合わせ、[ **サブツリーの変更**]、[属性の **変更**]、または [ **ノードの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-174">Hover over **Break on**, then select **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="DOM 変更ブレークポイントを作成するためのコンテキストメニュー" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="e2ed5-176">DOM 変更ブレークポイントを作成するためのコンテキストメニュー</span><span class="sxs-lookup"><span data-stu-id="e2ed5-176">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e2ed5-177">DOM の種類の変更ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-177">Types of DOM change breakpoints</span></span>   

*   <span data-ttu-id="e2ed5-178">**サブツリーの変更**。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-178">**Subtree modifications**.</span></span>  <span data-ttu-id="e2ed5-179">現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-179">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="e2ed5-180">子ノードの属性の変更、または現在選択されているノードへの変更に対してトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-180">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="e2ed5-181">**属性の変更**: 現在選択されているノードの属性が追加または削除されたとき、または属性値が変更されたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-181">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="e2ed5-182">**ノードの削除**: 現在選択されているノードが削除されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-182">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <span data-ttu-id="e2ed5-183">XHR/Fetch のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-183">XHR/Fetch breakpoints</span></span>   

<span data-ttu-id="e2ed5-184">XHR の要求 URL に指定された文字列が含まれている場合に中断する場合は、XHR ブレークポイントを使います。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-184">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="e2ed5-185">DevTools は、XHR がメソッドを実行しているコード行で一時停止し `send()` ます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-185">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2ed5-186">この機能は、 [FETCH API][MDNFetchApi] 要求でも動作します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-186">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="e2ed5-187">これが役に立つ場合の1つの例として、ページで正しくない URL が要求されていることがわかっていて、誤った要求を引き起こしている AJAX またはフェッチソースコードをすばやく見つける必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-187">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="e2ed5-188">XHR のブレークポイントを設定するには:</span><span class="sxs-lookup"><span data-stu-id="e2ed5-188">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="e2ed5-189">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-189">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-190">[ **Xhr のブレークポイント** ] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-190">Expand the **XHR Breakpoints** pane.</span></span>  
1.  <span data-ttu-id="e2ed5-191">[ **ブレークポイントの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-191">Click **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="e2ed5-192">改ページする文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-192">Enter the string which you want to break on.</span></span>  <span data-ttu-id="e2ed5-193">DevTools は、この文字列が XHR 要求 URL の任意の場所にある場合に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-193">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="e2ed5-194">を押して `Enter` 確認します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-194">Press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="XHR ブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="e2ed5-196">XHR ブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ed5-196">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e2ed5-197">イベントリスナーのブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-197">Event listener breakpoints</span></span> 

<span data-ttu-id="e2ed5-198">イベントが発生した後に実行されるイベントリスナーコードで一時停止する場合は、イベントリスナーのブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-198">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="e2ed5-199">[ `click` すべてのマウスイベント] などのイベントのカテゴリやカテゴリなどの特定のイベントを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-199">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="e2ed5-200">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-200">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-201">[ **イベントリスナーのブレークポイント** ] ウィンドウを展開します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-201">Expand the **Event Listener Breakpoints** pane.</span></span>  <span data-ttu-id="e2ed5-202">[DevTools] は、 **アニメーション**などのイベントカテゴリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-202">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="e2ed5-203">いずれかのカテゴリをチェックして、そのカテゴリのイベントが発生したときに一時停止するか、カテゴリを展開して特定のイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-203">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="イベントリスナーのブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="e2ed5-205">イベントリスナーのブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ed5-205">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e2ed5-206">例外のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-206">Exception breakpoints</span></span>   

<span data-ttu-id="e2ed5-207">キャッチまたはキャッチされない例外をスローするコード行で一時停止する場合は、例外のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-207">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="e2ed5-208">[ **ソース** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-208">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e2ed5-209">[ **例外時に一時停止] を** クリックします (例外がある場合は ![ 一時停止し ][ImagePauseOnExceptionsIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-209">Click **Pause on exceptions** \(![Pause on exceptions][ImagePauseOnExceptionsIcon]\).</span></span>  <span data-ttu-id="e2ed5-210">有効にすると、アイコンが青色に変わります。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-210">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="[例外時に一時停止] ボタン" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="e2ed5-212">**[例外時に一時停止**] ボタン</span><span class="sxs-lookup"><span data-stu-id="e2ed5-212">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e2ed5-213">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-213">**Optional**.</span></span>  <span data-ttu-id="e2ed5-214">キャッチされていない例外にも一時停止したい場合は、 **[キャッチした例外を一時停止** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-214">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="キャッチされていない例外で一時停止" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="e2ed5-216">キャッチされていない例外で一時停止</span><span class="sxs-lookup"><span data-stu-id="e2ed5-216">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="e2ed5-217">関数のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e2ed5-217">Function breakpoints</span></span>   

<span data-ttu-id="e2ed5-218">特定の `debug(method)` `method` 関数が実行されているときに一時停止する必要がある場合は、デバッグするコマンド、関数、またはメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-218">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="e2ed5-219">`debug()`コード (ステートメントなど) に挿入し `console.log()` たり、Devtools コンソールからメソッドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-219">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="e2ed5-220">関数の最初の行に [行コードのブレークポイント](#line-of-code-breakpoints) を設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-220">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <span data-ttu-id="e2ed5-221">ターゲット関数が範囲内にあることを確認する</span><span class="sxs-lookup"><span data-stu-id="e2ed5-221">Make sure the target function is in scope</span></span>   

<span data-ttu-id="e2ed5-222">DevTools は、 `ReferenceError` デバッグする関数がスコープ外であるかどうかをスローします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-222">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

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

<span data-ttu-id="e2ed5-223">DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあることを確認するのが複雑になり `debug()` ます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-223">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="e2ed5-224">1つの戦略を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-224">Here is one strategy:</span></span>  

1.  <span data-ttu-id="e2ed5-225">関数がスコープ内のどこかにある [行コードのブレークポイント](#line-of-code-breakpoints) を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-225">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="e2ed5-226">ブレークポイントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-226">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="e2ed5-227">コード `debug()` が行のブレークポイントで一時停止されている状態で、DevTools コンソールでこのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-227">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
<!---  
 


-->  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要 |Microsoft ドキュメント"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  

> [!NOTE]
> <span data-ttu-id="e2ed5-230">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-230">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e2ed5-231">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-231">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e2ed5-233">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e2ed5-233">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
