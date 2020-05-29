---
description: コンソールコマンドラインを使って、実行中のページを操作する
title: DevTools-本体-コマンドライン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、コンソールコマンドライン
ms.custom: seodec18
ms.openlocfilehash: c661736e5ea264f60279c89cfa0f9c55361d2288
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570523"
---
# <span data-ttu-id="acbe8-104">コンソールコマンドライン</span><span class="sxs-lookup"><span data-stu-id="acbe8-104">Console command line</span></span>

<span data-ttu-id="acbe8-105">本体のコマンドラインを使って、ページ上の値を表示して変更し、その場でデバッグコードを実行します。 Visual Studio の[*IntelliSense*](/visualstudio/ide/javascript-intellisense)では、自動コード補完が利用されます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-105">Use the Console command line to view and change values on a page and execute debug code on the fly, all while taking advantage of Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense) auto code completion.</span></span> 

<span data-ttu-id="acbe8-106">コマンドラインプロンプトで任意の有効な JavaScript を入力し、を押して `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-106">Simply enter any valid JavaScript at the command line prompt and press `Enter` to execute.</span></span> <span data-ttu-id="acbe8-107">複数行入力の場合は、 `Shift+Enter` 改行を追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-107">For multi-line input use `Shift+Enter` to add a line-break.</span></span> <span data-ttu-id="acbe8-108">現在の `Up` `Down` devtools セッション中に入力した前のコンソールコマンドの間を移動するには、および方向キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-108">Use the `Up` and `Down` arrow keys to navigate through previous console commands you entered during the current  DevTools session.</span></span> <span data-ttu-id="acbe8-109">コンソールは、標準の JavaScript や[コンソール API](./console-api.md)に加えて、次のコマンドもサポートします。</span><span class="sxs-lookup"><span data-stu-id="acbe8-109">In addition to standard JavaScript and the [Console API](./console-api.md), the Console also supports the following commands for:</span></span>

 - [<span data-ttu-id="acbe8-110">DOM オブジェクトの選択</span><span class="sxs-lookup"><span data-stu-id="acbe8-110">Selecting DOM objects</span></span>](#dom-selectors)
 - [<span data-ttu-id="acbe8-111">オブジェクトのプロパティを検査する</span><span class="sxs-lookup"><span data-stu-id="acbe8-111">Inspecting object properties</span></span>](#object-inspection)
 - [<span data-ttu-id="acbe8-112">特定のオブジェクトのすべてのイベントリスナーを検索する</span><span class="sxs-lookup"><span data-stu-id="acbe8-112">Finding all the event listeners on a given object</span></span>](#event-listeners)

<span data-ttu-id="acbe8-113">コマンドラインで入力したスクリプトは、ページがブレークポイントで一時停止されていない限り、現在選択されているウィンドウの[グローバルスコープ](/scripting/javascript/advanced/variable-scope-javascript)で実行されます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-113">Script entered in the command line executes in the [global scope](/scripting/javascript/advanced/variable-scope-javascript) of the currently selected window, unless the page is paused at a breakpoint.</span></span> <span data-ttu-id="acbe8-114">ページが一時停止している間に入力されたコンソールコマンドは、呼び出し履歴内の現在の関数の[ローカルスコープ](/scripting/javascript/advanced/variable-scope-javascript)で実行されます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-114">Console commands entered while the page is paused will execute in the [local scope](/scripting/javascript/advanced/variable-scope-javascript) of the current function within the call stack.</span></span>

<span data-ttu-id="acbe8-115">本体には本体の出力領域のすぐ上に**ターゲット**の実行コンテキストのドロップダウンがあります。</span><span class="sxs-lookup"><span data-stu-id="acbe8-115">The Console has a **Target** execution context drop-down just above the Console output area.</span></span> <span data-ttu-id="acbe8-116">既定では、[ **_top**] のトップレベルのドキュメントが選択されています。</span><span class="sxs-lookup"><span data-stu-id="acbe8-116">The default selection is the top-level document, **_top**.</span></span> <span data-ttu-id="acbe8-117">ドキュメント内または実行可能な拡張機能もオプションとして表示され、それらのスコープ内でコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-117">Any iframes in the document or running extensions will also appear as options, allowing you to alternately run commands within those scopes.</span></span>

## <span data-ttu-id="acbe8-118">DOM セレクター</span><span class="sxs-lookup"><span data-stu-id="acbe8-118">DOM selectors</span></span>
<span data-ttu-id="acbe8-119">以下のコンソールセレクターでは、DOM 内のオブジェクトにすばやくアクセスするためのシンプルな shorthands を提供しています。</span><span class="sxs-lookup"><span data-stu-id="acbe8-119">These console selectors provide simple shorthands for quickly accessing objects within the DOM:</span></span>

### <span data-ttu-id="acbe8-120">$ (*CSS セレクター文字列*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-120">$(*CSS selector string*)</span></span>
<span data-ttu-id="acbe8-121">指定された[CSS セレクター](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors) (または、複数のセレクターのグループ) 文字列に一致する、文書内の最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-121">Returns the first element within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="acbe8-122">[Document selector ()](https://developer.mozilla.org/docs/Web/API/Document/querySelector)の短縮形。</span><span class="sxs-lookup"><span data-stu-id="acbe8-122">Shorthand for [document.querySelector()](https://developer.mozilla.org/docs/Web/API/Document/querySelector).</span></span>

<span data-ttu-id="acbe8-123">例: 本体を開き、 `$('#main')` このページで div オブジェクトを返すために type を入力し `id='main'` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-123">Example: Open the console and type `$('#main')` to return the div object with `id='main'` on this page.</span></span>

![' $ ' セレクターの使用例](../media/console_cmd_$.png)

### <span data-ttu-id="acbe8-125">$ $ (*CSS セレクター文字列*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-125">$$(*CSS selector string*)</span></span>
<span data-ttu-id="acbe8-126">指定された[CSS セレクター](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors) (または、コンマ区切りのセレクター) 文字列に一致する、文書内の要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-126">Returns an array of elements within the document matching the specified [CSS selector](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  (or comma-separated group of selectors) string.</span></span> <span data-ttu-id="acbe8-127">[QuerySelectorAll ()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)の短縮形。</span><span class="sxs-lookup"><span data-stu-id="acbe8-127">Shorthand for [document.querySelectorAll()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll).</span></span>

<span data-ttu-id="acbe8-128">例: 本体を開いて、 `$$('.container')` このページにあるすべての div オブジェクトを返すように入力し `class='container'` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-128">Example: Open the console and type `$$('.container')` to return all the div objects with `class='container'` on this page.</span></span>

![' $ $ ' セレクターの使用例](../media/console_cmd_$$.png)

### <span data-ttu-id="acbe8-130">$0、$1、$2,...</span><span class="sxs-lookup"><span data-stu-id="acbe8-130">$0, $1, $2,...</span></span>
<span data-ttu-id="acbe8-131">[**要素**](../elements.md)パネルで選択されている最後の要素を返します。ここでは、現在選択されている項目を示し、その前に選択されている項目が含まれてい `$0` `$1` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-131">Returns the last elements selected in the [**Elements**](../elements.md) panel, where `$0` represents the currently selected item, `$1` was the selected item before that, and so on.</span></span>

<span data-ttu-id="acbe8-132">例: DevTools を開いて [**要素**] タブに移動し、を押して `CTRL + B` **[要素の選択**] ツールをアクティブ化し、マウスでこのページの一部の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acbe8-132">Example: Open  DevTools to the **Elements** tab, press `CTRL + B` to activate the **Select element** tool and click some area on this page with your mouse.</span></span> <span data-ttu-id="acbe8-133">次に、コンソールを開いて、 `$0` クリックしたばかりの要素を返すように入力します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-133">Now open the Console and type `$0` to return the element you just clicked.</span></span>

![' $0 ' セレクターの使用例](../media/console_cmd_$0.png)

### <span data-ttu-id="acbe8-135">$x (*XPath 式*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-135">$x(*XPath expression*)</span></span>
<span data-ttu-id="acbe8-136">指定された[XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript)式に一致する要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-136">Returns an array of elements matched by the specified [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) expression.</span></span> 

<span data-ttu-id="acbe8-137">例: 本体を開き、 `$x('//script[@defer]')` `<script>` 属性を含むこのページのすべての要素を返すには、「...」と入力し `defer` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-137">Example: Open the console and type `$x('//script[@defer]')` to return all the `<script>` elements on this page that contain a `defer` attribute.</span></span>

!["$X" セレクターの使用例](../media/console_cmd_$x.png)

## <span data-ttu-id="acbe8-139">オブジェクト検査</span><span class="sxs-lookup"><span data-stu-id="acbe8-139">Object inspection</span></span>

<span data-ttu-id="acbe8-140">以下のコマンドを使うと、オブジェクトのプロパティを簡単に調べることができます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-140">These commands provide quick ways to inspect the properties of an object.</span></span> <span data-ttu-id="acbe8-141">指定したオブジェクトは、グローバル名前空間またはデバッガーの現在のスコープで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="acbe8-141">The specified object must either be defined in the global namespace or the current scope of the debugger.</span></span>

### <span data-ttu-id="acbe8-142">dir (*オブジェクト*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-142">dir(*object*)</span></span>
<span data-ttu-id="acbe8-143">指定されたオブジェクトのプロパティのツリービューのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-143">Returns a tree view list of properties for the specified object.</span></span>

<span data-ttu-id="acbe8-144">例: 本体を開き、 `dir(document)` このページを表すドキュメントオブジェクトのオブジェクトプロパティを表示するには「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-144">Example: Open the console and type `dir(document)` to see the object properties for the document object representing this page.</span></span>

![' Dir ' メソッドの使用例](../media/console_cmd_dir.png)

### <span data-ttu-id="acbe8-146">キー (*オブジェクト*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-146">keys(*object*)</span></span>
<span data-ttu-id="acbe8-147">指定されたオブジェクトに結び付けられているプロパティ名の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-147">Returns an array of property names attached to the specified object.</span></span>

<span data-ttu-id="acbe8-148">例: 本体と type を開き、 `keys(window)` グローバルウィンドウオブジェクトで定義されているすべてのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-148">Example: Open the console and type `keys(window)` to return all of the properties defined on the global window object.</span></span>

!["Keys" メソッドの使用例](../media/console_cmd_keys.png)

### <span data-ttu-id="acbe8-150">値 (*オブジェクト*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-150">values(*object*)</span></span>
<span data-ttu-id="acbe8-151">指定されたオブジェクトに結び付けられているプロパティ値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-151">Returns an array of property values attached to the specified object.</span></span>

<span data-ttu-id="acbe8-152">例: 本体を開き、 `values(window)` グローバルウィンドウオブジェクトで定義されているすべてのプロパティ (キー) の値を返すには、「type」と入力します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-152">Example: Open the console and type `values(window)` to return the values of all the properties (keys) defined on the global window object.</span></span>

!["Values" メソッドの使用例](../media/console_cmd_values.png)

## <span data-ttu-id="acbe8-154">イベントリスナー</span><span class="sxs-lookup"><span data-stu-id="acbe8-154">Event listeners</span></span>

<span data-ttu-id="acbe8-155">このコマンドを使うと、指定したオブジェクトに登録されているイベントリスナーを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-155">This command allows you to inspect the event listeners registered to a given object.</span></span> <span data-ttu-id="acbe8-156">指定したオブジェクトは、グローバル名前空間またはデバッガーの現在のスコープで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="acbe8-156">The specified object must either be defined in the global namespace or the current scope of the  debugger.</span></span>

### <span data-ttu-id="acbe8-157">getEventListeners (*object*)</span><span class="sxs-lookup"><span data-stu-id="acbe8-157">getEventListeners(*object*)</span></span>
<span data-ttu-id="acbe8-158">指定されたオブジェクトに登録されている各イベントの種類について、キーを含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-158">Returns an object containing a key for each registered event type on the given object.</span></span> <span data-ttu-id="acbe8-159">各キーの値は、イベントリスナーとそれに関連する情報の配列です。</span><span class="sxs-lookup"><span data-stu-id="acbe8-159">The value of each key is an array of event listeners and their related info.</span></span> 

<span data-ttu-id="acbe8-160">例: 本体と type を開き、 `getEventListeners(document)` このページのドキュメントオブジェクトに登録されているすべてのイベントリスナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-160">Example: Open the console and type `getEventListeners(document)` to see all the event listeners registered on the document object of this page.</span></span>

![GetEventListeners メソッドの使用例](../media/console_cmd_getEventListeners.png)
