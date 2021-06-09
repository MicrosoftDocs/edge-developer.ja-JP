---
description: コンソール ツールを使用してブラウザーで現在の Web ページを操作する方法の概要
title: コンソールを使用して DOM を操作する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 56ce6b1d8f1ad98eeb9c141c2e9b002e7679d7de
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597016"
---
# <a name="use-the-console-to-interact-with-the-dom"></a><span data-ttu-id="8c5ba-104">コンソールを使用して DOM を操作する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-104">Use the Console to interact with the DOM</span></span>

<span data-ttu-id="8c5ba-105">コンソール **ツール** は、情報をログに [記録][DevtoolsConsoleConsoleLog] したり、任意の JavaScript を [実行したりするだけのツールではない][DevtoolsConsoleConsoleJavascript]。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-105">The **Console** tool isn't only for [logging information][DevtoolsConsoleConsoleLog] or to [run arbitrary JavaScript][DevtoolsConsoleConsoleJavascript].</span></span>  <span data-ttu-id="8c5ba-106">また、ブラウザーで Web ページを操作する場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-106">It also is a great way to interact with the webpage in the browser.</span></span>  <span data-ttu-id="8c5ba-107">スクリプト環境バージョンの Inspect ツールと **考** えます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-107">Consider it a script-environment version of the **Inspect** tool.</span></span>  

## <a name="read-from-the-dom"></a><span data-ttu-id="8c5ba-108">DOM から読み取る</span><span class="sxs-lookup"><span data-stu-id="8c5ba-108">Read from the DOM</span></span>

