---
title: コンソールユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: efa03e02813d718514f73445bc0dceb3a1a83f39
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708853"
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

# <span data-ttu-id="7612a-103">コンソールユーティリティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="7612a-103">Console Utilities API Reference</span></span>  

<span data-ttu-id="7612a-104">コンソールユーティリティ API には、一般的なタスク (DOM 要素の選択と検査、読み取り可能な形式でのデータの表示、プロファイラーの停止と開始、DOM イベントの監視) を実行するための便利なコマンドのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7612a-104">The Console Utilities API contains a collection of convenience commands for performing common tasks:  selecting and inspecting DOM elements, displaying data in readable format, stopping and starting the profiler, and monitoring DOM events.</span></span>  

> [!WARNING]
> <span data-ttu-id="7612a-105">次のコマンドは、Microsoft Edge DevTools コンソールでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="7612a-105">The following commands only work in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="7612a-106">スクリプトから実行した場合、コマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7612a-106">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="7612a-107">およびその他のメソッドを探してい `console.log()` `console.error()` `console.*` ますか?</span><span class="sxs-lookup"><span data-stu-id="7612a-107">Looking for `console.log()`, `console.error()`, and the rest of the `console.*` methods?</span></span>  <span data-ttu-id="7612a-108">「[コンソール API リファレンス][DevToolsConsoleApi]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7612a-108">See [Console API Reference][DevToolsConsoleApi].</span></span>  

## <span data-ttu-id="7612a-109">最近評価された式</span><span class="sxs-lookup"><span data-stu-id="7612a-109">Recently Evaluated Expression</span></span>  

```console
$_
```  

<span data-ttu-id="7612a-110">直近に評価された式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-110">Returns the value of the most recently evaluated expression.</span></span>  

<span data-ttu-id="7612a-111">次の図では、単純な式 \ (\ `2 + 2` ) が評価されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-111">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="7612a-112">`$_`プロパティが評価され、同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7612a-112">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$ _ は、最近評価された式です。" lightbox="../media/console-arithmatic.msft.png":::
   <span data-ttu-id="7612a-114">図 1: `$_` 前回評価された式</span><span class="sxs-lookup"><span data-stu-id="7612a-114">Figure 1:  `$_` is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-115">次の図では、評価式には最初に名前の配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7612a-115">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="7612a-116">評価して `$_.length` 配列の長さを確認します。変更された値は、 `$_` 最新の評価済みの式になり `4` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-116">Evaluating `$_.length` to find the length of the array, the value stored in `$_` changes to become the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="新しいコマンドが評価されたときの $ _ 変更" lightbox="../media/console-array-length.msft.png":::
   <span data-ttu-id="7612a-118">図 2: `$_` 新しいコマンドの評価時の変更点</span><span class="sxs-lookup"><span data-stu-id="7612a-118">Figure 2:  `$_` changes when new commands are evaluated</span></span>  
:::image-end:::  

## <span data-ttu-id="7612a-119">最近選んだ要素または JavaScript オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7612a-119">Recently Selected Element Or JavaScript Object</span></span>  

```console
$0
```  

<span data-ttu-id="7612a-120">最後に選択された要素または JavaScript オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-120">Returns the most recently selected element or JavaScript object.</span></span>  `$1` <span data-ttu-id="7612a-121">最後に選択された2番目の値を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-121">returns the second most recently selected one, and so on.</span></span>  <span data-ttu-id="7612a-122">、、、、 `$0` `$1` およびコマンドは、 `$2` `$3` `$4` **要素**パネル内で検査された最後の5つの DOM 要素、または**メモリ**パネルで選択された最後の5つの JavaScript ヒープオブジェクトへの履歴参照として機能します。</span><span class="sxs-lookup"><span data-stu-id="7612a-122">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** panel or the last five JavaScript heap objects selected in the **Memory** panel.</span></span>  

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

