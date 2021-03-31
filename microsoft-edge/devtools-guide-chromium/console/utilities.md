---
description: Microsoft Edge DevTools コンソールで使用できる便利なコマンドの参照。
title: コンソール ユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e7253bf5402a03d1659f56ba083bb87e93b3af38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398827"
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

# <a name="console-utilities-api-reference"></a><span data-ttu-id="2303d-104">コンソール ユーティリティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="2303d-104">Console Utilities API reference</span></span>  

<span data-ttu-id="2303d-105">コンソール ユーティリティ API には、DOM 要素の選択と検査、読み取り可能な形式でのデータの表示、プロファイラーの停止と開始、DOM イベントの監視など、一般的なタスクを実行するための便利なコマンドのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2303d-105">The Console Utilities API contains a collection of convenience commands for performing common tasks:  selecting and inspecting DOM elements, displaying data in readable format, stopping and starting the profiler, and monitoring DOM events.</span></span>  

> [!WARNING]
> <span data-ttu-id="2303d-106">次のコマンドは、Microsoft Edge DevTools コンソールでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2303d-106">The following commands only work in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="2303d-107">スクリプトから実行すると、コマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="2303d-107">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="2303d-108">メソッドと `console.log()` メソッド `console.error()` の残りの部分については、[コンソール API リファレンス] `console.*` [に移動します][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="2303d-108">For the `console.log()` and `console.error()` methods the rest of the `console.*` methods, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  

## <a name="recently-evaluated-expression"></a><span data-ttu-id="2303d-109">最近評価された式</span><span class="sxs-lookup"><span data-stu-id="2303d-109">Recently Evaluated Expression</span></span>  

```console
$_
```  

<span data-ttu-id="2303d-110">最近評価された式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-110">Returns the value of the most recently evaluated expression.</span></span>  

<span data-ttu-id="2303d-111">次の図では、単純な式 \( `2 + 2` \) が評価されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-111">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="2303d-112">その `$_` 後、同じ値を含むプロパティが評価されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-112">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ は、最近評価された式です。" lightbox="../media/console-arithmatic.msft.png":::
   <span data-ttu-id="2303d-114">図 1:  `$_` 最も最近評価された式</span><span class="sxs-lookup"><span data-stu-id="2303d-114">Figure 1:  `$_` is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-115">次の図では、評価された式には最初に名前の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2303d-115">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="2303d-116">配列の長さを見つけるために評価すると、変更に格納された値が最新の評価式 `$_.length` `$_` になります `4` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-116">Evaluating `$_.length` to find the length of the array, the value stored in `$_` changes to become the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$しいコマンドが評価される場合の $_ の変更" lightbox="../media/console-array-length.msft.png":::
   <span data-ttu-id="2303d-118">図 2:  `$_` 新しいコマンドが評価される場合の変更点</span><span class="sxs-lookup"><span data-stu-id="2303d-118">Figure 2:  `$_` changes when new commands are evaluated</span></span>  
:::image-end:::  

## <a name="recently-chosen-element-or-javascript-object"></a><span data-ttu-id="2303d-119">最近選択した要素または JavaScript オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2303d-119">Recently Chosen Element Or JavaScript Object</span></span>  

```console
$0
```  

<span data-ttu-id="2303d-120">最近選択した要素または JavaScript オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-120">Returns the most recently selected element or JavaScript object.</span></span>  `$1` <span data-ttu-id="2303d-121">2 番目に最近選択した 1 つを返します。などです。</span><span class="sxs-lookup"><span data-stu-id="2303d-121">returns the second most recently selected one, and so on.</span></span>  <span data-ttu-id="2303d-122">、 、 、 、およびコマンドは、Elements ツール内で検査された最後の 5 つの DOM 要素、またはメモリ ツールで選択された最後の 5 つの JavaScript ヒープ オブジェクトへの履歴参照として `$0` `$1` `$2` `$3` `$4` **機能**します。 </span><span class="sxs-lookup"><span data-stu-id="2303d-122">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** tool or the last five JavaScript heap objects selected in the **Memory** tool.</span></span>  