<span data-ttu-id="8c5ba-109">Web ページのヘッダーを参照するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-109">To reference the header of the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-110">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-110">Open the **Console**.</span></span>
    *   <span data-ttu-id="8c5ba-111">`Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-111">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="8c5ba-112">コンソールに次のコード スニペットを入力またはコピーして貼り **付けます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-112">Type or copy and paste the following code snippet in the **Console**.</span></span>  
    
    ```javascript
    document.querySelector('header')
    ```  
    
:::image type="complex" source="../media/console-dom-get-reference.msft.png" alt-text="コンソールでヘッダーへの参照を取得するには、document.querySelector を使用します。" lightbox="../media/console-dom-get-reference.msft.png":::
    <span data-ttu-id="8c5ba-114">コンソールでヘッダーへの参照を取得するには、</span><span class="sxs-lookup"><span data-stu-id="8c5ba-114">To get a reference to the header in console, use</span></span> `document.querySelector`  
:::image-end:::  

<span data-ttu-id="8c5ba-115">HTML 結果の `Shift` + `Tab` 上でマウス カーソルを選択または移動すると、DevTools によってヘッダーが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-115">If you select `Shift`+`Tab` or move your mouse cursor over the HTML result, DevTools highlights the header for you.</span></span>  

:::image type="complex" source="../media/console-dom-highlight-element.msft.png" alt-text="DevTools は、コンソールで選択したセクションを強調表示します。" lightbox="../media/console-dom-highlight-element.msft.png":::
    <span data-ttu-id="8c5ba-117">DevTools は、コンソールで選択したセクションを強調表示 **します。**</span><span class="sxs-lookup"><span data-stu-id="8c5ba-117">DevTools highlights the section you choose in the **Console**</span></span>  
:::image-end:::  

## <a name="manipulate-the-dom"></a><span data-ttu-id="8c5ba-118">DOM を操作する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-118">Manipulate the DOM</span></span>

<span data-ttu-id="8c5ba-119">Web ページも操作できます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-119">You may manipulate the webpage, too.</span></span>  <span data-ttu-id="8c5ba-120">たとえば、次をコピーして貼り付けるか、コンソールに\*\*\*\* 入力すると、ヘッダーの周囲に緑色の枠線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-120">For example, if you copy and paste or type the following into the **Console**, a green border displays around the header.</span></span>

```javascript
document.querySelector('header').style.border = '2em solid green'
```  

:::image type="complex" source="../media/console-dom-add-border.msft.png" alt-text="要素に罫線を追加するには、コンソールを使用します。" lightbox="../media/console-dom-add-border.msft.png":::
    <span data-ttu-id="8c5ba-122">要素に罫線を追加するには、コンソールを使用 **します。**</span><span class="sxs-lookup"><span data-stu-id="8c5ba-122">To add a border to an element, use the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-123">Web ページの複雑さによっては、操作する適切な要素を見つけるのが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-123">Depending on the complexity of the webpage, It may be daunting to find the right element to manipulate.</span></span>  <span data-ttu-id="8c5ba-124">ただし、検査ツールを **使用して** 役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-124">But you may use the **Inspect** tool to help you.</span></span>  <span data-ttu-id="8c5ba-125">ヘッダー内のパーツを `Documentation` 操作するとします。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-125">Say you want to manipulate the `Documentation` part in the header.</span></span>

:::image type="complex" source="../media/console-dom-highlight-documentation.msft.png" alt-text="画面に検査する要素を表示する" lightbox="../media/console-dom-highlight-documentation.msft.png":::
    <span data-ttu-id="8c5ba-127">画面に検査する要素を表示する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-127">Display the element that you inspect on the screen</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-128">操作する要素への直接参照を取得するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-128">To get a direct reference to the element to manipulate, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-129">要素を **選択するには、[検査** ] ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-129">Use the **Inspect** tool to choose the element.</span></span>  

    :::image type="complex" source="../media/console-dom-use-inspector-to-get-element.msft.png" alt-text="要素を選択するには、[検査] ツールを使用します。" lightbox="../media/console-dom-use-inspector-to-get-element.msft.png":::
        <span data-ttu-id="8c5ba-131">要素を選択するには、[検査] ツール **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-131">To choose an element, use the **Inspect** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8c5ba-132">選択すると、DevTools が要素ツールに **ジャンプ** します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-132">Choose it and DevTools jumps to the **Elements** tool.</span></span>  
1.  <span data-ttu-id="8c5ba-133">DOM ツリー `...` の要素の横にあるメニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-133">Choose the `...` menu next to the element in the DOM tree.</span></span>  
    
    :::image type="complex" source="../media/console-dom-overflow-menu-in-elements.msft.png" alt-text="選択した要素が Elements ツールの DOM ツリーに表示され、オーバーフロー メニューを選択してより多くの機能を取得します" lightbox="../media/console-dom-overflow-menu-in-elements.msft.png":::
        <span data-ttu-id="8c5ba-135">選択した要素が Elements ツールの DOM ツリーに **表示され、** オーバーフロー メニューを選択してより多くの機能を取得します</span><span class="sxs-lookup"><span data-stu-id="8c5ba-135">The chosen element displays in the DOM tree of the **Elements** tool, choose the overflow menu to get more features</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8c5ba-136">コンテキスト メニューを開き、[. `Copy`  >  `Copy JS Path`</span><span class="sxs-lookup"><span data-stu-id="8c5ba-136">Open the contextual menu and choose `Copy` > `Copy JS Path`.</span></span>  
    
    :::image type="complex" source="../media/console-dom-copy-JS-path.msft.png" alt-text="要素ツールの DOM ツリー内の要素から JavaScript パスをコピーする" lightbox="../media/console-dom-copy-JS-path.msft.png":::
        <span data-ttu-id="8c5ba-138">要素ツールの DOM ツリー内の要素から JavaScript パスを **コピー** する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-138">Copy the JavaScript path from an element in the DOM tree of the **Elements** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8c5ba-139">コンソールに戻り **、** コマンドを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-139">Go back to the **Console** and paste the command.</span></span>  
    
<span data-ttu-id="8c5ba-140">リンクのテキストをに変更するには `My Playground` 、以前に貼 `.textContent = "My Playground"` り付けしたコマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-140">To change the text of the link to `My Playground`, add `.textContent = "My Playground"` to the command you previously pasted.</span></span>  

:::image type="complex" source="../media/console-dom-change-content.msft.png" alt-text="コンソールを使用して要素のコンテンツを変更する" lightbox="../media/console-dom-change-content.msft.png":::
    <span data-ttu-id="8c5ba-142">コンソールを **使用して** 要素のコンテンツを変更する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-142">Use the **Console** to change the content of an element</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-143">コンソールで実行する JavaScript DOM 操作を使用 **します**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-143">Use any JavaScript DOM manipulations you want to do in the **Console**.</span></span>  <span data-ttu-id="8c5ba-144">使い方を便利にするために、 **コンソールには** いくつかのヘルパー メソッドが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-144">To make it more convenient, the **Console** comes with a few helper methods.</span></span>  

## <a name="helpful-console-utility-methods"></a><span data-ttu-id="8c5ba-145">便利なコンソール ユーティリティメソッド</span><span class="sxs-lookup"><span data-stu-id="8c5ba-145">Helpful Console utility methods</span></span>  

<span data-ttu-id="8c5ba-146">多くの便利な方法とショートカットは、コンソール ユーティリティ [として使用できます][DevtoolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-146">Many convenience methods and shortcuts are available to you as [Console Utilities][DevtoolsConsoleUtilities].</span></span>  <span data-ttu-id="8c5ba-147">いくつかのメソッドは非常に強力で、おそらく過去に一連のステートメントとして `console.log()` 書いたものです。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-147">Some of the methods are incredibly powerful and are things you probably wrote as a series of `console.log()` statements in the past.</span></span>

### <a name="the-power-to-the-"></a><span data-ttu-id="8c5ba-148">$ のパワー</span><span class="sxs-lookup"><span data-stu-id="8c5ba-148">The power to the $</span></span>

<span data-ttu-id="8c5ba-149">コンソール `$` には特別な機能があります\*\*\*\*。jQueryから覚えている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-149">The `$` has special powers in **Console** and you may remember that from jQuery.</span></span>

*   `$_` <span data-ttu-id="8c5ba-150">最後のコマンドの結果を格納します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-150">stores the result of the last command.</span></span>  <span data-ttu-id="8c5ba-151">したがって、入力して選択 `2 + 2` し `Enter` 、次に入力 `$_` すると、 **コンソールに表示** されます `4` 。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-151">So, if you type `2 + 2` and select `Enter`, and then type `$_`, the **Console** displays you `4`.</span></span>
*   `$0` <span data-ttu-id="8c5ba-152">to `$4` は、最後に検査された要素のスタックが `$0` 常に最新の要素です。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-152">to `$4` is a stack of the last inspected elements `$0` is always the newest one.</span></span>  <span data-ttu-id="8c5ba-153">したがって、前の例では、同じ効果を得る\*\*\*\* 検査ツールと入力で要素 `$0.textContent = "My Playground"` を選択しました。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-153">So in the earlier example, you just chose the element in the **Inspect** tool and type `$0.textContent = "My Playground"` to get the same effect.</span></span>
*   `$x()` <span data-ttu-id="8c5ba-154">を使用すると、XPATH を使用して DOM 要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-154">allows you to choose DOM elements using XPATH.</span></span>
*   `$()` <span data-ttu-id="8c5ba-155">と `$$()` の短いバージョン `document.querySelector()` です `document.querySelectorAll()` 。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-155">and `$$()` are shorter versions of for `document.querySelector()` and `document.querySelectorAll()`.</span></span>  
    
<span data-ttu-id="8c5ba-156">たとえば、次のコード スニペットは、web ページ内のすべてのリンクを取得し(\の短い場合)、リンクを並べ替え可能なテーブルとして表示して、たとえば、Excel にコピーして貼 `$$('a')` `document.querySelectorAll('a')` り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-156">For example, the following code snippet retrieves all the links in the webpage \(as `$$('a')` is short for `document.querySelectorAll('a')`\) and displays the links as a sortable table to copy and paste, for example, into Excel.</span></span>

```javascript
console.table($$('a'),['href','text']);
```  

:::image type="complex" source="../media/console-dom-get-all-links.msft.png" alt-text="Web ページ内のすべてのリンクを取得し、結果を表として表示する" lightbox="../media/console-dom-get-all-links.msft.png":::
    <span data-ttu-id="8c5ba-158">Web ページ内のすべてのリンクを取得し、結果を表として表示する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-158">Get all links in the webpage and display the result as a table</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-159">ただし、情報を表示したくないが、データとして取得する場合。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-159">However, if you don't want to display the information, but you want to grab it as data.</span></span>  <span data-ttu-id="8c5ba-160">この `$$('a')` ショートカットは、アンカー リンクと各プロパティのすべてのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-160">The `$$('a')` shortcut provides the anchor links and all of the properties for each one.</span></span>  <span data-ttu-id="8c5ba-161">問題は、リンクと関連するテキストだけが必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-161">The problem is that you only want the links and the related text.</span></span>  

:::image type="complex" source="../media/console-dom-too-much-link-information.msft.png" alt-text="$$ ショートカットは、あまりにも多くの情報を返します" lightbox="../media/console-dom-too-much-link-information.msft.png":::
    <span data-ttu-id="8c5ba-163">ショートカット `$$` が戻す情報が多すぎます</span><span class="sxs-lookup"><span data-stu-id="8c5ba-163">The `$$` shortcut returns far too much information</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-164">ショートカット `$$` には興味深い追加機能があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-164">The `$$` shortcut has an interesting extra feature.</span></span>  <span data-ttu-id="8c5ba-165">純粋な方法を返す代わりに、ショートカットを使用すると `NodeList` `document.querySelectorAll()` `$$` 、すべてのメソッドが `Array` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-165">Instead of returning a pure `NodeList` like `document.querySelectorAll()`, the `$$` shortcut gives you all of the `Array` methods.</span></span>  <span data-ttu-id="8c5ba-166">必要 `map()` な情報に情報を減らすには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-166">Use `map()` method to reduce the information to what you need.</span></span>  

```javascript
$$('a').map(a => {
    return {url: a.href, text: a.innerText}
})
```  

<span data-ttu-id="8c5ba-167">コード スニペットは、すべてのリンクの配列をオブジェクトとプロパティとして `url` 返 `text` します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-167">The code snippet returns an Array of all the links as objects with `url` and `text` properties.</span></span>  

:::image type="complex" source="../media/console-dom-filter-link-data.msft.png" alt-text="$$ のマップを使用して最小限に情報をフィルター処理する" lightbox="../media/console-dom-filter-link-data.msft.png":::
    <span data-ttu-id="8c5ba-169">map on を `$$` 使用して最小限の情報にフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-169">Use map on `$$` to filter information down to the bare minimum</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-170">まだ行っていませんが、いくつかのリンクは Web ページへの内部リンクまたは空のテキストです。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-170">You aren't done yet, several links are internal links to the webpage or have empty text.</span></span>  <span data-ttu-id="8c5ba-171">内部リンクを削除するには、filter メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-171">Use the filter method to get rid of the internal links.</span></span>  

```javascript
$$('a').map(a => {
    return {text: a.innerText, url: a.href}
}).filter(a => {
    return a.text !== '' && !a.url.match('docs.microsoft.com')
})
```  

:::image type="complex" source="../media/console-dom-filter-out-empty-links.msft.png" alt-text="空でないリンクを取得し、外部リンクを取得する" lightbox="../media/console-dom-filter-out-empty-links.msft.png":::
    <span data-ttu-id="8c5ba-173">空でないリンクを取得し、外部リンクを取得する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-173">Get the links that aren't empty and are external</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-174">Web ページの最初に表示される通り、これらの要素を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-174">As displayed at the start of the webpage, you may also change these elements.</span></span>  <span data-ttu-id="8c5ba-175">たとえば、次のコード スニペットは、すべての外部リンクの周囲に緑の枠線を作成します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-175">For example, the following code snippet creates a green border around all external links:</span></span>

```javascript
$$('a[href^="https://"]').forEach(
  a => a.style.border = '1px solid green'
)
```  

:::image type="complex" source="../media/console-dom-highlight-links.msft.png" alt-text="すべての外部リンクを強調表示するには、各リンクの周囲に緑の枠線を追加します。" lightbox="../media/console-dom-highlight-links.msft.png":::
    <span data-ttu-id="8c5ba-177">すべての外部リンクを強調表示するには、各リンクの周囲に緑の枠線を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-177">To highlight all external links, add a green border around each</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-178">複雑な JavaScript を記述して結果をフィルター処理する代わりに、CSS セレクターの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-178">Instead of writing complex JavaScript to filter results, use the power of CSS selectors.</span></span>  

<span data-ttu-id="8c5ba-179">インライン イメージではない Web ページ上のすべてのイメージのテーブルと情報を作成するには、次 `src` `alt` のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-179">To create a table of the `src` and `alt` information for all images on the webpage that aren't inline images, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-180">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-180">Open the **Console**.</span></span>  
1.  <span data-ttu-id="8c5ba-181">次のコード スニペットを入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-181">Type or copy and paste the following code snippet.</span></span>  

```javascript
console.table($$('img:not([src^=data])'), ['src','alt'])
```  

:::image type="complex" source="../media/console-dom-complex-CSS-selector.msft.png" alt-text="要素を選択するには、複雑な CSS セレクターを使用します。" lightbox="../media/console-dom-complex-CSS-selector.msft.png":::
    <span data-ttu-id="8c5ba-183">要素を選択するには、複雑な CSS セレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-183">To choose elements, use a complex CSS selector</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-184">さらに複雑な例の準備はできましたか?</span><span class="sxs-lookup"><span data-stu-id="8c5ba-184">Ready for an even more complex example?</span></span>  <span data-ttu-id="8c5ba-185">この記事のようなマークダウンから生成された HTML Web ページには、各見出しの自動 ID 値が含まれるので、そのセクションへの深いリンクが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-185">HTML webpages generated from markdown like this article, have automatic ID values for each heading to allow you to deep link to that section.</span></span>  <span data-ttu-id="8c5ba-186">たとえば、 に `# New features` 対する変更 `<h1 id="new-features">New features</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-186">For example, a `# New features` changes to `<h1 id="new-features">New features</h1>`.</span></span>  

