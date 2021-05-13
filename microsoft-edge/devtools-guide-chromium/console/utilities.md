---
description: DevTools コンソールで使用できる便利なコマンドMicrosoft Edge参照します。
title: コンソール ユーティリティ API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 436f2807c5fab1723ca6cc93fddc68d9ecf12db7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564533"
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
# <a name="console-utilities-api-reference"></a><span data-ttu-id="c84be-104">コンソール ユーティリティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c84be-104">Console Utilities API reference</span></span>  

<span data-ttu-id="c84be-105">コンソール ユーティリティ API には、次の一般的なタスクを完了するための便利なコマンドのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c84be-105">The Console Utilities API contains a collection of convenience commands to complete the following common tasks.</span></span>  

*   <span data-ttu-id="c84be-106">DOM 要素の選択と検査</span><span class="sxs-lookup"><span data-stu-id="c84be-106">Choose and inspect DOM elements</span></span>  
*   <span data-ttu-id="c84be-107">データを読み取り可能な形式で表示する</span><span class="sxs-lookup"><span data-stu-id="c84be-107">Display data in readable format</span></span>  
*   <span data-ttu-id="c84be-108">プロファイラーの停止と開始</span><span class="sxs-lookup"><span data-stu-id="c84be-108">Stop and start the profiler</span></span>  
*   <span data-ttu-id="c84be-109">DOM イベントの監視</span><span class="sxs-lookup"><span data-stu-id="c84be-109">Monitor DOM events</span></span>  
    
> [!WARNING]
> <span data-ttu-id="c84be-110">次のコマンドは、DevTools コンソールMicrosoft Edgeでのみ機能**します**。</span><span class="sxs-lookup"><span data-stu-id="c84be-110">The following commands only work in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="c84be-111">スクリプトから実行すると、コマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c84be-111">The commands do not work if run from your scripts.</span></span>  