:::row:::
   :::column span="1":::
      ```console
      $0
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $1
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $2
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ```console
      $3
      ```  
   :::column-end:::
   :::column span="1":::
      ```console
      $4
      ```  
   :::column-end:::
   :::column span="1":::
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2303d-123">次の図では、要素 `img` ツールで要素が **選択** されています。</span><span class="sxs-lookup"><span data-stu-id="2303d-123">In the following figure, an `img` element is selected in the **Elements** tool.</span></span>  <span data-ttu-id="2303d-124">コンソール ドロ **ワーで** 、 `$0` 評価され、同じ要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-124">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="2303d-126">図 3:</span><span class="sxs-lookup"><span data-stu-id="2303d-126">Figure 3:  The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="2303d-127">次の図では、同じページで選択されている別の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2303d-127">In the following figure, the image shows a different element selected in the same page.</span></span>  <span data-ttu-id="2303d-128">ここで `$0` 、新しく選択した要素を参照し、前に選択した要素 `$1` を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-128">The `$0` now refers to the newly selected element, while `$1` returns the previously selected one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="2303d-130">図 4:</span><span class="sxs-lookup"><span data-stu-id="2303d-130">Figure 4:  The</span></span> `$1`  
:::image-end:::  

## <a name="query-selector"></a><span data-ttu-id="2303d-131">クエリ セレクター</span><span class="sxs-lookup"><span data-stu-id="2303d-131">Query Selector</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="2303d-132">指定した CSS セレクターを持つ最初の DOM 要素への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-132">Returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="2303d-133">このメソッドは [、document.querySelector() メソッドのエイリアス][MDNDocumentQuerySelector] です。</span><span class="sxs-lookup"><span data-stu-id="2303d-133">This method is an alias for the [document.querySelector()][MDNDocumentQuerySelector] method.</span></span>  

<span data-ttu-id="2303d-134">次の図では、ドキュメントの最初の `<img>` 要素への参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-134">In the following figure, a reference to the first `<img>` element in the document is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$('img')" lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="2303d-136">図 5:</span><span class="sxs-lookup"><span data-stu-id="2303d-136">Figure 5:  The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="2303d-137">返された結果にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[要素パネルで表示]を選択してDOM で検索するか、[表示] にスクロールしてページに表示します。</span><span class="sxs-lookup"><span data-stu-id="2303d-137">Hover on the returned result, open the contextual menu \(right-click\), and choose **Reveal in Elements Panel** to find it in the DOM or **Scroll in to View** to show it on the page.</span></span>  

<span data-ttu-id="2303d-138">次の図では、現在選択されている要素への参照が返され、src プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-138">In the following figure, a reference to the currently selected element is returned and the src property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$('img').src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="2303d-140">図 6:</span><span class="sxs-lookup"><span data-stu-id="2303d-140">Figure 6:  The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="2303d-141">このメソッドは、要素を検索する "要素" または Node を指定する 2 番目のパラメーター startNode もサポートします。</span><span class="sxs-lookup"><span data-stu-id="2303d-141">This method also supports a second parameter, startNode, that specifies an "element" or Node from which to search for elements.</span></span>  <span data-ttu-id="2303d-142">パラメーターの既定値はです `document` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-142">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="2303d-143">次の図では、最初の要素 `img` が見つかり、正 `title--image` しく表示 `src` されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-143">In the following figure, the first `img` element is found after the `title--image` and displays the `src` properly is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$('img', document.querySelector('title--image')).src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="2303d-145">図 7:</span><span class="sxs-lookup"><span data-stu-id="2303d-145">Figure 7:  The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="2303d-146">使用する jQuery などのライブラリを使用している場合、機能は上書きされ、そのライブラリの実装 `$` `$` に対応します。</span><span class="sxs-lookup"><span data-stu-id="2303d-146">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

## <a name="query-selector-all"></a><span data-ttu-id="2303d-147">クエリ セレクター すべて</span><span class="sxs-lookup"><span data-stu-id="2303d-147">Query Selector All</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="2303d-148">指定した CSS セレクターに一致する要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-148">Returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="2303d-149">このメソッドは [、document.querySelectorAll() メソッドの実行と同][MDNDocumentQuerySelectorAll] じです。</span><span class="sxs-lookup"><span data-stu-id="2303d-149">This method is equivalent to running the [document.querySelectorAll()][MDNDocumentQuerySelectorAll] method.</span></span>  

<span data-ttu-id="2303d-150">次のコード サンプルと図では、現在のドキュメント内のすべての要素の配列を作成し、各要素のプロパティの値 `$$()` `<img>` `src` を表示します。</span><span class="sxs-lookup"><span data-stu-id="2303d-150">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current document and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="$$() を使用してドキュメント内のすべての画像を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="2303d-152">図 8: 文書 `$$()` 内のすべての画像を選択し、ソースを表示する使用</span><span class="sxs-lookup"><span data-stu-id="2303d-152">Figure 8:  Using `$$()` to select all images in the document and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-153">このメソッドは、要素を検索する要素または Node を指定する 2 番目のパラメーター startNode もサポートします。</span><span class="sxs-lookup"><span data-stu-id="2303d-153">This method also supports a second parameter, startNode, that specifies an element or Node from which to search for elements.</span></span>  <span data-ttu-id="2303d-154">パラメーターの既定値はです `document` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-154">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="2303d-155">次のコード サンプルと図では、前のコード サンプルと図の変更バージョンを使用して、選択したノードの後に現在のドキュメントに表示されるすべての要素の配列 `$$()` `<img>` を作成します。</span><span class="sxs-lookup"><span data-stu-id="2303d-155">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current document after the selected Node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="$$() を使用して、指定した div <の後に表示>を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="2303d-157">図 9: 文書内の指定された要素の後に表示される画像を選択し、ソース `$$()` `<div>` を表示する場合に使用する</span><span class="sxs-lookup"><span data-stu-id="2303d-157">Figure 9:  Using `$$()` to select all images that appear after the specified `<div>` element in the document and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="2303d-158">スクリプト `Shift` + `Enter` を実行せずに新しい行を開始するには、コンソールで選択します。</span><span class="sxs-lookup"><span data-stu-id="2303d-158">Select `Shift`+`Enter` in the console to start a new line without running the script.</span></span>  

## <a name="xpath"></a><span data-ttu-id="2303d-159">XPath</span><span class="sxs-lookup"><span data-stu-id="2303d-159">XPath</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="2303d-160">指定した XPath 式に一致する DOM 要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-160">Returns an array of DOM elements that match the specified XPath expression.</span></span>  

<span data-ttu-id="2303d-161">次のコード サンプルと図では、ページ上のすべての要素 `<p>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-161">In the following code sample and figure, all of the `<p>` elements on the page are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="XPath セレクターの使用" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="2303d-163">図 10: XPath セレクターの使用</span><span class="sxs-lookup"><span data-stu-id="2303d-163">Figure 10:  Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-164">次のコード サンプルと図では、要素を含む `<p>` すべての要素 `<a>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-164">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="より複雑な XPath セレクターの使用" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="2303d-166">図 11: より複雑な XPath セレクターの使用</span><span class="sxs-lookup"><span data-stu-id="2303d-166">Figure 11:  Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-167">他のセレクター コマンドと同様に、要素を検索する要素または Node を指定するオプションの 2 番目の `$x(path)` `startNode` パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="2303d-167">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or Node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="startNode で XPath セレクターを使用する" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="2303d-169">図 12: XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="2303d-169">Figure 12:  Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

## <a name="clear"></a><span data-ttu-id="2303d-170">clear</span><span class="sxs-lookup"><span data-stu-id="2303d-170">clear</span></span>  

```console
clear()
```  

<span data-ttu-id="2303d-171">履歴のコンソールをクリアします。</span><span class="sxs-lookup"><span data-stu-id="2303d-171">Clears the console of the history.</span></span>  

```console
clear()
```  

## <a name="copy"></a><span data-ttu-id="2303d-172">copy</span><span class="sxs-lookup"><span data-stu-id="2303d-172">copy</span></span>  

```console
copy(object)
```  

<span data-ttu-id="2303d-173">この `copy(object)` メソッドは、指定したオブジェクトの文字列表現をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2303d-173">The `copy(object)` method copies a string representation of the specified object to the clipboard.</span></span>  

```console
copy($0)
```  

## <a name="debug"></a><span data-ttu-id="2303d-174">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2303d-174">debug</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="2303d-175">クロム [の問題#1050237][MonorailIssue1050237] 関数のバグを追跡 `debug()` しています。</span><span class="sxs-lookup"><span data-stu-id="2303d-175">The [Chromium issue #1050237][MonorailIssue1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="2303d-176">問題が発生した場合は、代 [わりにブレークポイントを使用][DevtoolsJavascriptBreakpoints] してみてください。</span><span class="sxs-lookup"><span data-stu-id="2303d-176">If you encounter the issue, try [using breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="2303d-177">指定したメソッドを要求すると、デバッガーが呼び出され、ソース ツールの メソッド内でブレークされ、コードをステップ実行してデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="2303d-177">When you request the specified method, the debugger is invoked and breaks inside the method on the **Sources** tool allowing you to step through the code and debug it.</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="debug() を使用してメソッド内でブレークする" lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="2303d-179">図 13: メソッド内でのブレーク</span><span class="sxs-lookup"><span data-stu-id="2303d-179">Figure 13:  Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="2303d-180">メソッド `undebug(method)` のブレークを停止したり、UI を使用してすべてのブレークポイントを無効にしたりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="2303d-180">Use `undebug(method)` to stop breaking on the method, or use the UI to disable all breakpoints.</span></span>  

<span data-ttu-id="2303d-181">ブレークポイントの詳細については、「ブレークポイントを使用してコード [を一時停止する」に移動します][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="2303d-181">For more information on breakpoints, navigate to [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <a name="dir"></a><span data-ttu-id="2303d-182">dir</span><span class="sxs-lookup"><span data-stu-id="2303d-182">dir</span></span>  

```console
dir(object)
```  

<span data-ttu-id="2303d-183">指定したオブジェクトのすべてのプロパティのオブジェクト スタイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="2303d-183">Displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="2303d-184">このメソッドは [console.dir() メソッドのエイリアス][MDNConsoleDir] です。</span><span class="sxs-lookup"><span data-stu-id="2303d-184">This method is an alias for the [console.dir()][MDNConsoleDir] method.</span></span>  

<span data-ttu-id="2303d-185">コンソール `document.head` で評価し、タグとタグの間に HTML `<head>` を表示 `</head>` します。</span><span class="sxs-lookup"><span data-stu-id="2303d-185">Evaluate `document.head` in the Console to display the HTML between the `<head>` and `</head>` tags.</span></span>  <span data-ttu-id="2303d-186">次のコード サンプルと図では、コンソールで使用した後にオブジェクト スタイルの一覧 `console.dir()` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-186">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the Console.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="dir() メソッドを使用して document.head をログに記録する" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="2303d-188">図 14: メソッドによる `document.head` `dir()` ログ記録</span><span class="sxs-lookup"><span data-stu-id="2303d-188">Figure 14:  Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-189">詳細については、コンソール [`console.dir()`][DevToolsConsoleApiConsoleDirObject] API のエントリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2303d-189">For more information, navigate to [`console.dir()`][DevToolsConsoleApiConsoleDirObject] entry in the Console API.</span></span>  

## <a name="dirxml"></a><span data-ttu-id="2303d-190">dirxml</span><span class="sxs-lookup"><span data-stu-id="2303d-190">dirxml</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="2303d-191">要素ツールに表示される、指定したオブジェクトの XML 表現を **印刷** します。</span><span class="sxs-lookup"><span data-stu-id="2303d-191">Prints an XML representation of the specified object, as displayed in the **Elements** tool.</span></span>  <span data-ttu-id="2303d-192">このメソッドは [console.dirxml() メソッドと同][MDNConsoleDirxml] じです。</span><span class="sxs-lookup"><span data-stu-id="2303d-192">This method is equivalent to the [console.dirxml()][MDNConsoleDirxml] method.</span></span>  

## <a name="inspect"></a><span data-ttu-id="2303d-193">検査</span><span class="sxs-lookup"><span data-stu-id="2303d-193">inspect</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="2303d-194">適切なパネルで、指定した要素またはオブジェクト (DOM 要素の 要素ツールまたは JavaScript ヒープ オブジェクトのメモリ ツール) を開いて選択します。</span><span class="sxs-lookup"><span data-stu-id="2303d-194">Opens and selects the specified element or object in the appropriate panel:  either the **Elements** tool for DOM elements or the **Memory** tool for JavaScript heap objects.</span></span>  

<span data-ttu-id="2303d-195">次のコード サンプルと図では、要素 `document.body` ツールで **開** きます。</span><span class="sxs-lookup"><span data-stu-id="2303d-195">In the following code sample and figure, the `document.body` opens in the **Elements** tool.</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="inspect() を使用して要素を検査する" lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="2303d-197">図 15: で要素を検査する</span><span class="sxs-lookup"><span data-stu-id="2303d-197">Figure 15:  Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="2303d-198">検査するメソッドを渡す場合、メソッドは[ソース] ツールでドキュメントを開き、検査を行います。</span><span class="sxs-lookup"><span data-stu-id="2303d-198">When passing a method to inspect, the method opens the document in the **Sources** tool for you to inspect.</span></span>  

## <a name="geteventlisteners"></a><span data-ttu-id="2303d-199">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="2303d-199">getEventListeners</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="2303d-200">指定したオブジェクトに登録されているイベント リスナーを返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-200">Returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="2303d-201">戻り値は、登録されているイベントの種類 \(または \など) ごとに配列を含む `click` オブジェクト `keydown` です。</span><span class="sxs-lookup"><span data-stu-id="2303d-201">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="2303d-202">各配列のメンバーは、各型に登録されているリスナーを表すオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="2303d-202">The members of each array are objects that describe the listener registered for each type.</span></span>  <span data-ttu-id="2303d-203">次のコード サンプルの図では、ドキュメント オブジェクトに登録されているイベント リスナーのすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-203">In the following code sample figure, all of the event listeners registered on the document object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="getEventListeners(document) の使用の出力" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="2303d-205">図 16: 使用の結果</span><span class="sxs-lookup"><span data-stu-id="2303d-205">Figure 16:  The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="2303d-206">指定したオブジェクトに複数のリスナーが登録されている場合、配列にはリスナーごとにメンバーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="2303d-206">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="2303d-207">次の図では、イベントの document 要素に 2 つのイベント リスナーが登録 `click` されています。</span><span class="sxs-lookup"><span data-stu-id="2303d-207">In the following figure, there are two event listeners registered on the document element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="複数のリスナー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="2303d-209">図 17: 複数のリスナー</span><span class="sxs-lookup"><span data-stu-id="2303d-209">Figure 17:  Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-210">次の各オブジェクトをさらに展開して、プロパティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2303d-210">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="リスナー オブジェクトの拡張ビュー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="2303d-212">図 18: リスナー オブジェクトの拡張ビュー</span><span class="sxs-lookup"><span data-stu-id="2303d-212">Figure 18:  Expanded view of listener object</span></span>  
:::image-end:::  

## <a name="keys"></a><span data-ttu-id="2303d-213">キー</span><span class="sxs-lookup"><span data-stu-id="2303d-213">keys</span></span>  

```console
keys(object)
```  

<span data-ttu-id="2303d-214">指定したオブジェクトに属するプロパティの名前を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-214">Returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="2303d-215">同じプロパティの関連する値を取得するには、 を使用します `values()` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-215">To get the associated values of the same properties, use `values()`.</span></span>  

<span data-ttu-id="2303d-216">たとえば、アプリケーションが次のオブジェクトを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="2303d-216">For example, suppose your application defined the following object.</span></span>  

```console
var player1 =   
```  

<span data-ttu-id="2303d-217">次のコード サンプルと図では、入力する前とコンソールでグローバル名前空間 \(簡易\) で定義されたと `player1` `keys(player1)` `values(player1)` 仮定します。</span><span class="sxs-lookup"><span data-stu-id="2303d-217">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) prior to typing `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="keys() コマンドと values() コマンド" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="2303d-219">図 19: `keys()` and `values()` コマンド</span><span class="sxs-lookup"><span data-stu-id="2303d-219">Figure 19:  The `keys()` and `values()` commands</span></span>  
:::image-end:::  