<span data-ttu-id="8c5ba-187">コピーして貼り付けるすべての自動見出しの一覧を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-187">To list of all of the automatic headings to copy and paste, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-188">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-188">Open the **Console**.</span></span>  
1.  <span data-ttu-id="8c5ba-189">次のコード スニペットを入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-189">Type or copy and paste the following code snippet.</span></span>  

```javascript
let out = '';
$$('#main [id]').filter(
    elm => {return elm.nodeName.startsWith('H')}
).forEach(elm => {
   out += elm.innerText + "\n" + 
          document.location.href + '#' +
          elm.id + "\n";
});
console.log(out);
```  

<span data-ttu-id="8c5ba-190">結果は、各見出しのコンテンツを含むテキストの後に、その見出しを示す完全な URL が続きます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-190">The result is text that contains content for each heading followed by the full URL that points to it.</span></span>  

:::image type="complex" source="../media/console-dom-get-generated-headings.msft.png" alt-text="Web ページからすべての見出しと生成された URL を取得する" lightbox="../media/console-dom-get-generated-headings.msft.png":::
    <span data-ttu-id="8c5ba-192">Web ページからすべての見出しと生成された URL を取得する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-192">Get all the headings and the generated URLs from the webpage</span></span>  
:::image-end:::  

### <a name="clean-up-with-clear-and-copy"></a><span data-ttu-id="8c5ba-193">クリアとコピーでクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="8c5ba-193">Clean up with clear and copy</span></span>