<span data-ttu-id="c84be-112">and メソッドと他のメソッドの詳細については、「コンソール API リファレンス」 `console.log()` `console.error()` `console.*` [に移動します][DevToolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="c84be-112">For more information about the `console.log()` and `console.error()` methods and the rest of the `console.*` methods, navigate to [Console API Reference][DevToolsConsoleApi].</span></span>  

## <a name="recently-evaluated-expression"></a><span data-ttu-id="c84be-113">最近評価された式</span><span class="sxs-lookup"><span data-stu-id="c84be-113">Recently evaluated expression</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-114">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-114">Console syntax</span></span>  

```console
$_
```  

<span data-ttu-id="c84be-115">このコマンドは、最近評価された式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-115">This command returns the value of the most recently evaluated expression.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-116">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-116">Console example</span></span>  

<span data-ttu-id="c84be-117">次の図では、単純な式 \( `2 + 2` \) が評価されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-117">In the following figure, a simple expression \(`2 + 2`\) is evaluated.</span></span>  <span data-ttu-id="c84be-118">その `$_` 後、同じ値を含むプロパティが評価されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-118">The `$_` property is then evaluated, which contains the same value.</span></span>  

:::image type="complex" source="../media/console-arithmatic.msft.png" alt-text="$_ は、最近評価された式です。" lightbox="../media/console-arithmatic.msft.png":::
   `$_` <span data-ttu-id="c84be-120">は、最も最近評価された式です。</span><span class="sxs-lookup"><span data-stu-id="c84be-120">is the most recently evaluated expression</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-121">次の図では、評価された式には最初に名前の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c84be-121">In the following figure, the evaluated expression initially contains an array of names.</span></span>  <span data-ttu-id="c84be-122">配列の `$_.length` 長さを見つけるために評価すると、格納されている値が最新の `$_` 評価式になります `4` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-122">Evaluating `$_.length` to find the length of the array, the value stored in `$_` becomes the latest evaluated expression, `4`.</span></span>  

:::image type="complex" source="../media/console-array-length.msft.png" alt-text="$しいコマンドが評価される場合の $_ の変更" lightbox="../media/console-array-length.msft.png":::
   `$_` <span data-ttu-id="c84be-124">新しいコマンドが評価される場合の変更</span><span class="sxs-lookup"><span data-stu-id="c84be-124">changes when new commands are evaluated</span></span>  
:::image-end:::  

---  

## <a name="recently-chosen-element-or-javascript-object"></a><span data-ttu-id="c84be-125">最近選択した要素または JavaScript オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c84be-125">Recently chosen element or JavaScript object</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-126">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-126">Console syntax</span></span>  

```console
$0
```  

<span data-ttu-id="c84be-127">このコマンドは、最近選択した要素または JavaScript オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-127">This command returns the most recently chosen element or JavaScript object.</span></span>  `$1` <span data-ttu-id="c84be-128">2 番目に最近選択した 1 つを返します。などです。</span><span class="sxs-lookup"><span data-stu-id="c84be-128">returns the second most recently chosen one, and so on.</span></span>  <span data-ttu-id="c84be-129">、 、 、 、およびコマンドは、Elements ツール内で検査された最後の 5 つの DOM 要素、またはメモリ ツールで選択された最後の 5 つの JavaScript ヒープ オブジェクトへの履歴参照として `$0` `$1` `$2` `$3` `$4` **機能**します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c84be-129">The `$0`, `$1`, `$2`, `$3`, and `$4` commands work as a historical reference to the last five DOM elements inspected within the **Elements** tool or the last five JavaScript heap objects chosen in the **Memory** tool.</span></span>  

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
      &nbsp;
   :::column-end:::
:::row-end:::  

### <a name="console-example"></a><span data-ttu-id="c84be-130">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-130">Console example</span></span>  

<span data-ttu-id="c84be-131">次の図では、要素 `img` ツールで要素が **選択** されています。</span><span class="sxs-lookup"><span data-stu-id="c84be-131">In the following figure, an `img` element is chosen in the **Elements** tool.</span></span>  <span data-ttu-id="c84be-132">コンソール ドロ **ワーで** 、 `$0` 評価され、同じ要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-132">In the **Console** drawer, `$0` has been evaluated and displays the same element.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$0.msft.png" alt-text="$0" lightbox="../media/console-image-highlighted-$0.msft.png":::
   <span data-ttu-id="c84be-134">を使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-134">The</span></span> `$0`  
:::image-end:::  

<span data-ttu-id="c84be-135">次の図では、同じ Web ページで選択された別の要素が画像に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-135">In the following figure, the image displays a different element chosen in the same webpage.</span></span>  <span data-ttu-id="c84be-136">ここで `$0` 、新しく選択した要素を参照し、以前に選択した `$1` 要素を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-136">The `$0` now refers to the newly chosen element, while `$1` returns the previously chosen one.</span></span>  

:::image type="complex" source="../media/console-image-highlighted-$1.msft.png" alt-text="$1" lightbox="../media/console-image-highlighted-$1.msft.png":::
   <span data-ttu-id="c84be-138">を使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-138">The</span></span> `$1`  
:::image-end:::  

---  

## <a name="query-selector"></a><span data-ttu-id="c84be-139">クエリ セレクター</span><span class="sxs-lookup"><span data-stu-id="c84be-139">Query selector</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-140">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-140">Console syntax</span></span>  

```console
$(selector, [startNode])
```  

<span data-ttu-id="c84be-141">このコマンドは、指定された CSS セレクターを持つ最初の DOM 要素への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-141">This command returns the reference to the first DOM element with the specified CSS selector.</span></span>  <span data-ttu-id="c84be-142">このメソッドは [、document.querySelector() メソッドのエイリアス][MdnDocsWebApiDocumentQueryselector] です。</span><span class="sxs-lookup"><span data-stu-id="c84be-142">This method is an alias for the [document.querySelector()][MdnDocsWebApiDocumentQueryselector] method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-143">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-143">Console example</span></span>  

<span data-ttu-id="c84be-144">次の図では、Web ページの最初の要素への `<img>` 参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-144">In the following figure, a reference to the first `<img>` element in the webpage is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image.msft.png" alt-text="$('img')" lightbox="../media/console-element-selector-image.msft.png":::
   <span data-ttu-id="c84be-146">を使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-146">The</span></span> `$('img')`  
:::image-end:::  

<span data-ttu-id="c84be-147">DOM 内の最初の要素を見つけるか、Web ページで見つけて表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c84be-147">To find the first element in the DOM or to find and display it on the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="c84be-148">返された結果にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="c84be-148">Hover on the returned result.</span></span>  
1.  <span data-ttu-id="c84be-149">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="c84be-149">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="c84be-150">[要素 **] パネルで [表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c84be-150">Choose **Reveal in Elements Panel**.</span></span>  

<span data-ttu-id="c84be-151">次の図では、現在選択されている要素への参照が返され、 `src` プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-151">In the following figure, a reference to the currently chosen element is returned and the `src` property is displayed.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-source.msft.png" alt-text="$('img').src" lightbox="../media/console-element-selector-image-source.msft.png":::
   <span data-ttu-id="c84be-153">を使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-153">The</span></span> `$('img').src`  
:::image-end:::  

<span data-ttu-id="c84be-154">このメソッドは、要素を検索する要素またはノードを指定する 2 番目のパラメーター `startNode` もサポートします。</span><span class="sxs-lookup"><span data-stu-id="c84be-154">This method also supports a second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  <span data-ttu-id="c84be-155">パラメーターの既定値はです `document` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-155">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="c84be-156">次の図では、要素が見つかった後の最初の要素で、要素のプロパティ `img` `title--image` `src` `img` が返されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-156">In the following figure, the first `img` element after the `title--image` element is found, and the `src` property of the `img` element is returned.</span></span>  

:::image type="complex" source="../media/console-element-selector-image-filter-source.msft.png" alt-text="$('img', document.querySelector('title--image')).src" lightbox="../media/console-element-selector-image-filter-source.msft.png":::
   <span data-ttu-id="c84be-158">を使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-158">The</span></span> `$('img', document.querySelector('title--image')).src`  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c84be-159">使用する jQuery などのライブラリを使用している場合、機能は上書きされ、そのライブラリの実装 `$` `$` に対応します。</span><span class="sxs-lookup"><span data-stu-id="c84be-159">If you are using a library such as jQuery that uses `$`, the functionality is overwritten, and `$` corresponds to the implementation from that library.</span></span>  

---  

## <a name="query-selector-all"></a><span data-ttu-id="c84be-160">クエリ セレクターすべて</span><span class="sxs-lookup"><span data-stu-id="c84be-160">Query selector all</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-161">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-161">Console syntax</span></span>  

```console
$$(selector, [startNode])
```  

<span data-ttu-id="c84be-162">このコマンドは、指定した CSS セレクターに一致する要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-162">This command returns an array of elements that match the specified CSS selector.</span></span>  <span data-ttu-id="c84be-163">このメソッドは [、document.querySelectorAll() メソッドの実行と同][MdnDocsWebApiDocumentQueryselectorall] じです。</span><span class="sxs-lookup"><span data-stu-id="c84be-163">This method is equivalent to running the [document.querySelectorAll()][MdnDocsWebApiDocumentQueryselectorall] method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-164">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-164">Console example</span></span>  

<span data-ttu-id="c84be-165">次のコード サンプルと図では、現在の Web ページ内のすべての要素の配列を作成し、各要素のプロパティの値 `$$()` `<img>` `src` を表示します。</span><span class="sxs-lookup"><span data-stu-id="c84be-165">In the following code sample and figure, use `$$()` to create an array of all `<img>` elements in the current webpage and display the value of the `src` property for each element.</span></span>  

```console
var images = $$('img');
for (each in images) {
    console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-all.msft.png" alt-text="$$() を使用して Web ページ内のすべての画像を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-all.msft.png":::
   <span data-ttu-id="c84be-167">Web `$$()` ページ内のすべての画像を選択し、ソースを表示する場合に使用する</span><span class="sxs-lookup"><span data-stu-id="c84be-167">Using `$$()` to choose all images in the webpage and display the sources</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-168">このメソッドは、要素を検索する要素またはノードを指定する 2 番目のパラメーター `startNode` もサポートします。</span><span class="sxs-lookup"><span data-stu-id="c84be-168">This method also supports a second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  <span data-ttu-id="c84be-169">パラメーターの既定値はです `document` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-169">The default value of the parameter is `document`.</span></span>  

<span data-ttu-id="c84be-170">次のコード サンプルと図では、前のコード サンプルと図の変更されたバージョンを使用して、選択したノードの後に現在の Web ページに表示されるすべての要素の配列 `$$()` `<img>` を作成します。</span><span class="sxs-lookup"><span data-stu-id="c84be-170">In the following code sample and figure, a modified version of the previous code sample and figure uses `$$()` to create an array of all `<img>` elements that appear in the current webpage after the chosen node.</span></span>  

```console
var images = $$('img', document.querySelector(`title--image`));
for (each in images) {
   console.log(images[each].src);
}
```  

:::image type="complex" source="../media/console-element-selector-image-filter-all.msft.png" alt-text="$$() を使用して、web ページ内の指定された div <要素の>を選択し、ソースを表示する" lightbox="../media/console-element-selector-image-filter-all.msft.png":::
   <span data-ttu-id="c84be-172">Web `$$()` ページで指定した要素の後に表示される画像を選択し、ソース `<div>` を表示する場合に使用する</span><span class="sxs-lookup"><span data-stu-id="c84be-172">Using `$$()` to choose all images that appear after the specified `<div>` element in the webpage and display the sources</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c84be-173">スクリプト `Shift` + `Enter` を実行**せずに新**しい行を開始するには、コンソールで選択します。</span><span class="sxs-lookup"><span data-stu-id="c84be-173">Select `Shift`+`Enter` in the **Console** to start a new line without running the script.</span></span>  

---  

## <a name="xpath"></a><span data-ttu-id="c84be-174">XPath</span><span class="sxs-lookup"><span data-stu-id="c84be-174">XPath</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-175">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-175">Console syntax</span></span>  

```console
$x(path, [startNode])
```  

<span data-ttu-id="c84be-176">このコマンドは、指定した XPath 式に一致する DOM 要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-176">This command returns an array of DOM elements that match the specified XPath expression.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-177">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-177">Console example</span></span>  

<span data-ttu-id="c84be-178">次のコード サンプルと図では、Web ページ `<p>` 上のすべての要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-178">In the following code sample and figure, all of the `<p>` elements on the webpage are returned.</span></span>  

```console
$x("//p")
```  

:::image type="complex" source="../media/console-array-xpath.msft.png" alt-text="XPath セレクターの使用" lightbox="../media/console-array-xpath.msft.png":::
   <span data-ttu-id="c84be-180">XPath セレクターの使用</span><span class="sxs-lookup"><span data-stu-id="c84be-180">Using an XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-181">次のコード サンプルと図では、要素を含む `<p>` すべての要素 `<a>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-181">In the following code sample and figure, all of the `<p>` elements that contain `<a>` elements are returned.</span></span>  

```console
$x("//p[a]")
```  

:::image type="complex" source="../media/console-array-xpath-sub-element.msft.png" alt-text="より複雑な XPath セレクターの使用" lightbox="../media/console-array-xpath-sub-element.msft.png":::
   <span data-ttu-id="c84be-183">より複雑な XPath セレクターの使用</span><span class="sxs-lookup"><span data-stu-id="c84be-183">Using a more complicated XPath selector</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-184">他のセレクター コマンドと同様に、要素を検索する要素またはノードを指定するオプションの 2 番目の `$x(path)` `startNode` パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c84be-184">Similar to the other selector commands, `$x(path)` has an optional second parameter, `startNode`, that specifies an element or node from which to search for elements.</span></span>  

:::image type="complex" source="../media/console-array-xpath-startnode.msft.png" alt-text="startNode で XPath セレクターを使用する" lightbox="../media/console-array-xpath-startnode.msft.png":::
   <span data-ttu-id="c84be-186">XPath セレクターを使用する</span><span class="sxs-lookup"><span data-stu-id="c84be-186">Using an XPath selector with</span></span> `startNode`  
:::image-end:::  

---  

## <a name="clear"></a><span data-ttu-id="c84be-187">clear</span><span class="sxs-lookup"><span data-stu-id="c84be-187">clear</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-188">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-188">Console syntax</span></span>  

```console
clear()
```  

<span data-ttu-id="c84be-189">この commnad は、履歴のコンソールをクリアします。</span><span class="sxs-lookup"><span data-stu-id="c84be-189">This commnad clears the console of the history.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-190">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-190">Console example</span></span>  

```console
clear()
```  

## <a name="copy"></a><span data-ttu-id="c84be-191">copy</span><span class="sxs-lookup"><span data-stu-id="c84be-191">copy</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-192">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-192">Console syntax</span></span>  

```console
copy(object)
```  

<span data-ttu-id="c84be-193">このメソッドは、指定したオブジェクトの文字列表現をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c84be-193">This method copies a string representation of the specified object to the clipboard.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-194">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-194">Console example</span></span>  

```console
copy($0)
```  

---  

## <a name="debug"></a><span data-ttu-id="c84be-195">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c84be-195">debug</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-196">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-196">Console syntax</span></span>  

```console
debug(method)
```  

>[!NOTE]
> <span data-ttu-id="c84be-197">この[Chromium問題#1050237、][CR1050237]関数のバグを追跡 `debug()` しています。</span><span class="sxs-lookup"><span data-stu-id="c84be-197">The [Chromium issue #1050237][CR1050237] is tracking a bug with the `debug()` function.</span></span>  <span data-ttu-id="c84be-198">問題が発生した場合は、代わりに [ブレークポイントを使用][DevtoolsJavascriptBreakpoints] してみてください。</span><span class="sxs-lookup"><span data-stu-id="c84be-198">If you encounter the issue, try using [breakpoints][DevtoolsJavascriptBreakpoints] instead.</span></span>  

<span data-ttu-id="c84be-199">指定したメソッドを要求すると、デバッガーは **Sources** ツールでメソッド内を呼び出し、ブレークします。</span><span class="sxs-lookup"><span data-stu-id="c84be-199">When you request the specified method, the debugger invokes and breaks inside the method on the **Sources** tool.</span></span>  <span data-ttu-id="c84be-200">これにより、コードをステップ実行してデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="c84be-200">It allows you to step through and debug the code.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-201">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-201">Console example</span></span>  

```console
debug("debug");
```  

:::image type="complex" source="../media/console-debug-text.msft.png" alt-text="debug() を使用してメソッド内でブレークする" lightbox="../media/console-debug-text.msft.png":::
   <span data-ttu-id="c84be-203">メソッド内でのブレーク</span><span class="sxs-lookup"><span data-stu-id="c84be-203">Breaking inside a method with</span></span> `debug()`  
:::image-end:::  

<span data-ttu-id="c84be-204">メソッド `undebug(method)` のブレークを停止したり、UI を使用してすべてのブレークポイントをオフにしたりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-204">Use `undebug(method)` to stop breaking on the method, or use the UI to turn off all breakpoints.</span></span>  

<span data-ttu-id="c84be-205">ブレークポイントの詳細については[、「DevTools][DevtoolsJavascriptBreakpoints]でブレークポイントを使用してコードを一時停止する方法Microsoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="c84be-205">For more information on breakpoints, navigate to [How to pause your code with breakpoints in Microsoft Edge DevTools][DevtoolsJavascriptBreakpoints].</span></span>  

---  

## <a name="dir"></a><span data-ttu-id="c84be-206">dir</span><span class="sxs-lookup"><span data-stu-id="c84be-206">dir</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-207">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-207">Console syntax</span></span>  

```console
dir(object)
```  

<span data-ttu-id="c84be-208">このコマンドは、指定したオブジェクトのすべてのプロパティのオブジェクト スタイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c84be-208">This command displays an object-style listing of all of the properties for the specified object.</span></span>  <span data-ttu-id="c84be-209">このメソッドは [console.dir() メソッドのエイリアス][MdnDocsWebApiConsoleDir] です。</span><span class="sxs-lookup"><span data-stu-id="c84be-209">This method is an alias for the [console.dir()][MdnDocsWebApiConsoleDir] method.</span></span>  

<span data-ttu-id="c84be-210">コンソール `document.head` で評価 **し** 、タグとタグの間に HTML `<head>` を表示 `</head>` します。</span><span class="sxs-lookup"><span data-stu-id="c84be-210">Evaluate `document.head` in the **Console** to display the HTML between the `<head>` and `</head>` tags.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-211">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-211">Console example</span></span>  

<span data-ttu-id="c84be-212">次のコード サンプルと図では、コンソールで使用した後にオブジェクト スタイルの一覧 `console.dir()` が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="c84be-212">In the following code sample and figure, an object-style listing is displayed after using `console.dir()` in the **Console**.</span></span>  

```console
document.head;
dir(document.head);
```  

:::image type="complex" source="../media/console-dir-document-head-expanded.msft.png" alt-text="dir() メソッドを使用して document.head をログに記録する" lightbox="../media/console-dir-document-head-expanded.msft.png":::
   <span data-ttu-id="c84be-214">メソッド `document.head` による `dir()` ログ記録</span><span class="sxs-lookup"><span data-stu-id="c84be-214">Logging `document.head` with `dir()` method</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-215">詳細については、コンソール API の [console.dir()][DevToolsConsoleApiConsoleDirObject] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c84be-215">For more information, navigate to [console.dir()][DevToolsConsoleApiConsoleDirObject] in the Console API.</span></span>  

---  

## <a name="dirxml"></a><span data-ttu-id="c84be-216">dirxml</span><span class="sxs-lookup"><span data-stu-id="c84be-216">dirxml</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-217">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-217">Console syntax</span></span>  

```console
dirxml(object)
```  

<span data-ttu-id="c84be-218">このコマンドは、[要素] ツールに表示される、指定したオブジェクトの XML 表現 **を出力** します。</span><span class="sxs-lookup"><span data-stu-id="c84be-218">This command prints an XML representation of the specified object, as displayed in the **Elements** tool.</span></span>  <span data-ttu-id="c84be-219">このメソッドは [console.dirxml() メソッドと同][MdnDocsWebApiConsoleDirxml] じです。</span><span class="sxs-lookup"><span data-stu-id="c84be-219">This method is equivalent to the [console.dirxml()][MdnDocsWebApiConsoleDirxml] method.</span></span>  

---  

## <a name="inspect"></a><span data-ttu-id="c84be-220">検査</span><span class="sxs-lookup"><span data-stu-id="c84be-220">inspect</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-221">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-221">Console syntax</span></span>  

```console
inspect(object/method)
```  

<span data-ttu-id="c84be-222">このコマンドは、適切なパネルで指定された要素またはオブジェクト (DOM 要素\*\*\*\* の要素ツールまたは JavaScript\*\*\*\* ヒープ オブジェクトのメモリ ツール) を開いて選択します。</span><span class="sxs-lookup"><span data-stu-id="c84be-222">This command opens and chooses the specified element or object in the appropriate panel:  either the **Elements** tool for DOM elements or the **Memory** tool for JavaScript heap objects.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-223">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-223">Console example</span></span>  

<span data-ttu-id="c84be-224">次のコード サンプルと図では、要素 `document.body` ツールで **開** きます。</span><span class="sxs-lookup"><span data-stu-id="c84be-224">In the following code sample and figure, the `document.body` opens in the **Elements** tool.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-225">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-225">Console example</span></span>  

```console
inspect(document.body);
```  

:::image type="complex" source="../media/console-inspect-document-body.msft.png" alt-text="inspect() を使用して要素を検査する" lightbox="../media/console-inspect-document-body.msft.png":::
   <span data-ttu-id="c84be-227">を使用して要素を検査する</span><span class="sxs-lookup"><span data-stu-id="c84be-227">Inspecting an element with</span></span> `inspect()`  
:::image-end:::  

<span data-ttu-id="c84be-228">検査するメソッドを渡す場合、メソッドは[ソース]\*\*\*\* ツールで Web ページを開き、検査を行います。</span><span class="sxs-lookup"><span data-stu-id="c84be-228">When passing a method to inspect, the method opens the webpage in the **Sources** tool for you to inspect.</span></span>  

---  

## <a name="geteventlisteners"></a><span data-ttu-id="c84be-229">getEventListeners</span><span class="sxs-lookup"><span data-stu-id="c84be-229">getEventListeners</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-230">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-230">Console syntax</span></span>  

```console
getEventListeners(object)
```  

<span data-ttu-id="c84be-231">このコマンドは、指定したオブジェクトに登録されているイベント リスナーを返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-231">This command returns the event listeners registered on the specified object.</span></span>  <span data-ttu-id="c84be-232">戻り値は、登録されているイベントの種類 \(または \など) ごとに配列を含む `click` オブジェクト `keydown` です。</span><span class="sxs-lookup"><span data-stu-id="c84be-232">The return value is an object that contains an array for each registered event type \(such as `click` or `keydown`\).</span></span>  <span data-ttu-id="c84be-233">各配列のメンバーは、各型に登録されているリスナーを表すオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c84be-233">The members of each array are objects that describe the listener registered for each type.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-234">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-234">Console example</span></span>  

<span data-ttu-id="c84be-235">次のコード スニペットと図では、オブジェクトに登録されているイベント リスナーすべてが `document` 一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-235">In the following code snippet and figure, all of the event listeners registered on the `document` object are listed.</span></span>  

```console
getEventListeners(document);
```  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png" alt-text="getEventListeners(document) の使用の出力" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document.msft.png":::
   <span data-ttu-id="c84be-237">使用の結果</span><span class="sxs-lookup"><span data-stu-id="c84be-237">The result of using</span></span> `getEventListeners(document)`  
:::image-end:::  

<span data-ttu-id="c84be-238">指定したオブジェクトに複数のリスナーが登録されている場合、配列にはリスナーごとにメンバーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="c84be-238">If more than one listener is registered on the specified object, then the array contains a member for each listener.</span></span>  <span data-ttu-id="c84be-239">次の図では、2 つのイベント リスナーがイベント `document` の要素に登録 `click` されています。</span><span class="sxs-lookup"><span data-stu-id="c84be-239">In the following figure, two event listeners are registered on the `document` element for the `click` event.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png" alt-text="複数のリスナー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-expanded-1.msft.png":::
   <span data-ttu-id="c84be-241">複数のリスナー</span><span class="sxs-lookup"><span data-stu-id="c84be-241">Multiple listeners</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-242">次の各オブジェクトをさらに展開して、プロパティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c84be-242">You may further expand each of the following objects to explore the properties.</span></span>  

:::image type="complex" source="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png" alt-text="リスナー オブジェクトの拡張ビュー" lightbox="../media/console-elements-event-listeners-console-get-event-listeners-document-2.msft.png":::
   <span data-ttu-id="c84be-244">リスナー オブジェクトの拡張ビュー</span><span class="sxs-lookup"><span data-stu-id="c84be-244">Expanded view of listener object</span></span>  
:::image-end:::  

---  

## <a name="keys"></a><span data-ttu-id="c84be-245">キー</span><span class="sxs-lookup"><span data-stu-id="c84be-245">keys</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-246">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-246">Console syntax</span></span>  

```console
keys(object)
```  

<span data-ttu-id="c84be-247">このコマンドは、指定したオブジェクトに属するプロパティの名前を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-247">This command returns an array containing the names of the properties belonging to the specified object.</span></span>  <span data-ttu-id="c84be-248">同じプロパティの関連する値を取得するには、 を使用します `values()` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-248">To get the associated values of the same properties, use `values()`.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-249">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-249">Console example</span></span>  

<span data-ttu-id="c84be-250">たとえば、アプリケーションが次のオブジェクトを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="c84be-250">For example, suppose your application defined the following object.</span></span>  

```console
var player1 = {"name": "Ted", "level": 42}
```  

<span data-ttu-id="c84be-251">次のコード サンプルと図では、入力する前とコンソールでグローバル名前空間 `player1` \(簡易\) で定義されたと `keys(player1)` `values(player1)` 仮定します。</span><span class="sxs-lookup"><span data-stu-id="c84be-251">In the following code samples and figure, the result assumes `player1` was defined in the global namespace \(for simplicity\) before you type `keys(player1)` and `values(player1)` in the console.</span></span>  

```console
keys(player1)

values(player1)
```  

:::image type="complex" source="../media/console-keys-values.msft.png" alt-text="keys() コマンドと values() コマンド" lightbox="../media/console-keys-values.msft.png":::
   <span data-ttu-id="c84be-253">and `keys()` `values()` コマンド</span><span class="sxs-lookup"><span data-stu-id="c84be-253">The `keys()` and `values()` commands</span></span>  
:::image-end:::  

---  

## <a name="monitor"></a><span data-ttu-id="c84be-254">モニター</span><span class="sxs-lookup"><span data-stu-id="c84be-254">monitor</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-255">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-255">Console syntax</span></span>  

```console
monitor(method)
```  

<span data-ttu-id="c84be-256">このコマンドは、メソッド名と、要求の一部としてメソッドに渡される引数を示すメッセージをコンソールにログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c84be-256">This command logs a message to the console that indicates the method name along with the arguments passed to the method as part of a request.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-257">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-257">Console example</span></span>  

```console
function sum(x, y) {
    return x + y;
}
monitor(sum);
```  

:::image type="complex" source="../media/console-function-monitor-sum.msft.png" alt-text="monitor() メソッド" lightbox="../media/console-function-monitor-sum.msft.png":::
   <span data-ttu-id="c84be-259">メソッド `monitor()`</span><span class="sxs-lookup"><span data-stu-id="c84be-259">The `monitor()` method</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-260">監視 `unmonitor(method)` を終了するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c84be-260">Use `unmonitor(method)` to end monitoring.</span></span>  

---  

## <a name="monitorevents"></a><span data-ttu-id="c84be-261">monitorEvents</span><span class="sxs-lookup"><span data-stu-id="c84be-261">monitorEvents</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-262">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-262">Console syntax</span></span>  

```console
monitorEvents(object[, events])
```  

<span data-ttu-id="c84be-263">指定したオブジェクトで指定されたイベントの 1 つが発生すると、イベント オブジェクトはコンソールに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-263">When one of the specified events occurs on the specified object, the event object is logged to the console.</span></span>  <span data-ttu-id="c84be-264">監視する 1 つのイベント、イベントの配列、または定義済みのイベント のコレクションにマップされる一般的なイベントの種類のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c84be-264">You may specify a single event to monitor, an array of events, or one of the generic events types that are mapped to a predefined collection of events.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-265">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-265">Console example</span></span>  

<span data-ttu-id="c84be-266">次のコード サンプルと図を確認します。</span><span class="sxs-lookup"><span data-stu-id="c84be-266">Review the following code sample and figure.</span></span>  

<span data-ttu-id="c84be-267">次に、window オブジェクト上のすべてのサイズ変更イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="c84be-267">The following monitors all resize events on the window object.</span></span>  

```console
monitorEvents(window, "resize");
```  

:::image type="complex" source="../media/console-monitor-events-resize-window.msft.png" alt-text="ウィンドウのサイズ変更イベントの監視" lightbox="../media/console-monitor-events-resize-window.msft.png":::
   <span data-ttu-id="c84be-269">ウィンドウのサイズ変更イベントの監視</span><span class="sxs-lookup"><span data-stu-id="c84be-269">Monitoring window resize events</span></span>  
:::image-end:::  

<span data-ttu-id="c84be-270">次のコード スニペットは、window オブジェクトの両方とイベントを監視 `resize` `scroll` する配列を定義します。</span><span class="sxs-lookup"><span data-stu-id="c84be-270">The following code snippet defines an array to monitor both `resize` and `scroll` events on the window object.</span></span>  

```console
monitorEvents(window, ["resize", "scroll"]);
```  

<span data-ttu-id="c84be-271">使用可能なイベントの種類の 1 つ、定義済みのイベント セットにマップする文字列を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c84be-271">You may also specify one of the available types of events, strings that map to predefined sets of events.</span></span>  <span data-ttu-id="c84be-272">次の表に、使用可能なイベントの種類と関連付けられたイベント マッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="c84be-272">The following table displays the available event types and the associated event mappings.</span></span>  

| <span data-ttu-id="c84be-273">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="c84be-273">Event type</span></span> | <span data-ttu-id="c84be-274">対応するマップされたイベント</span><span class="sxs-lookup"><span data-stu-id="c84be-274">Corresponding mapped events</span></span> |  
|:--- |:--- |  
| `mouse` | <span data-ttu-id="c84be-275">"click"、"dblclick"、"mousedown"、"mousemove"、"mouseout"、"mouseover"、"mouseup"、"mousewheel"</span><span class="sxs-lookup"><span data-stu-id="c84be-275">"click", "dblclick", "mousedown", "mousemove", "mouseout", "mouseover", "mouseup", "mousewheel"</span></span> |  
| `key` | <span data-ttu-id="c84be-276">"keydown"、"keypress"、"keyup"、"textInput"</span><span class="sxs-lookup"><span data-stu-id="c84be-276">"keydown", "keypress", "keyup", "textInput"</span></span> |  
| `touch` | <span data-ttu-id="c84be-277">"touchcancel", "touchend", "touchmove", "touchstart"</span><span class="sxs-lookup"><span data-stu-id="c84be-277">"touchcancel", "touchend", "touchmove", "touchstart"</span></span> |  
| `control` | <span data-ttu-id="c84be-278">"ぼかし"、"change"、"focus"、"reset"、"resize"、"scroll"、"select"、"submit"、"zoom"</span><span class="sxs-lookup"><span data-stu-id="c84be-278">"blur", "change", "focus", "reset", "resize", "scroll", "select", "submit", "zoom"</span></span> |  

<span data-ttu-id="c84be-279">次のコード サンプルでは、入力テキスト フィールドのイベントに対応するイベントの種類が現在、要素 `key` `key` ツールで **選択** されています。</span><span class="sxs-lookup"><span data-stu-id="c84be-279">In the following code sample, the `key` event type corresponding to `key` events on an input text field are currently chosen in the **Elements** tool.</span></span>  

```console
monitorEvents($0, "key");
```  

<span data-ttu-id="c84be-280">次の図では、テキスト フィールドに文字を入力した後の出力例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-280">In the following figure, the sample output after typing a character in the text field is displayed.</span></span>  

:::image type="complex" source="../media/console-monitor-events-type-t-y.msft.png" alt-text="主要なイベントの監視" lightbox="../media/console-monitor-events-type-t-y.msft.png":::
   <span data-ttu-id="c84be-282">主要なイベントの監視</span><span class="sxs-lookup"><span data-stu-id="c84be-282">Monitoring key events</span></span>  
:::image-end:::  

---  

## <a name="profile"></a><span data-ttu-id="c84be-283">profile</span><span class="sxs-lookup"><span data-stu-id="c84be-283">profile</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-284">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-284">Console syntax</span></span>  

```console
profile([name])
```  

<span data-ttu-id="c84be-285">このコマンドは、オプションの名前で JavaScript CPU プロファイリング セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c84be-285">This command starts a JavaScript CPU profiling session with an optional name.</span></span>  <span data-ttu-id="c84be-286">[profileEnd() メソッドは](#profileend)プロファイルを完了し、結果を Memory ツールに**表示**します。</span><span class="sxs-lookup"><span data-stu-id="c84be-286">The [profileEnd()](#profileend) method completes the profile and displays the results in the **Memory** tool.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a><span data-ttu-id="c84be-287">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-287">Console example</span></span>  

1.  <span data-ttu-id="c84be-288">プロファイリングを `profile()` 開始するには、メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c84be-288">Run the `profile()` method to start profiling.</span></span>  
    
    ```console
    profile("My profile")
    ```  
    
1.  <span data-ttu-id="c84be-289">[profileEnd() メソッド](#profileend)を実行してプロファイリングを停止し、結果を Memory ツールに**表示**します。</span><span class="sxs-lookup"><span data-stu-id="c84be-289">Run the [profileEnd()](#profileend) method to stop profiling and display the results in the **Memory** tool.</span></span>  

<span data-ttu-id="c84be-290">プロファイルは入れ子にされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c84be-290">Profiles may also be nested.</span></span>  <span data-ttu-id="c84be-291">次のコード サンプルと図では、結果は順序が同じです。</span><span class="sxs-lookup"><span data-stu-id="c84be-291">In the following code samples and figure, the result is the same whatever the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

> [!NOTE]
> <span data-ttu-id="c84be-292">複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c84be-292">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

---  

## <a name="profileend"></a><span data-ttu-id="c84be-293">profileEnd</span><span class="sxs-lookup"><span data-stu-id="c84be-293">profileEnd</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-294">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-294">Console syntax</span></span>  

```console
profileEnd([name])
```  

<span data-ttu-id="c84be-295">このコマンドは、JavaScript CPU プロファイリング セッションを完了し、結果をメモリ ツールに **表示** します。</span><span class="sxs-lookup"><span data-stu-id="c84be-295">This command completes a JavaScript CPU profiling session and displays the results in the **Memory** tool.</span></span>  <span data-ttu-id="c84be-296">[profile() メソッドを実行している必要](#profile)があります。</span><span class="sxs-lookup"><span data-stu-id="c84be-296">You must be running the [profile()](#profile) method.</span></span>  <!--Navigate to [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJsRuntime].  -->  

### <a name="console-example"></a><span data-ttu-id="c84be-297">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-297">Console example</span></span>  

1.  <span data-ttu-id="c84be-298">[profile() メソッドを実行](#profile)してプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="c84be-298">Run the [profile()](#profile) method to start profiling.</span></span>  
1.  <span data-ttu-id="c84be-299">このメソッド `profileEnd()` を実行して、プロファイリングを停止し、結果をメモリ ツールに **表示** します。</span><span class="sxs-lookup"><span data-stu-id="c84be-299">Run the `profileEnd()` method to stop profiling and display the results in the **Memory** tool.</span></span>  
    
    ```console
    profileEnd("My profile")
    ```  

<span data-ttu-id="c84be-300">プロファイルは入れ子にされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c84be-300">Profiles may also be nested.</span></span>  <span data-ttu-id="c84be-301">次のコード サンプルと図では、結果は順序が同じです。</span><span class="sxs-lookup"><span data-stu-id="c84be-301">In the following code sample and figure, the result is the same whatever the order.</span></span>  

```console
profile('A');
profile('B');
profileEnd('A');
profileEnd('B');
```  

<span data-ttu-id="c84be-302">結果は、メモリ ツールのヒープ スナップショットとして **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-302">The result appears as a Heap Snapshot in the **Memory** tool.</span></span>  

:::image type="complex" source="../media/console-memory-multiple-cpu-profiles.msft.png" alt-text="グループ化されたプロファイル" lightbox="../media/console-memory-multiple-cpu-profiles.msft.png":::
   <span data-ttu-id="c84be-304">グループ化されたプロファイル</span><span class="sxs-lookup"><span data-stu-id="c84be-304">Grouped profiles</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c84be-305">複数の CPU プロファイルが同時に動作する場合があります。作成順序で各 CPU プロファイルを閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c84be-305">Multiple CPU profiles may operate at the same time and you are not required to close-out each one in creation order.</span></span>  

---  

## <a name="queryobjects"></a><span data-ttu-id="c84be-306">queryObjects</span><span class="sxs-lookup"><span data-stu-id="c84be-306">queryObjects</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-307">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-307">Console syntax</span></span>  

```console
queryObjects(Constructor)
```  

<span data-ttu-id="c84be-308">このコマンドは、指定したコンストラクターで作成されたオブジェクトの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-308">This command returns an array of objects created with the specified constructor.</span></span>  <span data-ttu-id="c84be-309">スコープは `queryObjects()` 、コンソールで現在選択されているランタイム コンテキスト **です**。</span><span class="sxs-lookup"><span data-stu-id="c84be-309">The scope of `queryObjects()` is the currently chosen runtime context in the **Console**.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-310">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-310">Console example</span></span>  

:::row:::
   :::column span="1":::
      ```console
      queryObjects(promise)
      ```  
      
      <span data-ttu-id="c84be-311">all を返します `Promises` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-311">Returns all `Promises`.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(HTMLElement)
      ```  
      
      <span data-ttu-id="c84be-312">すべての HTML 要素を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-312">Returns all HTML elements.</span></span>  
   :::column-end:::
   :::column span="1":::
      ```console
      queryObjects(functionName)
      ```  
      
      <span data-ttu-id="c84be-313">を使用してインスタンス化されたすべてのオブジェクトを返します `new functionName()` 。</span><span class="sxs-lookup"><span data-stu-id="c84be-313">Returns all objects that were instantiated using `new functionName()`.</span></span>  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="c84be-314">table</span><span class="sxs-lookup"><span data-stu-id="c84be-314">table</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-315">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-315">Console syntax</span></span>  

```console
table(data[, columns])
```  

<span data-ttu-id="c84be-316">このコマンドは、オプションの列見出しを使用して、データ オブジェクトに基づいてテーブルの書式設定を使用してオブジェクト データをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c84be-316">This command logs object data with table formatting based upon the data object in with optional column headings.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-317">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-317">Console example</span></span>  

<span data-ttu-id="c84be-318">次のコード サンプルと図では、コンソール内のテーブルを使用する名前の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-318">In the following code sample and figure, a list of names using a table in the console is displayed.</span></span>  

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
   <span data-ttu-id="c84be-320">メソッドの `table()` 結果</span><span class="sxs-lookup"><span data-stu-id="c84be-320">The result of the `table()` method</span></span>  
:::image-end:::  

---  

## <a name="undebug"></a><span data-ttu-id="c84be-321">undebug</span><span class="sxs-lookup"><span data-stu-id="c84be-321">undebug</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-322">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-322">Console syntax</span></span>  

```console
undebug(method)
```  

<span data-ttu-id="c84be-323">このコマンドは、指定されたメソッドのデバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="c84be-323">This command stops the debug of the specified method.</span></span> <span data-ttu-id="c84be-324">そのため、メソッドが要求されると、デバッガーは呼び出されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c84be-324">So when the method is requested, the debugger is no longer invoked.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-325">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-325">Console example</span></span>  

```console
undebug(getData);
```  

---  

## <a name="unmonitor"></a><span data-ttu-id="c84be-326">unmonitor</span><span class="sxs-lookup"><span data-stu-id="c84be-326">unmonitor</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-327">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-327">Console syntax</span></span>  

```console
unmonitor(method)
```  

<span data-ttu-id="c84be-328">このコマンドは、指定されたメソッドの監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="c84be-328">This command stops the monitoring of the specified method.</span></span>  <span data-ttu-id="c84be-329">このメソッドは monitor() メソッドと一 [緒に使用](#monitor) されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-329">This method is used in concert with the [monitor()](#monitor) method.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-330">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-330">Console example</span></span>  

```console
unmonitor(getData);
```  

---  

## <a name="unmonitorevents"></a><span data-ttu-id="c84be-331">unmonitorEvents</span><span class="sxs-lookup"><span data-stu-id="c84be-331">unmonitorEvents</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-332">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-332">Console syntax</span></span>  

```console
unmonitorEvents(object[, events])
```  

<span data-ttu-id="c84be-333">このコマンドは、指定されたオブジェクトとイベントの監視イベントを停止します。</span><span class="sxs-lookup"><span data-stu-id="c84be-333">This command stops monitoring events for the specified object and events.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-334">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-334">Console example</span></span>  

<span data-ttu-id="c84be-335">たとえば、次のコード スニペットは、window オブジェクト上のすべてのイベント監視を停止します。</span><span class="sxs-lookup"><span data-stu-id="c84be-335">For example, the following code snippet stops all event monitoring on the window object.</span></span>  

```console
unmonitorEvents(window);
```  

<span data-ttu-id="c84be-336">また、オブジェクトの特定のイベントの監視を選択的に停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="c84be-336">You may also selectively stop monitoring specific events on an object.</span></span>  <span data-ttu-id="c84be-337">たとえば、次のコードは、現在選択されている要素のすべてのイベントの監視を開始し、イベントの監視を停止します \(コンソール出力のノイズを低減 `mouse` `mousemove` する可能性があります\)。</span><span class="sxs-lookup"><span data-stu-id="c84be-337">For example, the following code starts monitoring all `mouse` events on the currently chosen element, and then stops monitoring `mousemove` events \(perhaps to reduce noise in the console output\).</span></span>  

```console
monitorEvents($0, "mouse");
unmonitorEvents($0, "mousemove");
```  

---  

## <a name="values"></a><span data-ttu-id="c84be-338">値</span><span class="sxs-lookup"><span data-stu-id="c84be-338">values</span></span>  

### <a name="console-syntax"></a><span data-ttu-id="c84be-339">コンソール構文</span><span class="sxs-lookup"><span data-stu-id="c84be-339">Console syntax</span></span>  

```console
values(object)
```  

<span data-ttu-id="c84be-340">このコマンドは、指定したオブジェクトに属するすべてのプロパティの値を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c84be-340">This command returns an array containing the values of all properties belonging to the specified object.</span></span>  

### <a name="console-example"></a><span data-ttu-id="c84be-341">コンソールの例</span><span class="sxs-lookup"><span data-stu-id="c84be-341">Console example</span></span>  

```console
values(object);
```  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c84be-342">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c84be-342">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleApiConsoleDirObject]: ./api.md#dir "dir - コンソール API リファレンス |Microsoft Docs"  

[DevtoolsJavascriptBreakpoints]: ../javascript/breakpoints.md "DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"  

[DevtoolsRenderingToolsJsRuntime]: ../rendering-tools/js-runtime.md "JavaScript ランタイム の高速化|Microsoft Docs"  

[CR1050237]: https://crbug.com/1050237 "問題 1050237: debug(function) が動作|Chromiumバグ"  

[MdnDocsWebApiConsoleDir]: https://developer.mozilla.org/docs/Web/API/Console/dir "Console.dir() |MDN"  
[MdnDocsWebApiConsoleDirxml]: https://developer.mozilla.org/docs/Web/API/Console/dirxml "Console.dirxml() |MDN"  
[MdnDocsWebApiDocumentQueryselector]: https://developer.mozilla.org/docs/Web/API/Document/querySelector "Document.querySelector() |MDN"  
[MdnDocsWebApiDocumentQueryselectorall]: https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll "Document.querySelectorAll() |MDN"  

> [!NOTE]
> <span data-ttu-id="c84be-352">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c84be-352">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c84be-353">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/utilities) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c84be-353">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/utilities) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c84be-355">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c84be-355">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
