---
title: コンソールユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 28b40f3f79928725d3d49418e01cf02247224370
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601797"
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





# <span data-ttu-id="1c046-103">コンソールユーティリティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="1c046-103">Console Utilities API Reference</span></span>   



<span data-ttu-id="1c046-104">コンソールユーティリティ API には、一般的なタスク (DOM 要素の選択と検査、読み取り可能な形式でのデータの表示、プロファイラーの停止と開始、DOM イベントの監視) を実行するための便利なコマンドのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c046-104">The Console Utilities API contains a collection of convenience commands for performing common tasks:  selecting and inspecting DOM elements, displaying data in readable format, stopping and starting the profiler, and monitoring DOM events.</span></span>  

> [!WARNING]
> <span data-ttu-id="1c046-105">次のコマンドは、Microsoft Edge DevTools コンソールでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="1c046-105">The following commands only work in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="1c046-106">スクリプトから実行した場合、コマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="1c046-106">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="1c046-107">およびその他のメソッドを探してい `console.log()` `console.error()` `console.*` ますか?</span><span class="sxs-lookup"><span data-stu-id="1c046-107">Looking for `console.log()`, `console.error()`, and the rest of the `console.*` methods?</span></span>  <span data-ttu-id="1c046-108">「[コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c046-108">See [Console API Reference][DevToolsConsoleApi].</span></span>  

## <span data-ttu-id="1c046-109">最近評価された式</span><span class="sxs-lookup"><span data-stu-id="1c046-109">Recently Evaluated Expression</span></span>  

```console
$_
```  

<span data-ttu-id="1c046-110">直近に評価された式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-110">Returns the value of the most recently evaluated expression.</span></span>  

<span data-ttu-id="1c046-111">[図 1](#figure-1)では、単純な式 \ ( `2 + 2` \) が評価されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-111">In [Figure 1](#figure-1), a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="1c046-112">`$_`プロパティが評価され、同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c046-112">The `$_` property is then evaluated, which contains the same value.</span></span>  

> ##### <span data-ttu-id="1c046-113">図 1</span><span class="sxs-lookup"><span data-stu-id="1c046-113">Figure 1</span></span>  
> `$_` <span data-ttu-id="1c046-114">は、最後に評価された式です。</span><span class="sxs-lookup"><span data-stu-id="1c046-114">is the most recently evaluated expression</span></span>  
> ![$ _ は、最近評価された式です。][ImageRecentExpression]  

<span data-ttu-id="1c046-116">[図 2](#figure-2)では、最初に評価式に名前の配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c046-116">In [Figure 2](#figure-2), the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="1c046-117">評価して `$_.length` 配列の長さを確認します。変更された値は、 `$_` 最新の評価済みの式になり `4` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-117">Evaluating `$_.length` to find the length of the array, the value stored in `$_` changes to become the latest evaluated expression, `4`.</span></span>  

> ##### <span data-ttu-id="1c046-118">図 2</span><span class="sxs-lookup"><span data-stu-id="1c046-118">Figure 2</span></span>  
> `$_` <span data-ttu-id="1c046-119">新しいコマンドの評価時の変更点</span><span class="sxs-lookup"><span data-stu-id="1c046-119">changes when new commands are evaluated</span></span>  
> ![新しいコマンドが評価されたときの $ _ 変更][ImageChangedRecentExpression]  

## <span data-ttu-id="1c046-121">最近選んだ要素または JavaScript オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1c046-121">Recently Selected Element Or JavaScript Object</span></span>  

```console
$0
```  

<span data-ttu-id="1c046-122">最後に選択された要素または JavaScript オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-122">Returns the most recently selected element or JavaScript object.</span></span>  `$1` <span data-ttu-id="1c046-123">最後に選択された2番目の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-123">returns the second most recently selected one, and so on.</span></span>  <span data-ttu-id="1c046-124">、、、、 `$0` `$1` およびコマンドは、 `$2` `$3` `$4` **要素**パネル内で検査された最後の5つの DOM 要素、または**メモリ**パネルで選択された最後の5つの JavaScript ヒープオブジェクトへの履歴参照として機能します。</span><span class="sxs-lookup"><span data-stu-id="1c046-124">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** panel or the last five JavaScript heap objects selected in the **Memory** panel.</span></span>  

```console
$1
```  

```console
$2
```  

```console
$3
```  

```console
$4
```  

<span data-ttu-id="1c046-125">[図 3](#figure-3)では、[ `img` **要素**] パネルで要素が選択されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-125">In [Figure 3](#figure-3), an `img` element is selected in the **Elements** panel.</span></span>  <span data-ttu-id="1c046-126">**本体**のドロアーで、 `$0` 評価が完了し、同じ要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-126">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

> ##### <span data-ttu-id="1c046-127">図 3</span><span class="sxs-lookup"><span data-stu-id="1c046-127">Figure 3</span></span>  
> <span data-ttu-id="1c046-128">、</span><span class="sxs-lookup"><span data-stu-id="1c046-128">The</span></span> `$0`  
> ![$0][ImageElement0]  

<span data-ttu-id="1c046-130">[図 4](#figure-4)では、同じページで選択された別の要素が画像に表示されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-130">In [Figure 4](#figure-4), the image shows a different element selected in the same page.</span></span>  <span data-ttu-id="1c046-131">現在選択されている `$0` 要素を参照して `$1` いますが、以前に選択されていた要素を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-131">The `$0` now refers to the newly selected element, while `$1` returns the previously selected one.</span></span>  

> ##### <span data-ttu-id="1c046-132">図 4</span><span class="sxs-lookup"><span data-stu-id="1c046-132">Figure 4</span></span>  
> <span data-ttu-id="1c046-133">、</span><span class="sxs-lookup"><span data-stu-id="1c046-133">The</span></span> `$1`  
> ![$1][ImageElement1]  

## <span data-ttu-id="1c046-135">クエリセレクター</span><span class="sxs-lookup"><span data-stu-id="1c046-135">Query Selector</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="1c046-136">指定された CSS セレクターで最初の DOM 要素への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-136">Returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="1c046-137">このメソッドは、[ドキュメントの querySelector ()][MDNDocumentQuerySelector]メソッドのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="1c046-137">This method is an alias for the [document.querySelector()][MDNDocumentQuerySelector] method.</span></span>  

<span data-ttu-id="1c046-138">[図 5](#figure-5)では、文書内の最初の要素への参照 `<img>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-138">In [Figure 5](#figure-5), a reference to the first `<img>` element in the document is returned.</span></span>  

> ##### <span data-ttu-id="1c046-139">図 5</span><span class="sxs-lookup"><span data-stu-id="1c046-139">Figure 5</span></span>  
> <span data-ttu-id="1c046-140">、</span><span class="sxs-lookup"><span data-stu-id="1c046-140">The</span></span> `$('img')`  
> ![$ (' Img ')][ImageElementImg]  

<span data-ttu-id="1c046-142">返された結果を右クリックし、[**要素パネルで**表示] を選択して DOM で見つけます。または、[表示] に**スクロール**して、ページに表示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-142">Right-click on the returned result and select **Reveal in Elements Panel** to find it in the DOM, or **Scroll in to View** to show it on the page.</span></span>  

<span data-ttu-id="1c046-143">[図 6](#figure-6)では、現在選択されている要素への参照が返され、src プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-143">In [Figure 6](#figure-6), a reference to the currently selected element is returned and the src property is displayed.</span></span>  

> ##### <span data-ttu-id="1c046-144">図 6</span><span class="sxs-lookup"><span data-stu-id="1c046-144">Figure 6</span></span>  
> <span data-ttu-id="1c046-145">、</span><span class="sxs-lookup"><span data-stu-id="1c046-145">The</span></span> `$('img').src`  
> ![$ (' Img ') src][ImageElementImgSource]  

<span data-ttu-id="1c046-147">このメソッドは、要素を検索する "element" またはノードを指定する2番目のパラメーター startNode もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1c046-147">This method also supports a second parameter, startNode, that specifies an "element" or Node from which to search for elements.</span></span>  <span data-ttu-id="1c046-148">このパラメーターの既定値は `document` です。</span><span class="sxs-lookup"><span data-stu-id="1c046-148">The default value of this parameter is `document`.</span></span>  

<span data-ttu-id="1c046-149">[図 7](#figure-7)では、最初 `img` の要素がであり、 `title--image` 正しく表示され `src` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-149">In [Figure 7](#figure-7), the first `img` element is found after the `title--image` and displays the `src` properly is returned.</span></span>  

> ##### <span data-ttu-id="1c046-150">図 7</span><span class="sxs-lookup"><span data-stu-id="1c046-150">Figure 7</span></span>  
> <span data-ttu-id="1c046-151">$ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src</span><span class="sxs-lookup"><span data-stu-id="1c046-151">The $('img', document.querySelector('title--image')).src</span></span>  
> ![$ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src][ImageElementImgNodeSource]  

> [!NOTE]
> <span data-ttu-id="1c046-153">使用する jQuery などのライブラリを使用している場合 `$` 、この機能は上書きされ、 `$` そのライブラリの実装に対応します。</span><span class="sxs-lookup"><span data-stu-id="1c046-153">If you are using a library such as jQuery that uses `$`, this functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

## <span data-ttu-id="1c046-154">すべてのクエリセレクター</span><span class="sxs-lookup"><span data-stu-id="1c046-154">Query Selector All</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="1c046-155">指定された CSS セレクターに一致する要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-155">Returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="1c046-156">このメソッドは、 [querySelectorAll ()][MDNDocumentQuerySelectorAll]メソッドを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="1c046-156">This method is equivalent to calling the [document.querySelectorAll()][MDNDocumentQuerySelectorAll] method.</span></span>  

<span data-ttu-id="1c046-157">[図 8](#figure-8)では、を使用して、 `$$()` 現在のドキュメント内のすべての要素の配列を作成 `<img>` し、各要素のプロパティの値を表示し `src` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-157">In [Figure 8](#figure-8), use `$$()` to create an array of all `<img>` elements in the current document and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

> ##### <span data-ttu-id="1c046-158">図 8</span><span class="sxs-lookup"><span data-stu-id="1c046-158">Figure 8</span></span>  
> <span data-ttu-id="1c046-159">`$$()`ドキュメント内のすべての画像を選択してソースを表示するために使用する</span><span class="sxs-lookup"><span data-stu-id="1c046-159">Using `$$()` to select all images in the document and display the sources</span></span>  
> ![$ $ () を使用して、ドキュメント内のすべての画像を選択し、ソースを表示する][ImageArrayElementImgSource]  

<span data-ttu-id="1c046-161">このメソッドは、要素を検索する要素またはノードを指定する2番目の parameter startNode もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1c046-161">This method also supports a second parameter, startNode, that specifies an element or Node from which to search for elements.</span></span>  <span data-ttu-id="1c046-162">このパラメーターの既定値は `document` です。</span><span class="sxs-lookup"><span data-stu-id="1c046-162">The default value of this parameter is `document`.</span></span>  

<span data-ttu-id="1c046-163">[図 9](#figure-9)では、変更されたバージョンの[図 8](#figure-8)を使用して、 `$$()` `<img>` 選択したノードの後に現在の文書内に出現するすべての要素の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="1c046-163">In [Figure 9](#figure-9), a modified version of [Figure 8](#figure-8) uses `$$()` to create an array of all `<img>` elements that appear in the current document after the selected Node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

> ##### <span data-ttu-id="1c046-164">図 9</span><span class="sxs-lookup"><span data-stu-id="1c046-164">Figure 9</span></span>  
> <span data-ttu-id="1c046-165">`$$()`文書内の指定された要素の後に表示されるすべての画像を選択してソースを表示するために使用する `<div>`</span><span class="sxs-lookup"><span data-stu-id="1c046-165">Using `$$()` to select all images that appear after the specified `<div>` element in the document and display the sources</span></span>  
> ![$ $ () を使用して、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する][ImageArrayElementImgNodeSource]  

> [!NOTE]
> <span data-ttu-id="1c046-167">コンソールを押して、 `Shift` + `Enter` スクリプトを実行せずに、新しい行を開始します。</span><span class="sxs-lookup"><span data-stu-id="1c046-167">Press `Shift`+`Enter` in the console to start a new line without running the script.</span></span>  

## <span data-ttu-id="1c046-168">X</span><span class="sxs-lookup"><span data-stu-id="1c046-168">XPath</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="1c046-169">指定された XPath 式と一致する DOM 要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-169">Returns an array of DOM elements that match the specified XPath expression.</span></span>  

<span data-ttu-id="1c046-170">[図 10](#figure-10)では、ページ上のすべての `<p>` 要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-170">In [Figure 10](#figure-10), all of the `<p>` elements on the page are returned.</span></span>  

```console
$x("//p")
```  

> ##### <span data-ttu-id="1c046-171">図 10</span><span class="sxs-lookup"><span data-stu-id="1c046-171">Figure 10</span></span>  
> <span data-ttu-id="1c046-172">XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="1c046-172">Using an XPath selector</span></span>  
> ![XPath セレクターを使用する][ImageArrayXpath]  

<span data-ttu-id="1c046-174">[図 11](#figure-11)で `<p>` は、要素を含むすべての要素 `<a>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-174">In [Figure 11](#figure-11), all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

> ##### <span data-ttu-id="1c046-175">図 11</span><span class="sxs-lookup"><span data-stu-id="1c046-175">Figure 11</span></span>  
> <span data-ttu-id="1c046-176">より複雑な XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="1c046-176">Using a more complicated XPath selector</span></span>  
> ![より複雑な XPath セレクターを使用する][ImageArrayXpathChild]  

<span data-ttu-id="1c046-178">他のセレクターコマンドと同様に、 `$x(path)` `startNode` 要素を検索する要素またはノードを指定する、オプションの2番目のパラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="1c046-178">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or Node from which to search for elements.</span></span>  

> ##### <span data-ttu-id="1c046-179">図 12</span><span class="sxs-lookup"><span data-stu-id="1c046-179">Figure 12</span></span>  
> <span data-ttu-id="1c046-180">XPath セレクターの使い方</span><span class="sxs-lookup"><span data-stu-id="1c046-180">Using an XPath selector with</span></span> `startNode`  
> ![StartNode で XPath セレクターを使用する][ImageArrayXpathNode]  

## <span data-ttu-id="1c046-182">clear</span><span class="sxs-lookup"><span data-stu-id="1c046-182">clear</span></span>  

```console
clear()
```  

<span data-ttu-id="1c046-183">履歴の本体をクリアします。</span><span class="sxs-lookup"><span data-stu-id="1c046-183">Clears the console of the history.</span></span>  

```console
clear()
```  

## <span data-ttu-id="1c046-184">copy</span><span class="sxs-lookup"><span data-stu-id="1c046-184">copy</span></span>  

```console
copy(object)
```  

<span data-ttu-id="1c046-185">メソッドによって、 `copy(object)` 指定したオブジェクトの文字列表現がクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1c046-185">The `copy(object)` method copies a string representation of the specified object to the clipboard.</span></span>  

```console
copy($0)
```  

## <span data-ttu-id="1c046-186">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1c046-186">debug</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="1c046-187">[Chromium 問題 #1050237][MonorailIssue1050237]は、関数のバグを追跡 `debug()` しています。</span><span class="sxs-lookup"><span data-stu-id="1c046-187">The [Chromium issue #1050237][MonorailIssue1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="1c046-188">この問題が発生した場合は、代わりに[ブレークポイントを使用][DevtoolsJavascriptBreakpoints]してみてください。</span><span class="sxs-lookup"><span data-stu-id="1c046-188">If you encounter this issue, try [using breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="1c046-189">指定したメソッドを要求すると、デバッガーが呼び出され、**ソース**パネルのメソッド内で中断されます。これにより、コードをステップ実行してデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c046-189">When you request the specified method, the debugger is invoked and breaks inside the method on the **Sources** panel allowing you to step through the code and debug it.</span></span>  

```console
debug("debug");
```  

> ##### <span data-ttu-id="1c046-190">図 13</span><span class="sxs-lookup"><span data-stu-id="1c046-190">Figure 13</span></span>  
> <span data-ttu-id="1c046-191">メソッド内での区切り</span><span class="sxs-lookup"><span data-stu-id="1c046-191">Breaking inside a method with</span></span> `debug()`  
> ![Debug () を使用したメソッド内の中断][ImageDebugMethod]  

<span data-ttu-id="1c046-193">`undebug(method)`メソッドの中断を停止するには、または UI を使ってすべてのブレークポイントを無効にする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1c046-193">Use `undebug(method)` to stop breaking on the method, or use the UI to disable all breakpoints.</span></span>  

<span data-ttu-id="1c046-194">ブレークポイントの詳細については、「[ブレークポイントでコードを一時停止][DevToolsJavascriptBreakpoints]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c046-194">For more information on breakpoints, see [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <span data-ttu-id="1c046-195">dir</span><span class="sxs-lookup"><span data-stu-id="1c046-195">dir</span></span>  

```console
dir(object)
```  

<span data-ttu-id="1c046-196">指定したオブジェクトのすべてのプロパティのオブジェクトスタイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-196">Displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="1c046-197">このメソッドは、 [console. dir ()][MDNConsoleDir]メソッドのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="1c046-197">This method is an alias for the [console.dir()][MDNConsoleDir] method.</span></span>  

<span data-ttu-id="1c046-198">本体でを評価して、 `document.head` タグとタグの間に HTML を表示し `<head>` `</head>` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-198">Evaluate `document.head` in the Console to display the HTML between the `<head>` and `</head>` tags.</span></span>  <span data-ttu-id="1c046-199">[図 14](#figure-14)では、コンソールで使用した後にオブジェクトスタイルの一覧が表示され `console.dir()` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-199">In [Figure 14](#figure-14), an object-style listing is displayed after using `console.dir()` in the Console.</span></span>  

```console
document.head;
dir(document.head);
```  

> ##### <span data-ttu-id="1c046-200">図 14</span><span class="sxs-lookup"><span data-stu-id="1c046-200">Figure 14</span></span>  
> <span data-ttu-id="1c046-201">ログ `document.head` 記録 `dir()` メソッド</span><span class="sxs-lookup"><span data-stu-id="1c046-201">Logging `document.head` with `dir()` method</span></span>  
> ![Dir () メソッドを使ってドキュメントをログに記録します。][ImageLogObject]  

<span data-ttu-id="1c046-203">詳細については、 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 本体 API のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c046-203">For more information, see the [`console.dir()`][DevToolsConsoleApiConsoleDirObject] entry in the Console API.</span></span>  

## <span data-ttu-id="1c046-204">dirxml</span><span class="sxs-lookup"><span data-stu-id="1c046-204">dirxml</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="1c046-205">[**要素**] タブに表示されるように、指定したオブジェクトの XML 表現を印刷します。 このメソッドは、console の[dirxml ()][MDNConsoleDirxml]メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="1c046-205">Prints an XML representation of the specified object, as seen in the **Elements** tab.  This method is equivalent to the [console.dirxml()][MDNConsoleDirxml] method.</span></span>  

## <span data-ttu-id="1c046-206">検査</span><span class="sxs-lookup"><span data-stu-id="1c046-206">inspect</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="1c046-207">適切なパネル (DOM 要素の場合は**要素**パネル、JavaScript ヒープオブジェクトの場合は**メモリ**パネル) で、指定された要素またはオブジェクトを開き、選択します。</span><span class="sxs-lookup"><span data-stu-id="1c046-207">Opens and selects the specified element or object in the appropriate panel:  either the **Elements** panel for DOM elements or the **Memory** panel for JavaScript heap objects.</span></span>  

<span data-ttu-id="1c046-208">[図 15](#figure-15)では、[ `document.body` **要素**] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="1c046-208">In [Figure 15](#figure-15), the `document.body` opens in the **Elements** panel.</span></span>  

```console
inspect(document.body);
```  

> ##### <span data-ttu-id="1c046-209">図 15</span><span class="sxs-lookup"><span data-stu-id="1c046-209">Figure 15</span></span>  
> <span data-ttu-id="1c046-210">要素の検査</span><span class="sxs-lookup"><span data-stu-id="1c046-210">Inspecting an element with</span></span> `inspect()`  
> ![検査 () での要素の検査][ImageInspectElement]  

<span data-ttu-id="1c046-212">検査するメソッドを渡すとき、メソッドは**ソース**パネルでドキュメントを開き、調べることができます。</span><span class="sxs-lookup"><span data-stu-id="1c046-212">When passing a method to inspect, the method opens the document up in the **Sources** panel for you to inspect.</span></span>  

## <span data-ttu-id="1c046-213">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="1c046-213">getEventListeners</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="1c046-214">指定したオブジェクトに登録されているイベントリスナーを返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-214">Returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="1c046-215">戻り値は、登録されている各イベントの種類 (やなど) の配列を含むオブジェクトです `click` `keydown` 。</span><span class="sxs-lookup"><span data-stu-id="1c046-215">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="1c046-216">各配列のメンバーは、各型に登録されているリスナーを記述するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="1c046-216">The members of each array are objects that describe the listener registered for each type.</span></span>  <span data-ttu-id="1c046-217">[図 16](#figure-16)では、ドキュメントオブジェクトに登録されているすべてのイベントリスナーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-217">In [Figure 16](#figure-16), all of the event listeners registered on the document object are listed.</span></span>  

```console
getEventListeners(document);
```  

> ##### <span data-ttu-id="1c046-218">図 16</span><span class="sxs-lookup"><span data-stu-id="1c046-218">Figure 16</span></span>  
> <span data-ttu-id="1c046-219">を使用した出力</span><span class="sxs-lookup"><span data-stu-id="1c046-219">Output of using</span></span> `getEventListeners(document)`  
> ![GetEventListeners を使った出力 (ドキュメント)][ImageGetListeners]  

<span data-ttu-id="1c046-221">指定したオブジェクトに複数のリスナーが登録されている場合、この配列には各リスナーのメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c046-221">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="1c046-222">[図 16](#figure-16)では、イベントのドキュメント要素に2つのイベントリスナーが登録されてい `click` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-222">In [Figure 16](#figure-16), there are two event listeners registered on the document element for the `click` event.</span></span>  

> ##### <span data-ttu-id="1c046-223">図 17</span><span class="sxs-lookup"><span data-stu-id="1c046-223">Figure 17</span></span>  
> <span data-ttu-id="1c046-224">複数のリスナー</span><span class="sxs-lookup"><span data-stu-id="1c046-224">Multiple listeners</span></span>  
> ![複数のリスナー][ImageMultipleListeners]  

<span data-ttu-id="1c046-226">次の各オブジェクトをさらに拡張して、プロパティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1c046-226">You may further expand each of the following objects to explore the properties.</span></span>  

> ##### <span data-ttu-id="1c046-227">図18</span><span class="sxs-lookup"><span data-stu-id="1c046-227">Figure 18</span></span>  
> <span data-ttu-id="1c046-228">リスナーオブジェクトの展開ビュー</span><span class="sxs-lookup"><span data-stu-id="1c046-228">Expanded view of listener object</span></span>  
> ![リスナーオブジェクトの展開ビュー][ImageListenersExpanded]  

## <span data-ttu-id="1c046-230">キー</span><span class="sxs-lookup"><span data-stu-id="1c046-230">keys</span></span>  

```console
keys(object)
```  

<span data-ttu-id="1c046-231">指定したオブジェクトに属するプロパティの名前を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-231">Returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="1c046-232">同じプロパティの関連する値を取得するには、を使用 `values()` します。</span><span class="sxs-lookup"><span data-stu-id="1c046-232">To get the associated values of the same properties, use `values()`.</span></span>  

<span data-ttu-id="1c046-233">たとえば、アプリケーションが次のオブジェクトを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="1c046-233">For example, suppose your application defined the following object.</span></span>  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

<span data-ttu-id="1c046-234">[図 19](#figure-19)では、 `player1` 入力と本体の入力前のグローバル名前空間 \ (簡潔さ) で結果が定義されていることを前提としてい `keys(player1)` `values(player1)` ます。</span><span class="sxs-lookup"><span data-stu-id="1c046-234">In [Figure 19](#figure-19), the result assumes `player1` was defined in the global namespace \(for simplicity\) prior to typing `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)
```  

```console
values(player1)
```  

> ##### <span data-ttu-id="1c046-235">図19</span><span class="sxs-lookup"><span data-stu-id="1c046-235">Figure 19</span></span>  
> <span data-ttu-id="1c046-236">`keys()`And `values()` コマンド</span><span class="sxs-lookup"><span data-stu-id="1c046-236">The `keys()` and `values()` commands</span></span>  
> ![Keys () コマンドと values () コマンド][ImageConsoleKeysValues]  

## <span data-ttu-id="1c046-238">モニター</span><span class="sxs-lookup"><span data-stu-id="1c046-238">monitor</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="1c046-239">メソッドが呼び出されたときにメソッドに渡された引数と共に、メソッド名を示すメッセージをコンソールに記録します。</span><span class="sxs-lookup"><span data-stu-id="1c046-239">Logs a message to the console that indicates the method name along with the arguments that are passed to the method when it was called.</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

> ##### <span data-ttu-id="1c046-240">図20</span><span class="sxs-lookup"><span data-stu-id="1c046-240">Figure 20</span></span>  
> <span data-ttu-id="1c046-241">`monitor()`メソッド</span><span class="sxs-lookup"><span data-stu-id="1c046-241">The `monitor()` method</span></span>  
> ![Monitor () メソッド][ImageConsoleMonitorSum]  

<span data-ttu-id="1c046-243">`unmonitor(method)`監視を停止するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1c046-243">Use `unmonitor(method)` to cease monitoring.</span></span>  

## <span data-ttu-id="1c046-244">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="1c046-244">monitorEvents</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="1c046-245">指定したイベントのいずれかが指定したオブジェクトで発生した場合、イベントオブジェクトは本体に記録されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-245">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="1c046-246">監視する1つのイベント、一連のイベント、または定義済みのイベントコレクションにマップされる汎用イベント型のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1c046-246">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  <span data-ttu-id="1c046-247">[図 21](#figure-21)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c046-247">See [Figure 21](#figure-21).</span></span>  

<span data-ttu-id="1c046-248">次のモニターは、window オブジェクトのすべてのサイズ変更イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="1c046-248">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

> ##### <span data-ttu-id="1c046-249">図21</span><span class="sxs-lookup"><span data-stu-id="1c046-249">Figure 21</span></span>  
> <span data-ttu-id="1c046-250">モニタリングウィンドウのサイズ変更イベント</span><span class="sxs-lookup"><span data-stu-id="1c046-250">Monitoring window resize events</span></span>  
> ![モニタリングウィンドウのサイズ変更イベント][ImageMonitorResize]  

<span data-ttu-id="1c046-252">次の例では、window オブジェクトの両方のイベントとイベントを監視する配列を定義して `resize` `scroll` います。</span><span class="sxs-lookup"><span data-stu-id="1c046-252">The following defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="1c046-253">また、使用可能なイベントの種類のいずれかを指定することもできます。これは、事前定義された一連のイベントにマップされる文字列です。</span><span class="sxs-lookup"><span data-stu-id="1c046-253">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="1c046-254">以下の表に、利用可能なイベントの種類と関連付けられているイベントマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-254">The table below displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="1c046-255">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="1c046-255">Event type</span></span> | <span data-ttu-id="1c046-256">対応するマップされたイベント</span><span class="sxs-lookup"><span data-stu-id="1c046-256">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="1c046-257">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mousewheel"、"mouseup"、""</span><span class="sxs-lookup"><span data-stu-id="1c046-257">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="1c046-258">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="1c046-258">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="1c046-259">"touchcancel", "touchend", "touchmove", "touchstart"</span><span class="sxs-lookup"><span data-stu-id="1c046-259">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="1c046-260">"ぼかし"、"変更"、"フォーカス"、"リセット"、"サイズ変更"、"スクロール"、"選択"、"送信"、"ズーム"</span><span class="sxs-lookup"><span data-stu-id="1c046-260">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="1c046-261">[図 22](#figure-22)では、 `key` 入力テキストフィールドのイベントに対応するイベントの種類が、[ `key` **要素**] パネルで現在選択されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-261">In [Figure 22](#figure-22), the `key` event type corresponding to `key` events on an input text field are currently selected in the **Elements** panel.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="1c046-262">[図 22](#figure-22)では、テキストフィールドに文字を入力した後のサンプル出力が表示されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-262">In [Figure 22](#figure-22) the sample output after typing a character in the text field is displayed.</span></span>  

> ##### <span data-ttu-id="1c046-263">図22</span><span class="sxs-lookup"><span data-stu-id="1c046-263">Figure 22</span></span>  
> <span data-ttu-id="1c046-264">主要イベントの監視</span><span class="sxs-lookup"><span data-stu-id="1c046-264">Monitoring key events</span></span>  
> ![主要イベントの監視][ImageMonitorKey]  

## <span data-ttu-id="1c046-266">profile</span><span class="sxs-lookup"><span data-stu-id="1c046-266">profile</span></span>  

```console
profile([name])
```  

<span data-ttu-id="1c046-267">省略可能な名前で JavaScript CPU プロファイリングセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1c046-267">Starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="1c046-268">Profile [end ()](#profileend)メソッドは、プロファイルを完了し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-268">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** panel.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="1c046-269">メソッドを実行して `profile()` プロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="1c046-269">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="1c046-270">プロファイルを停止して、**メモリ**パネルに結果を表示するには、 [profileend ()](#profileend)メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c046-270">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** panel.</span></span>  

<span data-ttu-id="1c046-271">プロファイルは入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c046-271">Profiles may also be nested.</span></span>  <span data-ttu-id="1c046-272">[図 23](#figure-23)では、結果は順序に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="1c046-272">In [Figure 23](#figure-23) the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="1c046-273">複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1c046-273">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="1c046-274">profileEnd</span><span class="sxs-lookup"><span data-stu-id="1c046-274">profileEnd</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="1c046-275">JavaScript CPU のプロファイリングセッションを完了し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-275">Completes a JavaScript CPU profiling session and displays the results in the **Memory** panel.</span></span>  <span data-ttu-id="1c046-276">[Profile ()](#profile)メソッドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c046-276">You must be running the [profile()](#profile) method.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="1c046-277">[Profile ()](#profile)メソッドを実行してプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="1c046-277">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="1c046-278">メソッドを実行して `profileEnd()` プロファイリングを停止し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="1c046-278">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** panel.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="1c046-279">プロファイルは入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c046-279">Profiles may also be nested.</span></span>  <span data-ttu-id="1c046-280">[図 23](#figure-23)では、結果は順序に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="1c046-280">In [Figure 23](#figure-23) the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="1c046-281">結果は、**メモリ**パネルにヒープスナップショットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-281">The result appears as a Heap Snapshot in the **Memory** panel.</span></span>  

> ##### <span data-ttu-id="1c046-282">図23</span><span class="sxs-lookup"><span data-stu-id="1c046-282">Figure 23</span></span>  
> <span data-ttu-id="1c046-283">グループ化されたプロファイル</span><span class="sxs-lookup"><span data-stu-id="1c046-283">Grouped profiles</span></span>  
> ![グループ化されたプロファイル][ImageGroupedProfiles]  

> [!NOTE]
> <span data-ttu-id="1c046-285">複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1c046-285">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="1c046-286">'95'5c</span><span class="sxs-lookup"><span data-stu-id="1c046-286">table</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="1c046-287">列見出しを省略できるデータオブジェクトに基づいて、テーブルの書式設定でオブジェクトデータをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="1c046-287">Logs object data with table formatting based upon the data object in with optional column headings.</span></span>  <span data-ttu-id="1c046-288">[図 24](#figure-24)では、コンソールの表を使って名前のリストが表示されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-288">In [Figure 24](#figure-24), a list of names using a table in the console is displayed.</span></span>  

```console
var names = {
    0:  {
        firstName:  "John",
        lastName:  "Smith"
    },
    1:  {
        firstName:  "Jane",
        lastName:  "Doe"
    }
};
table(names);
```  

> ##### <span data-ttu-id="1c046-289">図24</span><span class="sxs-lookup"><span data-stu-id="1c046-289">Figure 24</span></span>  
> <span data-ttu-id="1c046-290">`table()`メソッド</span><span class="sxs-lookup"><span data-stu-id="1c046-290">The `table()` method</span></span>  
> ![Table () メソッド][ImageConsoleTable]  

## <span data-ttu-id="1c046-292">undebug</span><span class="sxs-lookup"><span data-stu-id="1c046-292">undebug</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="1c046-293">メソッドが呼び出されたときにデバッガーが呼び出されなくなるように、指定されたメソッドのデバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="1c046-293">Stops the debugging of the specified method so that when the method is called, the debugger is no longer invoked.</span></span>  

```console
undebug(getData);
```  

## <span data-ttu-id="1c046-294">未停止</span><span class="sxs-lookup"><span data-stu-id="1c046-294">unmonitor</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="1c046-295">指定したメソッドの監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="1c046-295">Stops the monitoring of the specified method.</span></span>  <span data-ttu-id="1c046-296">これは、 [monitor ()](#monitor)メソッドと連携して使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-296">This is used in concert with the [monitor()](#monitor) method.</span></span>  

```console
unmonitor(getData);
```  

## <span data-ttu-id="1c046-297">イベントを監視しない</span><span class="sxs-lookup"><span data-stu-id="1c046-297">unmonitorEvents</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="1c046-298">指定したオブジェクトおよびイベントの監視イベントを停止します。</span><span class="sxs-lookup"><span data-stu-id="1c046-298">Stops monitoring events for the specified object and events.</span></span>  <span data-ttu-id="1c046-299">たとえば、次の例では、window オブジェクトのイベント監視がすべて停止しています。</span><span class="sxs-lookup"><span data-stu-id="1c046-299">For example, the following stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="1c046-300">オブジェクトの特定のイベントの監視を選択的に停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c046-300">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="1c046-301">たとえば、次のコードでは、現在選択されている要素のすべての `mouse` イベントを監視し、イベントの監視を停止します (多くの場合、 `mousemove` 本体の出力のノイズを軽減します)。</span><span class="sxs-lookup"><span data-stu-id="1c046-301">For example, the following code starts monitoring all `mouse` events on the currently selected element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <span data-ttu-id="1c046-302">values</span><span class="sxs-lookup"><span data-stu-id="1c046-302">values</span></span>  

```console
values(object)
```  

<span data-ttu-id="1c046-303">指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="1c046-303">Returns an array containing the values of all properties belonging to the specified object.</span></span>  

```console
values(object);
```  

<!--   -->  



<!-- image links -->  

[ImageRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-arithmatic.msft.png "図 1: $ _ は、最近評価された式です。"  
[ImageChangedRecentExpression]: /microsoft-edge/devtools-guide-chromium/media/console-array-length.msft.png "図 2: 新しいコマンドが評価されたときの $ _ の変更"  
[ImageElement0]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$0.msft.png "図 3: $0"  
[ImageElement1]: /microsoft-edge/devtools-guide-chromium/media/console-image-highlighted-$1.msft.png "図 4: $1"  
[ImageElementImg]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image.msft.png "図 5: $ (' img ')"  
[ImageElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-source.msft.png "図 6: $ (' img ') src"  
[ImageElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-source.msft.png "図 7: $ (' img '、ドキュメントの querySelector (' title--image '))。 src"  
[ImageArrayElementImgSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-all.msft.png "図 8: $ $ () を使用してドキュメント内のすべての画像を選択し、ソースを表示する"  
[ImageArrayElementImgNodeSource]: /microsoft-edge/devtools-guide-chromium/media/console-element-selector-image-filter-all.msft.png "図 9: $ $ () を使って、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する"  
[ImageArrayXpath]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath.msft.png "図 10: XPath セレクターを使用する"  
[ImageArrayXpathChild]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-sub-element.msft.png "図 11: より複雑な XPath セレクターを使用する"  
[ImageArrayXpathNode]: /microsoft-edge/devtools-guide-chromium/media/console-array-xpath-startnode.msft.png "図 12: startNode で XPath セレクターを使用する"  
[ImageDebugMethod]: /microsoft-edge/devtools-guide-chromium/media/console-debug-text.msft.png "図 13: debug () を使用したメソッド内の中断"  
[ImageLogObject]: /microsoft-edge/devtools-guide-chromium/media/console-dir-document-head-expanded.msft.png "図 14: dir () メソッドを使った文書の記録"  
[ImageInspectElement]: /microsoft-edge/devtools-guide-chromium/media/console-inspect-document-body.msft.png "図 15: 検査 () を使って要素を検査する"  
[ImageGetListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document.msft.png "図 16: getEventListeners を使った出力 (ドキュメント)"  
[ImageMultipleListeners]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png "図 17: 複数のリスナー"  
[ImageListenersExpanded]: /microsoft-edge/devtools-guide-chromium/media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png "図 18: リスナーオブジェクトの展開ビュー"  
[ImageConsoleKeysValues]: /microsoft-edge/devtools-guide-chromium/media/console-keys-values.msft.png "図 19: keys () および values () コマンド"  
[ImageConsoleMonitorSum]: /microsoft-edge/devtools-guide-chromium/media/console-function-monitor-sum.msft.png "図 20: monitor () メソッド"  
[ImageMonitorResize]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-resize-window.msft.png "図 21: ウィンドウのサイズ変更イベントの監視"  
[ImageMonitorKey]: /microsoft-edge/devtools-guide-chromium/media/console-monitor-events-type-t-y.msft.png "図 22: 主要イベントの監視"  
[ImageGroupedProfiles]: /microsoft-edge/devtools-guide-chromium/media/console-memory-multiple-cpu-profiles.msft.png "図 23: グループ化されたプロファイル"  
[ImageConsoleTable]: /microsoft-edge/devtools-guide-chromium/media/console-table-display.msft.png "図 24: table () メソッド"  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "本体の API リファレンス"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir-本体の API リファレンス"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "JavaScript の実行時間を短縮する"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console. dir () |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console. dirxml () |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "ドキュメントの querySelector () |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "QuerySelectorAll () |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "問題 1050237: debug (関数) が機能しません |Monorail アウト"  

> [!NOTE]
> <span data-ttu-id="1c046-337">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c046-337">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1c046-338">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-338">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1c046-340">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1c046-340">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