<span data-ttu-id="8c5ba-194">コンソールで開発すると **、** 問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-194">When developing in the **Console**, things may get messy.</span></span>  <span data-ttu-id="8c5ba-195">コピーして貼り付ける間に結果を選択しようとするとイライラする場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-195">You may find it frustrating to try to choose results while you copy and paste.</span></span>  <span data-ttu-id="8c5ba-196">次の 2 つのユーティリティ メソッドが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-196">The following two utility methods help you.</span></span>  

*   `copy()` <span data-ttu-id="8c5ba-197">クリップボードに与える内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-197">copies whatever you give it to the clipboard.</span></span>  <span data-ttu-id="8c5ba-198">この `copy()` メソッドは、最後の結果をコピーするメソッドと組み合 `$_` わせするときに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-198">The `copy()` method is especially useful when you mix it with `$_` that copies the last result.</span></span>
*   `clear()` <span data-ttu-id="8c5ba-199">コンソールをクリア**します。**</span><span class="sxs-lookup"><span data-stu-id="8c5ba-199">clears the **Console**.</span></span>

### <a name="read-and-monitor-events"></a><span data-ttu-id="8c5ba-200">イベントの読み取りおよび監視</span><span class="sxs-lookup"><span data-stu-id="8c5ba-200">Read and monitor events</span></span>