<span data-ttu-id="7612a-123">次の図では、[ `img` **要素**] パネルで要素が選択されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-123">In the following figure, an `img` element is selected in the **Elements** panel.</span></span>  <span data-ttu-id="7612a-124">**本体**のドロアーで、 `$0` 評価が完了し、同じ要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-124">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="7612a-126">図 3:</span><span class="sxs-lookup"><span data-stu-id="7612a-126">Figure 3:  The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="7612a-127">次の図では、同じページで選択された別の要素が画像に表示されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-127">In the following figure, the image shows a different element selected in the same page.</span></span>  <span data-ttu-id="7612a-128">現在選択されている `$0` 要素を参照して `$1` いますが、以前に選択されていた要素を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-128">The `$0` now refers to the newly selected element, while `$1` returns the previously selected one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="7612a-130">図 4:</span><span class="sxs-lookup"><span data-stu-id="7612a-130">Figure 4:  The</span></span> `$1`  
:::image-end:::  

## <span data-ttu-id="7612a-131">クエリセレクター</span><span class="sxs-lookup"><span data-stu-id="7612a-131">Query Selector</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="7612a-132">指定された CSS セレクターで最初の DOM 要素への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-132">Returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="7612a-133">このメソッドは、[ドキュメントの querySelector ()][MDNDocumentQuerySelector]メソッドのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="7612a-133">This method is an alias for the [document.querySelector()][MDNDocumentQuerySelector] method.</span></span>  

<span data-ttu-id="7612a-134">次の図では、文書内の最初の要素への参照 `<img>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-134">In the following figure, a reference to the first `<img>` element in the document is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$ (' Img ')" lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="7612a-136">図 5:</span><span class="sxs-lookup"><span data-stu-id="7612a-136">Figure 5:  The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="7612a-137">返された結果にポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[**要素パネルで**表示] を選択して DOM で見つけるか、表示されたらページ上に**スクロール**して表示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-137">Hover on the returned result, open the contextual menu \(right-click\), and select **Reveal in Elements Panel** to find it in the DOM or **Scroll in to View** to show it on the page.</span></span>  

<span data-ttu-id="7612a-138">次の図では、現在選択されている要素への参照が返され、src プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-138">In the following figure, a reference to the currently selected element is returned and the src property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$ (' Img ') src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="7612a-140">図 6:</span><span class="sxs-lookup"><span data-stu-id="7612a-140">Figure 6:  The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="7612a-141">このメソッドは、要素を検索する "element" またはノードを指定する2番目のパラメーター startNode もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7612a-141">This method also supports a second parameter, startNode, that specifies an "element" or Node from which to search for elements.</span></span>  <span data-ttu-id="7612a-142">パラメーターの既定値は `document` です。</span><span class="sxs-lookup"><span data-stu-id="7612a-142">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="7612a-143">次の図では、最初 `img` の要素がであり、 `title--image` 正しく表示され `src` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-143">In the following figure, the first `img` element is found after the `title--image` and displays the `src` properly is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$ (' Img '、ドキュメントの querySelector (' タイトル--image ')) src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="7612a-145">図 7:</span><span class="sxs-lookup"><span data-stu-id="7612a-145">Figure 7:  The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="7612a-146">使用している jQuery などのライブラリを使用している場合、 `$` 機能は上書きされ、 `$` そのライブラリの実装に対応します。</span><span class="sxs-lookup"><span data-stu-id="7612a-146">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

## <span data-ttu-id="7612a-147">すべてのクエリセレクター</span><span class="sxs-lookup"><span data-stu-id="7612a-147">Query Selector All</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="7612a-148">指定された CSS セレクターに一致する要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-148">Returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="7612a-149">このメソッドは、 [querySelectorAll ()][MDNDocumentQuerySelectorAll]メソッドを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="7612a-149">This method is equivalent to calling the [document.querySelectorAll()][MDNDocumentQuerySelectorAll] method.</span></span>  

<span data-ttu-id="7612a-150">次のコードサンプルと図では、を使用して、 `$$()` 現在のドキュメント内のすべての要素の配列を作成 `<img>` し、各要素のプロパティの値を表示し `src` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-150">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current document and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="$ $ () を使用して、ドキュメント内のすべての画像を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="7612a-152">図 8: `$$()` ドキュメント内のすべての画像を選択してソースを表示するために使用する</span><span class="sxs-lookup"><span data-stu-id="7612a-152">Figure 8:  Using `$$()` to select all images in the document and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-153">このメソッドは、要素を検索する要素またはノードを指定する2番目の parameter startNode もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7612a-153">This method also supports a second parameter, startNode, that specifies an element or Node from which to search for elements.</span></span>  <span data-ttu-id="7612a-154">パラメーターの既定値は `document` です。</span><span class="sxs-lookup"><span data-stu-id="7612a-154">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="7612a-155">次のコードサンプルと図では、前のコードサンプルと図を変更したバージョンを使って、選択した `$$()` `<img>` ノードの後に現在の文書内に出現するすべての要素の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="7612a-155">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current document after the selected Node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="$ $ () を使用して、文書内の指定された <div> 要素の後に表示されるすべての画像を選択して、ソースを表示する" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="7612a-157">図 9: `$$()` 文書内の指定された要素の後に表示されるすべての画像を選択して `<div>` ソースを表示する</span><span class="sxs-lookup"><span data-stu-id="7612a-157">Figure 9:  Using `$$()` to select all images that appear after the specified `<div>` element in the document and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="7612a-158">コンソールを押して、 `Shift` + `Enter` スクリプトを実行せずに、新しい行を開始します。</span><span class="sxs-lookup"><span data-stu-id="7612a-158">Press `Shift`+`Enter` in the console to start a new line without running the script.</span></span>  

## <span data-ttu-id="7612a-159">X</span><span class="sxs-lookup"><span data-stu-id="7612a-159">XPath</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="7612a-160">指定された XPath 式と一致する DOM 要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-160">Returns an array of DOM elements that match the specified XPath expression.</span></span>  

<span data-ttu-id="7612a-161">次のコードサンプルと図では、ページ上のすべての `<p>` 要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-161">In the following code sample and figure, all of the `<p>` elements on the page are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="XPath セレクターを使用する" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="7612a-163">図 10: XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="7612a-163">Figure 10:  Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-164">次のコードサンプルと図では、要素を `<p>` 含むすべての要素 `<a>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-164">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="より複雑な XPath セレクターを使用する" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="7612a-166">図 11: より複雑な XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="7612a-166">Figure 11:  Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-167">他のセレクターコマンドと同様に、 `$x(path)` `startNode` 要素を検索する要素またはノードを指定する、オプションの2番目のパラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="7612a-167">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or Node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="StartNode で XPath セレクターを使用する" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="7612a-169">図 12: で XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="7612a-169">Figure 12:  Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