## <a name="monitor"></a><span data-ttu-id="2303d-220">モニター</span><span class="sxs-lookup"><span data-stu-id="2303d-220">monitor</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="2303d-221">呼び出されたメソッドに渡される引数と共に、メソッド名を示すメッセージをコンソールにログに記録します。</span><span class="sxs-lookup"><span data-stu-id="2303d-221">Logs a message to the console that indicates the method name along with the arguments that are passed to the method when it was called.</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="monitor() メソッド" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="2303d-223">図 20: `monitor()` メソッド</span><span class="sxs-lookup"><span data-stu-id="2303d-223">Figure 20:  The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-224">監視 `unmonitor(method)` を停止するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2303d-224">Use `unmonitor(method)` to cease monitoring.</span></span>  

## <a name="monitorevents"></a><span data-ttu-id="2303d-225">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="2303d-225">monitorEvents</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="2303d-226">指定したオブジェクトで指定されたイベントの 1 つが発生すると、イベント オブジェクトはコンソールに記録されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-226">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="2303d-227">監視する 1 つのイベント、イベントの配列、または定義済みのイベント のコレクションにマップされる一般的なイベントの種類のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2303d-227">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  <span data-ttu-id="2303d-228">次のコード サンプルと図を確認します。</span><span class="sxs-lookup"><span data-stu-id="2303d-228">Review the following code sample and figure.</span></span>  