<span data-ttu-id="8c5ba-201">Console の他の 2 つの興味深いユーティリティ **メソッドは** 、イベント処理を扱います。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-201">Two other interesting utility methods of **Console** deal with event handling.</span></span>

*   `getEventListeners(node)` <span data-ttu-id="8c5ba-202">ノードのすべてのイベント リスナーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-202">lists all the event listeners of a node.</span></span>
*   `monitorEvents(node, events)` <span data-ttu-id="8c5ba-203">ノードで発生するイベントを監視およびログに記録します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-203">monitors and logs the events that happen on a node.</span></span>

<span data-ttu-id="8c5ba-204">Web ページの最初のフォームに割り当てられているすべてのイベント リスナーを一覧表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-204">To list all of the event listener assigned to the first form in the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-205">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-205">Open the **Console**.</span></span>  
1.  <span data-ttu-id="8c5ba-206">次のコード スニペットを入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-206">Type or copy and paste the following code snippet.</span></span>  
    
    ```javascript
    getEventListeners($('form')); 
    ```  

:::image type="complex" source="../media/console-dom-get-form-events.msft.png" alt-text="Web ページの最初のフォームのすべてのイベント リスナーを取得する" lightbox="../media/console-dom-get-form-events.msft.png":::
    <span data-ttu-id="8c5ba-208">Web ページの最初のフォームのすべてのイベント リスナーを取得する</span><span class="sxs-lookup"><span data-stu-id="8c5ba-208">Get all events listeners for the first form in the webpage</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-209">監視すると、指定した要素に何かが変更されるごとに、 **コンソール** で通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-209">When you monitor, you to get a notification in the **Console** every time something changes to the specified elements.</span></span>  <span data-ttu-id="8c5ba-210">リッスンするイベントを 2 番目のパラメーターとして定義します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-210">You define the events you want to listen to as a second parameter.</span></span>  <span data-ttu-id="8c5ba-211">監視するイベントを定義することが重要です。それ以外の場合は、要素に発生するイベントが報告されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-211">It is important for you to define the events that you want to monitor, otherwise any event happening to the element is reported.</span></span>