## <span data-ttu-id="7612a-170">clear</span><span class="sxs-lookup"><span data-stu-id="7612a-170">clear</span></span>  

```console
clear()
```  

<span data-ttu-id="7612a-171">履歴の本体をクリアします。</span><span class="sxs-lookup"><span data-stu-id="7612a-171">Clears the console of the history.</span></span>  

```console
clear()
```  

## <span data-ttu-id="7612a-172">copy</span><span class="sxs-lookup"><span data-stu-id="7612a-172">copy</span></span>  

```console
copy(object)
```  

<span data-ttu-id="7612a-173">メソッドによって、 `copy(object)` 指定したオブジェクトの文字列表現がクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7612a-173">The `copy(object)` method copies a string representation of the specified object to the clipboard.</span></span>  

```console
copy($0)
```  

## <span data-ttu-id="7612a-174">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7612a-174">debug</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="7612a-175">[Chromium 問題 #1050237][MonorailIssue1050237]は、関数のバグを追跡 `debug()` しています。</span><span class="sxs-lookup"><span data-stu-id="7612a-175">The [Chromium issue #1050237][MonorailIssue1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="7612a-176">この問題が発生した場合は、代わりに[ブレークポイントを使用][DevtoolsJavascriptBreakpoints]してみてください。</span><span class="sxs-lookup"><span data-stu-id="7612a-176">If you encounter the issue, try [using breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="7612a-177">指定したメソッドを要求すると、デバッガーが呼び出され、**ソース**パネルのメソッド内で中断されます。これにより、コードをステップ実行してデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="7612a-177">When you request the specified method, the debugger is invoked and breaks inside the method on the **Sources** panel allowing you to step through the code and debug it.</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="Debug () を使用したメソッド内の中断" lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="7612a-179">図 13: メソッド内での区切り</span><span class="sxs-lookup"><span data-stu-id="7612a-179">Figure 13:  Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="7612a-180">`undebug(method)`メソッドの中断を停止するには、または UI を使ってすべてのブレークポイントを無効にする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="7612a-180">Use `undebug(method)` to stop breaking on the method, or use the UI to disable all breakpoints.</span></span>  