<span data-ttu-id="2303d-229">次に、window オブジェクト上のすべてのサイズ変更イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="2303d-229">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="ウィンドウのサイズ変更イベントの監視" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="2303d-231">図 21: 監視ウィンドウのサイズ変更イベント</span><span class="sxs-lookup"><span data-stu-id="2303d-231">Figure 21:  Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="2303d-232">次に、window オブジェクトの両方とイベントを監視 `resize` `scroll` する配列を定義します。</span><span class="sxs-lookup"><span data-stu-id="2303d-232">The following defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="2303d-233">使用可能なイベントの種類の 1 つ、定義済みのイベント セットにマップする文字列を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2303d-233">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="2303d-234">次の表に、使用可能なイベントの種類と関連付けられたイベント マッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="2303d-234">The following table displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="2303d-235">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="2303d-235">Event type</span></span> | <span data-ttu-id="2303d-236">対応するマップされたイベント</span><span class="sxs-lookup"><span data-stu-id="2303d-236">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="2303d-237">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel"</span><span class="sxs-lookup"><span data-stu-id="2303d-237">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="2303d-238">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="2303d-238">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="2303d-239">"touchcancel", "touchend", "touchmove", "touchstart"</span><span class="sxs-lookup"><span data-stu-id="2303d-239">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="2303d-240">"ぼかし"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom"</span><span class="sxs-lookup"><span data-stu-id="2303d-240">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="2303d-241">次のコード サンプルでは、入力テキスト フィールドのイベントに対応するイベントの種類が現在、要素 `key` `key` ツールで **選択** されています。</span><span class="sxs-lookup"><span data-stu-id="2303d-241">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently selected in the **Elements** tool.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="2303d-242">次の図では、テキスト フィールドに文字を入力した後の出力例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-242">In the following figure the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="主要なイベントの監視" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="2303d-244">図 22: キー イベントの監視</span><span class="sxs-lookup"><span data-stu-id="2303d-244">Figure 22:  Monitoring key events</span></span>  
:::image-end:::  

