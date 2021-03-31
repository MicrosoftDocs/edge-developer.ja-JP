---
description: コンソール コマンド ラインを使用して実行中のページを操作する
title: DevTools - コンソール - コマンド ライン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, コンソール コマンド ライン
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d7ea2bef9fa0014e4d61745636a06d508565df91
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234604"
---
# <span data-ttu-id="e91a2-104">コンソール コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="e91a2-104">Console command line</span></span>

<span data-ttu-id="e91a2-105">コンソール のコマンド ラインを使用して、ページ上の値を表示および変更し、デバッグ コードをオンザフライで実行します[](/visualstudio/ide/javascript-intellisense)。同時に、自動コードVisual Studio IntelliSense利用できます。</span><span class="sxs-lookup"><span data-stu-id="e91a2-105">Use the Console command line to view and change values on a page and execute debug code on the fly, all while taking advantage of Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense) auto code completion.</span></span> 

<span data-ttu-id="e91a2-106">コマンド ライン プロンプトで有効な JavaScript を入力し、押して `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-106">Simply enter any valid JavaScript at the command line prompt and press `Enter` to execute.</span></span> <span data-ttu-id="e91a2-107">複数行入力の場合は、 `Shift+Enter` 行間を追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-107">For multi-line input use `Shift+Enter` to add a line-break.</span></span> <span data-ttu-id="e91a2-108">現在の DevTools セッション中に入力した以前のコンソール コマンドを移動するには、方向キーと `Up` `Down` 方向キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-108">Use the `Up` and `Down` arrow keys to navigate through previous console commands you entered during the current  DevTools session.</span></span> <span data-ttu-id="e91a2-109">標準の JavaScript とコンソール [API](./console-api.md)に加えて、コンソールは次のコマンドもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e91a2-109">In addition to standard JavaScript and the [Console API](./console-api.md), the Console also supports the following commands for:</span></span>

 - [<span data-ttu-id="e91a2-110">DOM オブジェクトの選択</span><span class="sxs-lookup"><span data-stu-id="e91a2-110">Selecting DOM objects</span></span>](#dom-selectors)
 - [<span data-ttu-id="e91a2-111">オブジェクト プロパティの検査</span><span class="sxs-lookup"><span data-stu-id="e91a2-111">Inspecting object properties</span></span>](#object-inspection)
 - [<span data-ttu-id="e91a2-112">特定のオブジェクトのすべてのイベント リスナーを検索する</span><span class="sxs-lookup"><span data-stu-id="e91a2-112">Finding all the event listeners on a given object</span></span>](#event-listeners)

<span data-ttu-id="e91a2-113">コマンド ラインに入力されたスクリプトは、ページが[](/scripting/javascript/advanced/variable-scope-javascript)ブレークポイントで一時停止されていない限り、現在選択されているウィンドウのグローバル スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e91a2-113">Script entered in the command line executes in the [global scope](/scripting/javascript/advanced/variable-scope-javascript) of the currently selected window, unless the page is paused at a breakpoint.</span></span> <span data-ttu-id="e91a2-114">ページが一時停止している間に入力されたコンソール コマンドは、[](/scripting/javascript/advanced/variable-scope-javascript)呼び出し履歴内の現在の関数のローカル スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e91a2-114">Console commands entered while the page is paused will execute in the [local scope](/scripting/javascript/advanced/variable-scope-javascript) of the current function within the call stack.</span></span>

<span data-ttu-id="e91a2-115">コンソールには、コンソール **出力領域** の上にターゲット実行コンテキストドロップダウンがあります。</span><span class="sxs-lookup"><span data-stu-id="e91a2-115">The Console has a **Target** execution context drop-down just above the Console output area.</span></span> <span data-ttu-id="e91a2-116">既定の選択範囲は、トップ レベルの文書 **_top。**</span><span class="sxs-lookup"><span data-stu-id="e91a2-116">The default selection is the top-level document, **_top**.</span></span> <span data-ttu-id="e91a2-117">ドキュメント内の iframe や実行中の拡張機能もオプションとして表示され、これらの範囲内でコマンドを別の方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e91a2-117">Any iframes in the document or running extensions will also appear as options, allowing you to alternately run commands within those scopes.</span></span>

## <span data-ttu-id="e91a2-118">DOM セレクター</span><span class="sxs-lookup"><span data-stu-id="e91a2-118">DOM selectors</span></span>
<span data-ttu-id="e91a2-119">次のコンソール セレクターは、DOM 内のオブジェクトにすばやくアクセスする簡単な短い方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-119">These console selectors provide simple shorthands for quickly accessing objects within the DOM:</span></span>

### <span data-ttu-id="e91a2-120">$(*CSS セレクター文字列*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-120">$(*CSS selector string*)</span></span>
<span data-ttu-id="e91a2-121">指定された [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  セレクター (またはセレクターのコンマ区切りグループ) 文字列に一致するドキュメント内の最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-121">Returns the first element within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="e91a2-122">[document.querySelector() の簡単な説明です](https://developer.mozilla.org/docs/Web/API/Document/querySelector)。</span><span class="sxs-lookup"><span data-stu-id="e91a2-122">Shorthand for [document.querySelector()](https://developer.mozilla.org/docs/Web/API/Document/querySelector).</span></span>

<span data-ttu-id="e91a2-123">例: コンソールを開き、このページ `$('#main')` で div オブジェクトを返 `id='main'` すコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-123">Example: Open the console and type `$('#main')` to return the div object with `id='main'` on this page.</span></span>

!['$' セレクターの使用例](../media/console_cmd_$.png)

### <span data-ttu-id="e91a2-125">$$(*CSS セレクター文字列*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-125">$$(*CSS selector string*)</span></span>
<span data-ttu-id="e91a2-126">指定された [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  セレクター (またはセレクターのコンマ区切りグループ) 文字列に一致するドキュメント内の要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-126">Returns an array of elements within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="e91a2-127">[document.querySelectorAll() の簡単な説明です](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)。</span><span class="sxs-lookup"><span data-stu-id="e91a2-127">Shorthand for [document.querySelectorAll()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll).</span></span>

<span data-ttu-id="e91a2-128">例: コンソールを開き、このページに含 `$$('.container')` まれるすべての div オブジェクトを返 `class='container'` す型を入力します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-128">Example: Open the console and type `$$('.container')` to return all the div objects with `class='container'` on this page.</span></span>

!['$$' セレクターの使用例](../media/console_cmd_$$.png)

### <span data-ttu-id="e91a2-130">$0、$1、$2,...</span><span class="sxs-lookup"><span data-stu-id="e91a2-130">$0, $1, $2,...</span></span>
<span data-ttu-id="e91a2-131">要素パネルで選択された最後の要素を[](../elements.md)返します。現在選択されている項目を表し、その前に選択された項目だったなど `$0` `$1` です。</span><span class="sxs-lookup"><span data-stu-id="e91a2-131">Returns the last elements selected in the [**Elements**](../elements.md) panel, where `$0` represents the currently selected item, `$1` was the selected item before that, and so on.</span></span>

<span data-ttu-id="e91a2-132">例: DevTools を **[要素**] タブで開き、Select 要素ツールを押してアクティブ化し、このページの一部の領域をマウス `CTRL + B` でクリックします。 </span><span class="sxs-lookup"><span data-stu-id="e91a2-132">Example: Open  DevTools to the **Elements** tab, press `CTRL + B` to activate the **Select element** tool and click some area on this page with your mouse.</span></span> <span data-ttu-id="e91a2-133">コンソールを開き、クリック `$0` した要素を入力して返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-133">Now open the Console and type `$0` to return the element you just clicked.</span></span>

!['$0' セレクターの使用例](../media/console_cmd_$0.png)

### <span data-ttu-id="e91a2-135">$x(*XPath 式*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-135">$x(*XPath expression*)</span></span>
<span data-ttu-id="e91a2-136">指定した XPath 式と一致する要素の [配列を返](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-136">Returns an array of elements matched by the specified [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) expression.</span></span> 

<span data-ttu-id="e91a2-137">例: コンソールを開き、属性を含むこのページのすべての要素を返 `$x('//script[@defer]')` `<script>` す型を入力 `defer` します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-137">Example: Open the console and type `$x('//script[@defer]')` to return all the `<script>` elements on this page that contain a `defer` attribute.</span></span>

!['$x' セレクターの使用例](../media/console_cmd_$x.png)

## <span data-ttu-id="e91a2-139">オブジェクト検査</span><span class="sxs-lookup"><span data-stu-id="e91a2-139">Object inspection</span></span>

<span data-ttu-id="e91a2-140">これらのコマンドは、オブジェクトのプロパティを簡単に検査する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-140">These commands provide quick ways to inspect the properties of an object.</span></span> <span data-ttu-id="e91a2-141">指定したオブジェクトは、デバッガーのグローバル名前空間または現在のスコープで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e91a2-141">The specified object must either be defined in the global namespace or the current scope of the debugger.</span></span>

### <span data-ttu-id="e91a2-142">dir(*object*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-142">dir(*object*)</span></span>
<span data-ttu-id="e91a2-143">指定したオブジェクトのプロパティのツリー ビューリストを返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-143">Returns a tree view list of properties for the specified object.</span></span>

<span data-ttu-id="e91a2-144">例: コンソールを開き、入力して、このページを表すドキュメント オブジェクトの `dir(document)` オブジェクト プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-144">Example: Open the console and type `dir(document)` to see the object properties for the document object representing this page.</span></span>

!['dir' メソッドの使用例](../media/console_cmd_dir.png)

### <span data-ttu-id="e91a2-146">keys(*object*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-146">keys(*object*)</span></span>
<span data-ttu-id="e91a2-147">指定したオブジェクトに関連付けられたプロパティ名の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-147">Returns an array of property names attached to the specified object.</span></span>

<span data-ttu-id="e91a2-148">例: コンソールを開き、グローバル ウィンドウ オブジェクトで定義されているプロパティ `keys(window)` を返す型を入力します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-148">Example: Open the console and type `keys(window)` to return all of the properties defined on the global window object.</span></span>

!['keys' メソッドの使用例](../media/console_cmd_keys.png)

### <span data-ttu-id="e91a2-150">values(*object*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-150">values(*object*)</span></span>
<span data-ttu-id="e91a2-151">指定したオブジェクトに関連付けられたプロパティ値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-151">Returns an array of property values attached to the specified object.</span></span>

<span data-ttu-id="e91a2-152">例: コンソールを開いて入力し、グローバル ウィンドウ オブジェクトで定義されているプロパティ (キー) の値 `values(window)` を返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-152">Example: Open the console and type `values(window)` to return the values of all the properties (keys) defined on the global window object.</span></span>

!['values' メソッドの使用例](../media/console_cmd_values.png)

## <span data-ttu-id="e91a2-154">イベント リスナー</span><span class="sxs-lookup"><span data-stu-id="e91a2-154">Event listeners</span></span>

<span data-ttu-id="e91a2-155">このコマンドを使用すると、特定のオブジェクトに登録されているイベント リスナーを検査できます。</span><span class="sxs-lookup"><span data-stu-id="e91a2-155">This command allows you to inspect the event listeners registered to a given object.</span></span> <span data-ttu-id="e91a2-156">指定したオブジェクトは、デバッガーのグローバル名前空間または現在のスコープで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e91a2-156">The specified object must either be defined in the global namespace or the current scope of the  debugger.</span></span>

### <span data-ttu-id="e91a2-157">getEventListeners(*object*)</span><span class="sxs-lookup"><span data-stu-id="e91a2-157">getEventListeners(*object*)</span></span>
<span data-ttu-id="e91a2-158">特定のオブジェクトに登録されている各イベントの種類のキーを含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-158">Returns an object containing a key for each registered event type on the given object.</span></span> <span data-ttu-id="e91a2-159">各キーの値は、イベント リスナーとその関連情報の配列です。</span><span class="sxs-lookup"><span data-stu-id="e91a2-159">The value of each key is an array of event listeners and their related info.</span></span> 

<span data-ttu-id="e91a2-160">例: コンソールを開き、入力して、このページのドキュメント オブジェクトに登録されているイベント リスナー `getEventListeners(document)` を表示します。</span><span class="sxs-lookup"><span data-stu-id="e91a2-160">Example: Open the console and type `getEventListeners(document)` to see all the event listeners registered on the document object of this page.</span></span>

!['getEventListeners' メソッドの使用例](../media/console_cmd_getEventListeners.png)