<span data-ttu-id="7612a-181">ブレークポイントの詳細については、「[ブレークポイントでコードを一時停止][DevToolsJavascriptBreakpoints]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7612a-181">For more information on breakpoints, see [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

## <span data-ttu-id="7612a-182">dir</span><span class="sxs-lookup"><span data-stu-id="7612a-182">dir</span></span>  

```console
dir(object)
```  

<span data-ttu-id="7612a-183">指定したオブジェクトのすべてのプロパティのオブジェクトスタイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-183">Displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="7612a-184">このメソッドは、 [console. dir ()][MDNConsoleDir]メソッドのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="7612a-184">This method is an alias for the [console.dir()][MDNConsoleDir] method.</span></span>  

<span data-ttu-id="7612a-185">本体でを評価して、 `document.head` タグとタグの間に HTML を表示し `<head>` `</head>` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-185">Evaluate `document.head` in the Console to display the HTML between the `<head>` and `</head>` tags.</span></span>  <span data-ttu-id="7612a-186">次のコードサンプルと図では、コンソールで使用した後にオブジェクトスタイルの一覧が表示され `console.dir()` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-186">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the Console.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="Dir () メソッドを使ってドキュメントをログに記録します。" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="7612a-188">図 14: `document.head` メソッドを使用してログを記録する `dir()`</span><span class="sxs-lookup"><span data-stu-id="7612a-188">Figure 14:  Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-189">詳細については、 [`console.dir()`][DevToolsConsoleApiConsoleDirObject] 本体 API のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7612a-189">For more information, see the [`console.dir()`][DevToolsConsoleApiConsoleDirObject] entry in the Console API.</span></span>  

## <span data-ttu-id="7612a-190">dirxml</span><span class="sxs-lookup"><span data-stu-id="7612a-190">dirxml</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="7612a-191">[**要素**] タブに表示されるように、指定したオブジェクトの XML 表現を印刷します。 このメソッドは、console の[dirxml ()][MDNConsoleDirxml]メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="7612a-191">Prints an XML representation of the specified object, as seen in the **Elements** tab.  This method is equivalent to the [console.dirxml()][MDNConsoleDirxml] method.</span></span>  

## <span data-ttu-id="7612a-192">検査</span><span class="sxs-lookup"><span data-stu-id="7612a-192">inspect</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="7612a-193">適切なパネル (DOM 要素の場合は**要素**パネル、JavaScript ヒープオブジェクトの場合は**メモリ**パネル) で、指定された要素またはオブジェクトを開き、選択します。</span><span class="sxs-lookup"><span data-stu-id="7612a-193">Opens and selects the specified element or object in the appropriate panel:  either the **Elements** panel for DOM elements or the **Memory** panel for JavaScript heap objects.</span></span>  

<span data-ttu-id="7612a-194">次のコードサンプルと図は、[ `document.body` **要素**] パネルで開きます。</span><span class="sxs-lookup"><span data-stu-id="7612a-194">In the following code sample and figure, the `document.body` opens in the **Elements** panel.</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="検査 () での要素の検査" lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="7612a-196">図 15: の要素を調べる</span><span class="sxs-lookup"><span data-stu-id="7612a-196">Figure 15:  Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="7612a-197">検査するメソッドを渡すとき、メソッドは**ソース**パネルでドキュメントを開き、調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7612a-197">When passing a method to inspect, the method opens the document in the **Sources** panel for you to inspect.</span></span>  