## <a name="profile"></a><span data-ttu-id="2303d-245">profile</span><span class="sxs-lookup"><span data-stu-id="2303d-245">profile</span></span>  

```console
profile([name])
```  

<span data-ttu-id="2303d-246">オプションの名前で JavaScript CPU プロファイリング セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="2303d-246">Starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="2303d-247">[profileEnd() メソッドは](#profileend)プロファイルを完了し、結果を Memory ツールに**表示**します。</span><span class="sxs-lookup"><span data-stu-id="2303d-247">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** tool.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="2303d-248">プロファイリングを `profile()` 開始するには、メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2303d-248">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="2303d-249">[profileEnd() メソッド](#profileend)を実行してプロファイリングを停止し、結果を Memory ツールに**表示**します。</span><span class="sxs-lookup"><span data-stu-id="2303d-249">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** tool.</span></span>  

<span data-ttu-id="2303d-250">プロファイルは入れ子にされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2303d-250">Profiles may also be nested.</span></span>  <span data-ttu-id="2303d-251">次のコード サンプルと図では、順序に関係なく結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="2303d-251">In the following code samples and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="2303d-252">複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2303d-252">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <a name="profileend"></a><span data-ttu-id="2303d-253">profileEnd</span><span class="sxs-lookup"><span data-stu-id="2303d-253">profileEnd</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="2303d-254">JavaScript CPU プロファイリング セッションを完了し、結果をメモリ ツールに **表示** します。</span><span class="sxs-lookup"><span data-stu-id="2303d-254">Completes a JavaScript CPU profiling session and displays the results in the **Memory** tool.</span></span>  <span data-ttu-id="2303d-255">[profile() メソッドを実行している必要](#profile)があります。</span><span class="sxs-lookup"><span data-stu-id="2303d-255">You must be running the [profile()](#profile) method.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="2303d-256">[profile() メソッドを実行](#profile)してプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="2303d-256">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="2303d-257">このメソッド `profileEnd()` を実行して、プロファイリングを停止し、結果をメモリ ツールに **表示** します。</span><span class="sxs-lookup"><span data-stu-id="2303d-257">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** tool.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="2303d-258">プロファイルは入れ子にされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2303d-258">Profiles may also be nested.</span></span>  <span data-ttu-id="2303d-259">次のコード サンプルと図では、順序に関係なく結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="2303d-259">In the following code sample and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="2303d-260">結果は、メモリ ツールのヒープ スナップショットとして **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-260">The result appears as a Heap Snapshot in the **Memory** tool.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="グループ化されたプロファイル" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="2303d-262">図 23: グループ化されたプロファイル</span><span class="sxs-lookup"><span data-stu-id="2303d-262">Figure 23:  Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="2303d-263">複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2303d-263">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <a name="queryobjects"></a><span data-ttu-id="2303d-264">queryObjects</span><span class="sxs-lookup"><span data-stu-id="2303d-264">queryObjects</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="2303d-265">指定したコンストラクターで作成されたオブジェクトの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-265">Return an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="2303d-266">スコープは `queryObjects()` 、コンソールで現在選択されているランタイム コンテキストです。</span><span class="sxs-lookup"><span data-stu-id="2303d-266">The scope of `queryObjects()` is the currently-selected runtime context in the console.</span></span>

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="2303d-267">all を返します `Promises` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-267">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="2303d-268">すべての HTML 要素を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-268">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="2303d-269">を使用してインスタンス化されたすべてのオブジェクトを返します `new functionName()` 。</span><span class="sxs-lookup"><span data-stu-id="2303d-269">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="2303d-270">table</span><span class="sxs-lookup"><span data-stu-id="2303d-270">table</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="2303d-271">オプションの列見出しを使用して、データ オブジェクトに基づいてテーブルの書式設定を使用してオブジェクト データをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="2303d-271">Logs object data with table formatting based upon the data object in with optional column headings.</span></span>  <span data-ttu-id="2303d-272">次のコード サンプルと図では、コンソール内のテーブルを使用する名前の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-272">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="table() メソッドの結果" lightbox="../media/console-table-display.msft.png":::
   <span data-ttu-id="2303d-274">図 24: メソッドの `table()` 結果</span><span class="sxs-lookup"><span data-stu-id="2303d-274">Figure 24:  The result of the `table()` method</span></span>  
:::image-end:::  

## <a name="undebug"></a><span data-ttu-id="2303d-275">undebug</span><span class="sxs-lookup"><span data-stu-id="2303d-275">undebug</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="2303d-276">指定したメソッドのデバッグを停止し、メソッドが呼び出されるとデバッガーが呼び出されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2303d-276">Stops the debugging of the specified method so that when the method is called, the debugger is no longer invoked.</span></span>  

```console
undebug(getData);
```  

## <a name="unmonitor"></a><span data-ttu-id="2303d-277">unmonitor</span><span class="sxs-lookup"><span data-stu-id="2303d-277">unmonitor</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="2303d-278">指定したメソッドの監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="2303d-278">Stops the monitoring of the specified method.</span></span>  <span data-ttu-id="2303d-279">このメソッドは monitor() メソッドと一 [緒に使用](#monitor) されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-279">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

```console
unmonitor(getData);
```  

## <a name="unmonitorevents"></a><span data-ttu-id="2303d-280">unmonitorEvents</span><span class="sxs-lookup"><span data-stu-id="2303d-280">unmonitorEvents</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="2303d-281">指定したオブジェクトとイベントの監視イベントを停止します。</span><span class="sxs-lookup"><span data-stu-id="2303d-281">Stops monitoring events for the specified object and events.</span></span>  <span data-ttu-id="2303d-282">たとえば、次の例では、window オブジェクト上のすべてのイベント監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="2303d-282">For example, the following stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="2303d-283">また、オブジェクトの特定のイベントの監視を選択的に停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="2303d-283">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="2303d-284">たとえば、次のコードは、現在選択されている要素のすべてのイベントの監視を開始し、イベントの監視を停止します \(コンソール出力のノイズを低減 `mouse` `mousemove` する場合があります\)。</span><span class="sxs-lookup"><span data-stu-id="2303d-284">For example, the following code starts monitoring all `mouse` events on the currently selected element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <a name="values"></a><span data-ttu-id="2303d-285">値</span><span class="sxs-lookup"><span data-stu-id="2303d-285">values</span></span>  

```console
values(object)
```  

<span data-ttu-id="2303d-286">指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2303d-286">Returns an array containing the values of all properties belonging to the specified object.</span></span>  

```console
values(object);
```  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="2303d-287">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="2303d-287">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "コンソール API リファレンス"  
[DevToolsConsoleApiConsoleDirObject]: /microsoft-edge/devtools-guide-chromium/console/api#dir "dir - コンソール API リファレンス"  
[DevToolsJavascriptBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints "Microsoft Edge DevTools でブレークポイントを使用してコードを一時停止する方法"  
[DevToolsRenderingToolsJSRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "JavaScript ランタイムの高速化"  

[MDNConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console.dir() |MDN"  
[MDNConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console.dirxml() |MDN"  
[MDNDocumentQuerySelector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "Document.querySelector() |MDN"  
[MDNDocumentQuerySelectorAll]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "Document.querySelectorAll() |MDN"  

[MonorailIssue1050237]: https://bugs.chromium.org/p/chromium/issues/detail?id=1050237 "問題 1050237: debug(function) が動作|モノレール"  

> [!NOTE]
> <span data-ttu-id="2303d-297">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="2303d-297">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2303d-298">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="2303d-298">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="2303d-300">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="2303d-300">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