<span data-ttu-id="8c5ba-212">スクロール、ウィンドウのサイズ変更\*\*\*\*、またはユーザーが検索フォームに入力する度にコンソールで通知を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-212">To get a notification in the **Console** every time you scroll, resize the window, or when the user types in the search form, complete the following actions.</span></span>  

1.  <span data-ttu-id="8c5ba-213">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-213">Open the **Console**.</span></span>  
1.  <span data-ttu-id="8c5ba-214">次のコード スニペットを入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-214">Type or copy and paste the following code snippet.</span></span>  
    
    ```javascript
    monitorEvents(window, ['resize', 'scroll']);
    monitorEvents($0, 'keyup');
    ```  
    
:::image type="complex" source="../media/console-dom-monitor-events.msft.png" alt-text="コンソールには、ウィンドウで発生するスクロール イベントが表示されます。" lightbox="../media/console-dom-monitor-events.msft.png":::
    <span data-ttu-id="8c5ba-216">**コンソールには** 、ウィンドウで発生するスクロール イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-216">**Console** displays every scroll event that happens on the Window</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-217">現在選択されている要素に対するキー アクションをログに記録するには、ヘッダーの検索フォームにフォーカスを合わせ、いくつかのキーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-217">To log any key action on the currently chosen element, focus on the search form in the header and select some keys.</span></span>  