## <span data-ttu-id="7612a-198">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="7612a-198">getEventListeners</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="7612a-199">指定したオブジェクトに登録されているイベントリスナーを返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-199">Returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="7612a-200">戻り値は、登録されている各イベントの種類 (やなど) の配列を含むオブジェクトです `click` `keydown` 。</span><span class="sxs-lookup"><span data-stu-id="7612a-200">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="7612a-201">各配列のメンバーは、各型に登録されているリスナーを記述するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7612a-201">The members of each array are objects that describe the listener registered for each type.</span></span>  <span data-ttu-id="7612a-202">次のコードサンプルの図は、ドキュメントオブジェクトに登録されているすべてのイベントリスナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="7612a-202">In the following code sample figure, all of the event listeners registered on the document object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="GetEventListeners を使った出力 (ドキュメント)" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="7612a-204">図 16: を使用した場合の結果</span><span class="sxs-lookup"><span data-stu-id="7612a-204">Figure 16:  The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="7612a-205">指定したオブジェクトに複数のリスナーが登録されている場合、この配列には各リスナーのメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7612a-205">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="7612a-206">次の図に、イベントのドキュメント要素に登録されている2つのイベントリスナーを示し `click` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-206">In the following figure, there are two event listeners registered on the document element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="複数のリスナー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="7612a-208">図 17: 複数のリスナー</span><span class="sxs-lookup"><span data-stu-id="7612a-208">Figure 17:  Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-209">次の各オブジェクトをさらに拡張して、プロパティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7612a-209">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="リスナーオブジェクトの展開ビュー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="7612a-211">図 18: リスナーオブジェクトの展開ビュー</span><span class="sxs-lookup"><span data-stu-id="7612a-211">Figure 18:  Expanded view of listener object</span></span>  
:::image-end:::  

## <span data-ttu-id="7612a-212">キー</span><span class="sxs-lookup"><span data-stu-id="7612a-212">keys</span></span>  

```console
keys(object)
```  

<span data-ttu-id="7612a-213">指定したオブジェクトに属するプロパティの名前を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-213">Returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="7612a-214">同じプロパティの関連する値を取得するには、を使用 `values()` します。</span><span class="sxs-lookup"><span data-stu-id="7612a-214">To get the associated values of the same properties, use `values()`.</span></span>  

<span data-ttu-id="7612a-215">たとえば、アプリケーションが次のオブジェクトを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="7612a-215">For example, suppose your application defined the following object.</span></span>  

```console
var player1 = { "name":  "Ted", "level": 42 }
```  

<span data-ttu-id="7612a-216">次のコードサンプルと図では、 `player1` 入力と本体への入力前に、その結果がグローバル名前空間 \ (簡潔さ) で定義されていることを前提としてい `keys(player1)` `values(player1)` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-216">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) prior to typing `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="Keys () コマンドと values () コマンド" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="7612a-218">図 19: `keys()` および `values()` コマンド</span><span class="sxs-lookup"><span data-stu-id="7612a-218">Figure 19:  The `keys()` and `values()` commands</span></span>  
:::image-end:::  

## <span data-ttu-id="7612a-219">モニター</span><span class="sxs-lookup"><span data-stu-id="7612a-219">monitor</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="7612a-220">メソッドが呼び出されたときにメソッドに渡された引数と共に、メソッド名を示すメッセージをコンソールに記録します。</span><span class="sxs-lookup"><span data-stu-id="7612a-220">Logs a message to the console that indicates the method name along with the arguments that are passed to the method when it was called.</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="Monitor () メソッド" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="7612a-222">図 20: `monitor()` メソッド</span><span class="sxs-lookup"><span data-stu-id="7612a-222">Figure 20:  The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-223">`unmonitor(method)`監視を停止するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7612a-223">Use `unmonitor(method)` to cease monitoring.</span></span>  

## <span data-ttu-id="7612a-224">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="7612a-224">monitorEvents</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="7612a-225">指定したイベントのいずれかが指定したオブジェクトで発生した場合、イベントオブジェクトは本体に記録されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-225">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="7612a-226">監視する1つのイベント、一連のイベント、または定義済みのイベントコレクションにマップされる汎用イベント型のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7612a-226">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  <span data-ttu-id="7612a-227">次のコードサンプルと図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7612a-227">See the following code sample and figure.</span></span>  

<span data-ttu-id="7612a-228">次のモニターは、window オブジェクトのすべてのサイズ変更イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="7612a-228">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="モニタリングウィンドウのサイズ変更イベント" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="7612a-230">図 21: ウィンドウのサイズ変更イベントの監視</span><span class="sxs-lookup"><span data-stu-id="7612a-230">Figure 21:  Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="7612a-231">次の例では、window オブジェクトの両方のイベントとイベントを監視する配列を定義して `resize` `scroll` います。</span><span class="sxs-lookup"><span data-stu-id="7612a-231">The following defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="7612a-232">また、使用可能なイベントの種類のいずれかを指定することもできます。これは、事前定義された一連のイベントにマップされる文字列です。</span><span class="sxs-lookup"><span data-stu-id="7612a-232">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="7612a-233">以下の表に、利用可能なイベントの種類と関連付けられているイベントマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-233">The table below displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="7612a-234">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="7612a-234">Event type</span></span> | <span data-ttu-id="7612a-235">対応するマップされたイベント</span><span class="sxs-lookup"><span data-stu-id="7612a-235">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="7612a-236">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mousewheel"、"mouseup"、""</span><span class="sxs-lookup"><span data-stu-id="7612a-236">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="7612a-237">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="7612a-237">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="7612a-238">"touchcancel", "touchend", "touchmove", "touchstart"</span><span class="sxs-lookup"><span data-stu-id="7612a-238">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="7612a-239">"ぼかし"、"変更"、"フォーカス"、"リセット"、"サイズ変更"、"スクロール"、"選択"、"送信"、"ズーム"</span><span class="sxs-lookup"><span data-stu-id="7612a-239">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="7612a-240">次のコードサンプルでは、 `key` 入力テキストフィールドのイベントに対応するイベントの種類が、[ `key` **要素**] パネルで現在選択されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-240">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently selected in the **Elements** panel.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="7612a-241">次の図では、テキストフィールドに文字を入力した後のサンプル出力が表示されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-241">In the following figure the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="主要イベントの監視" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="7612a-243">図 22: 主要イベントの監視</span><span class="sxs-lookup"><span data-stu-id="7612a-243">Figure 22:  Monitoring key events</span></span>  
:::image-end:::  

## <span data-ttu-id="7612a-244">profile</span><span class="sxs-lookup"><span data-stu-id="7612a-244">profile</span></span>  

```console
profile([name])
```  