:::image type="complex" source="../media/console-dom-monitor-key-events.msft.png" alt-text="コンソールは、フォームで発生するキーアップ イベントを表示します。" lightbox="../media/console-dom-monitor-key-events.msft.png":::
    <span data-ttu-id="8c5ba-219">**コンソールには** 、 `keyup` フォーム上で発生するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-219">**Console** displays `keyup` events that happen on the form</span></span>  
:::image-end:::  

<span data-ttu-id="8c5ba-220">停止するには、次のコード スニペットを使用して設定した監視を削除します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-220">To stop it, remove the monitoring you set using the following code snippet.</span></span>  

```javascript
unmonitorEvents(window, ['resize', 'scroll']);
unmonitorEvents($0, 'key');
```  

## <a name="reuse-dom-manipulation-scripts"></a><span data-ttu-id="8c5ba-221">DOM 操作スクリプトの再利用</span><span class="sxs-lookup"><span data-stu-id="8c5ba-221">Reuse DOM manipulation scripts</span></span>

<span data-ttu-id="8c5ba-222">コンソールから DOM を操作すると便利な場合 **があります**。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-222">You may find it useful to manipulate the DOM from the **Console**.</span></span>  <span data-ttu-id="8c5ba-223">開発プラットフォームとしてコンソールの制限 **が発生する** 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-223">You may soon run into the limitations of the **Console** as a development platform.</span></span>  <span data-ttu-id="8c5ba-224">良いニュースは [、DevTools][DevtoolsSourcesIndex] の Sources ツールが完全に機能する開発環境を提供しているというニュースです。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-224">The good news is that the [Sources][DevtoolsSourcesIndex] tool in DevTools offers a fully featured development environment.</span></span>  <span data-ttu-id="8c5ba-225">[ソース **] ツールで** 、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-225">In the **Sources** tool, you may complete the following actions.</span></span>  

*   <span data-ttu-id="8c5ba-226">コンソールのスクリプトを **スニペット** として [保存します][DevToolsJavascriptSnippets]。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-226">Store your scripts for the **Console** as [Snippets][DevToolsJavascriptSnippets].</span></span>  
*   <span data-ttu-id="8c5ba-227">キーボード ショートカットまたはエディターを使用して Web ページでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5ba-227">Run the scripts in a webpage using a keyboard shortcut or the editor.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="8c5ba-228">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="8c5ba-228">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール にログイン|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[DevToolsJavascriptSnippets]: ../javascript/snippets.md "DevTools を使用して任意のページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  
[DevtoolsSourcesIndex]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