<span data-ttu-id="7612a-245">省略可能な名前で JavaScript CPU プロファイリングセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="7612a-245">Starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="7612a-246">Profile [end ()](#profileend)メソッドは、プロファイルを完了し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-246">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** panel.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="7612a-247">メソッドを実行して `profile()` プロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="7612a-247">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="7612a-248">プロファイルを停止して、**メモリ**パネルに結果を表示するには、 [profileend ()](#profileend)メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7612a-248">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** panel.</span></span>  

<span data-ttu-id="7612a-249">プロファイルは入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7612a-249">Profiles may also be nested.</span></span>  <span data-ttu-id="7612a-250">次のコードサンプルと図では、注文に関係なく同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="7612a-250">In the following code samples and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="7612a-251">複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7612a-251">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="7612a-252">profileEnd</span><span class="sxs-lookup"><span data-stu-id="7612a-252">profileEnd</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="7612a-253">JavaScript CPU のプロファイリングセッションを完了し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-253">Completes a JavaScript CPU profiling session and displays the results in the **Memory** panel.</span></span>  <span data-ttu-id="7612a-254">[Profile ()](#profile)メソッドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7612a-254">You must be running the [profile()](#profile) method.</span></span>  <!--See also [Speed Up JavaScript Runtime][DevToolsRenderingToolsJSRuntime].  -->  

1.  <span data-ttu-id="7612a-255">[Profile ()](#profile)メソッドを実行してプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="7612a-255">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="7612a-256">メソッドを実行して `profileEnd()` プロファイリングを停止し、**メモリ**パネルに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7612a-256">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** panel.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="7612a-257">プロファイルは入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7612a-257">Profiles may also be nested.</span></span>  <span data-ttu-id="7612a-258">次のコードサンプルと図は、順序に関係なく同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="7612a-258">In the following code sample and figure the result is the same regardless of the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="7612a-259">結果は、**メモリ**パネルにヒープスナップショットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-259">The result appears as a Heap Snapshot in the **Memory** panel.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="グループ化されたプロファイル" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="7612a-261">図 23: グループ化されたプロファイル</span><span class="sxs-lookup"><span data-stu-id="7612a-261">Figure 23:  Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="7612a-262">複数の CPU プロファイルを同時に操作することができます。また、複数の CPU プロファイルを作成順序で閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7612a-262">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

## <span data-ttu-id="7612a-263">queryObjects</span><span class="sxs-lookup"><span data-stu-id="7612a-263">queryObjects</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="7612a-264">指定したコンストラクターで作成されたオブジェクトの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-264">Return an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="7612a-265">のスコープ `queryObjects()` は、現在選択されているランタイムコンテキスト (本体) です。</span><span class="sxs-lookup"><span data-stu-id="7612a-265">The scope of `queryObjects()` is the currently-selected runtime context in the console.</span></span>

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="7612a-266">All を返し `Promises` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-266">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="7612a-267">すべての HTML 要素を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-267">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="7612a-268">を使用してインスタンス化されたすべてのオブジェクトを返し `new functionName()` ます。</span><span class="sxs-lookup"><span data-stu-id="7612a-268">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <span data-ttu-id="7612a-269">'95'5c</span><span class="sxs-lookup"><span data-stu-id="7612a-269">table</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="7612a-270">列見出しを省略できるデータオブジェクトに基づいて、テーブルの書式設定でオブジェクトデータをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7612a-270">Logs object data with table formatting based upon the data object in with optional column headings.</span></span>  <span data-ttu-id="7612a-271">次のコードサンプルと図では、コンソールの表を使って名前のリストが表示されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-271">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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

:::image type="complex" source="../media/console-table-display.msft.png" alt-text="Table () メソッドの結果" lightbox="../media/console-table-display.msft.png":::
   <span data-ttu-id="7612a-273">図 24: メソッドの結果 `table()`</span><span class="sxs-lookup"><span data-stu-id="7612a-273">Figure 24:  The result of the `table()` method</span></span>  
:::image-end:::  

## <span data-ttu-id="7612a-274">undebug</span><span class="sxs-lookup"><span data-stu-id="7612a-274">undebug</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="7612a-275">メソッドが呼び出されたときにデバッガーが呼び出されなくなるように、指定されたメソッドのデバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="7612a-275">Stops the debugging of the specified method so that when the method is called, the debugger is no longer invoked.</span></span>  

```console
undebug(getData);
```  

## <span data-ttu-id="7612a-276">未停止</span><span class="sxs-lookup"><span data-stu-id="7612a-276">unmonitor</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="7612a-277">指定したメソッドの監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="7612a-277">Stops the monitoring of the specified method.</span></span>  <span data-ttu-id="7612a-278">このメソッドは、 [monitor ()](#monitor)メソッドと連携して使用されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-278">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

```console
unmonitor(getData);
```  

## <span data-ttu-id="7612a-279">イベントを監視しない</span><span class="sxs-lookup"><span data-stu-id="7612a-279">unmonitorEvents</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="7612a-280">指定したオブジェクトおよびイベントの監視イベントを停止します。</span><span class="sxs-lookup"><span data-stu-id="7612a-280">Stops monitoring events for the specified object and events.</span></span>  <span data-ttu-id="7612a-281">たとえば、次の例では、window オブジェクトのイベント監視がすべて停止しています。</span><span class="sxs-lookup"><span data-stu-id="7612a-281">For example, the following stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="7612a-282">オブジェクトの特定のイベントの監視を選択的に停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="7612a-282">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="7612a-283">たとえば、次のコードでは、現在選択されている要素のすべての `mouse` イベントを監視し、イベントの監視を停止します (多くの場合、 `mousemove` 本体の出力のノイズを軽減します)。</span><span class="sxs-lookup"><span data-stu-id="7612a-283">For example, the following code starts monitoring all `mouse` events on the currently selected element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

## <span data-ttu-id="7612a-284">values</span><span class="sxs-lookup"><span data-stu-id="7612a-284">values</span></span>  

```console
values(object)
```  

<span data-ttu-id="7612a-285">指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7612a-285">Returns an array containing the values of all properties belonging to the specified object.</span></span>  

```console
values(object);
```  

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
> <span data-ttu-id="7612a-295">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7612a-295">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7612a-296">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-296">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7612a-298">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7612a-298">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
