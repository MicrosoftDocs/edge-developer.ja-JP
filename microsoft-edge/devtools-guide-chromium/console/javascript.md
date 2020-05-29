---
title: 本体の JavaScript の実行を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 724d0e3c7c8439551538383e68a5fc4465eade94
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601727"
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







# <span data-ttu-id="744d1-103">本体の JavaScript の実行を開始する</span><span class="sxs-lookup"><span data-stu-id="744d1-103">Get Started With Running JavaScript In The Console</span></span>   



<span data-ttu-id="744d1-104">この対話形式のチュートリアルでは、Microsoft Edge DevTools コンソールで JavaScript を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="744d1-104">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools Console.</span></span>  <span data-ttu-id="744d1-105">メッセージをコンソールに記録する方法については、「[ログメッセージの概要][DevToolsConsoleLoggingMessages]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="744d1-105">See [Get Started With Logging Messages][DevToolsConsoleLoggingMessages] to learn how to log messages to the Console.</span></span>  <span data-ttu-id="744d1-106">JavaScript コードを一時停止して、一度に1行ずつ手順を実行する方法については、「 [Javascript のデバッグを開始][DevToolsJavascriptIndex]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="744d1-106">See [Get Started With Debugging JavaScript][DevToolsJavascriptIndex] to learn how to pause JavaScript code and step through it one line at a time.</span></span>  

> ##### <span data-ttu-id="744d1-107">図 1</span><span class="sxs-lookup"><span data-stu-id="744d1-107">Figure 1</span></span>  
> <span data-ttu-id="744d1-108">**本体**</span><span class="sxs-lookup"><span data-stu-id="744d1-108">The **Console**</span></span>  
> ![本体][ImageConsole]  

## <span data-ttu-id="744d1-110">概要</span><span class="sxs-lookup"><span data-stu-id="744d1-110">Overview</span></span>   

<span data-ttu-id="744d1-111">**本体**は[REPL][WikiReadEvalPrintLoop]であり、読み取り、評価、印刷、ループを意味します。</span><span class="sxs-lookup"><span data-stu-id="744d1-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="744d1-112">これは、入力した JavaScript を読み上げてコードを評価し、[式][2alityExpressionsVersusStatements]の結果を出力した後、最初の手順にループします。</span><span class="sxs-lookup"><span data-stu-id="744d1-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="744d1-113">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="744d1-113">Set up DevTools</span></span>   

<span data-ttu-id="744d1-114">このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="744d1-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="744d1-115">実際にフォローすると、後でワークフローを覚える可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="744d1-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="744d1-116">`Control` + `Shift` + `J` 本体を開くには、\ (Windows \) または `Command` + `Option` + `J` \ ( **Console**macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="744d1-116">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="744d1-117">`Control`[\ (Windows \)] または `Command` [\ (macOS \)] をクリックし、[**コンソール Javascript の例**] をクリックして新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="744d1-117">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Javascript Example** to open in a new window.</span></span>  
    
    [<span data-ttu-id="744d1-118">本体の Javascript の例</span><span class="sxs-lookup"><span data-stu-id="744d1-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    > ##### <span data-ttu-id="744d1-119">図 2</span><span class="sxs-lookup"><span data-stu-id="744d1-119">Figure 2</span></span>  
    > <span data-ttu-id="744d1-120">左側の本体の JavaScript のサンプルページと右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="744d1-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    > ![左側の本体の JavaScript のサンプルページと右側の DevTools][ImageTutorialDevToolsJs]  

## <span data-ttu-id="744d1-122">ページの JavaScript または DOM を表示して変更する</span><span class="sxs-lookup"><span data-stu-id="744d1-122">View and change the JavaScript or DOM of the page</span></span>   

<span data-ttu-id="744d1-123">ページの作成またはデバッグ時には、ページの外観や実行方法を変更するために、**コンソール**でステートメントを実行すると便利なことがあります。</span><span class="sxs-lookup"><span data-stu-id="744d1-123">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="744d1-124">ボタンのテキストに注目してください。</span><span class="sxs-lookup"><span data-stu-id="744d1-124">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="744d1-125">コンソールに入力し、を `document.getElementById('hello').textContent = 'Hello, Console!'` 押して式を評価し**Console** `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="744d1-125">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then press `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="744d1-126">ボタン内のテキストがどのように変化するかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="744d1-126">Notice how the text inside the button changes.</span></span>  
    
    > ##### <span data-ttu-id="744d1-127">図 3</span><span class="sxs-lookup"><span data-stu-id="744d1-127">Figure 3</span></span>  
    > <span data-ttu-id="744d1-128">式を評価した後の本体の外観</span><span class="sxs-lookup"><span data-stu-id="744d1-128">How the Console looks after evaluating the expression</span></span>  
    > ![式を評価した後の本体の外観][ImageConsoleAfterEvaluating]  
    
    <span data-ttu-id="744d1-130">評価したコードの下に表示さ `"Hello, Console!"` れます。</span><span class="sxs-lookup"><span data-stu-id="744d1-130">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="744d1-131">REPL: read、evaluate、print、loop の4つの手順を取り消します。</span><span class="sxs-lookup"><span data-stu-id="744d1-131">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="744d1-132">コードを評価した後、REPL は式の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="744d1-132">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="744d1-133">そのため `"Hello, Console!"` 、評価の結果である必要があり `document.getElementById('hello').textContent = 'Hello, Console!'` ます。</span><span class="sxs-lookup"><span data-stu-id="744d1-133">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="744d1-134">ページに関連していない任意の JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="744d1-134">Run arbitrary JavaScript that is not related to the page</span></span>   

<span data-ttu-id="744d1-135">場合によっては、コードをテストできる場所でコードプレイグラウンドを使用したり、使い慣れていない新しい JavaScript 機能を試したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="744d1-135">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="744d1-136">このような種類の実験では、コンソールは最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="744d1-136">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="744d1-137">`5 + 15`本体に入力し、を押して `Enter` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="744d1-137">Type `5 + 15` in the Console and press `Enter` to evaluate the expression.</span></span> <span data-ttu-id="744d1-138">本体によって、コードの下に式の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="744d1-138">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="744d1-139">**図 4**は、この式を評価した後の本体の表示方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="744d1-139">**Figure 4** below shows how your Console should look after evaluating this expression.</span></span>  

1.  <span data-ttu-id="744d1-140">**コンソール**に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="744d1-140">Type the following code into the **Console**.</span></span>  <span data-ttu-id="744d1-141">テキストをコピーして貼り付けるのではなく、文字で入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="744d1-141">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20) {
        return a + b;
    }
    ```  
    
    <span data-ttu-id="744d1-142">構文に慣れていない場合は、「[関数引数の既定値を定義][Esma6DefaultParameterValues]する」を参照してください `b=20` 。</span><span class="sxs-lookup"><span data-stu-id="744d1-142">See [define default values for function arguments][Esma6DefaultParameterValues] if you are unfamiliar with the `b=20` syntax.</span></span>  
    
1.  <span data-ttu-id="744d1-143">次に、定義した関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="744d1-143">Now, call the function that you just defined.</span></span>  
    
    ```javascript
    add(25);
    ```  
    
    > ##### <span data-ttu-id="744d1-144">図 4</span><span class="sxs-lookup"><span data-stu-id="744d1-144">Figure 4</span></span>  
    > <span data-ttu-id="744d1-145">上の式を評価した後の本体の外観</span><span class="sxs-lookup"><span data-stu-id="744d1-145">How the Console looks after evaluating the expressions above</span></span>  
    > ![上の式を評価した後の本体の外観][ImagePlayground]  
    
    `add(25)` <span data-ttu-id="744d1-147">`45` `add` 2 番目の引数を指定せずに関数を呼び出した場合は、として評価され `b` ます。既定は、 `20` です。</span><span class="sxs-lookup"><span data-stu-id="744d1-147">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="744d1-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="744d1-148">Next steps</span></span>   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="744d1-149">DevTools では、実行中にスクリプトを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="744d1-149">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="744d1-150">一時停止中は、**本体**を使ってその時点でのページの表示や変更を行うことができ `window` `DOM` ます。</span><span class="sxs-lookup"><span data-stu-id="744d1-150">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="744d1-151">これにより、強力なデバッグワークフローが実現します。</span><span class="sxs-lookup"><span data-stu-id="744d1-151">This makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="744d1-152">「対話型チュートリアルの[デバッグ JavaScript の概要][DevToolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="744d1-152">See [Get Started With Debugging JavaScript][DevToolsJavascriptIndex] for an interactive tutorial.</span></span>  

<span data-ttu-id="744d1-153">**コンソール**には、ページを操作しやすくするための便利な機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="744d1-153">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="744d1-154">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="744d1-154">For example:</span></span>  

*   <span data-ttu-id="744d1-155">`document.querySelector()`要素を選択する代わりに、「」と入力 `$()` します。</span><span class="sxs-lookup"><span data-stu-id="744d1-155">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="744d1-156">この構文は jQuery が示していますが、実際は jQuery ではありません。</span><span class="sxs-lookup"><span data-stu-id="744d1-156">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="744d1-157">これは、の別名にすぎ `document.querySelector()` ません。</span><span class="sxs-lookup"><span data-stu-id="744d1-157">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="744d1-158">関数の最初の行に、効率的にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="744d1-158">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="744d1-159">指定されたオブジェクトのキーを含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="744d1-159">returns an array containing the keys of the specified object.</span></span>  

<!--See [Console Utilities API Reference][DevToolsConsoleUtilities] to explore all the convenience functions.  -->  

<!--todo: add console utilities api reference section when available  -->  

 



<!-- image links -->  

[ImageConsole]: /microsoft-edge/devtools-guide-chromium/media/console-javascript-example-console-playground.msft.png "図 1: 本体"  
[ImageTutorialDevToolsJs]: /microsoft-edge/devtools-guide-chromium/media/console-javascript-example-console-empty.msft.png "図 2: 左側の本体の JavaScript のサンプルページと右側の DevTools"  
[ImageConsoleAfterEvaluating]: /microsoft-edge/devtools-guide-chromium/media/console-javascript-example-console-change-button-text.msft.png "図 3: 式を評価した後の本体の外観"  
[ImagePlayground]: /microsoft-edge/devtools-guide-chromium/media/console-javascript-example-console-playground.msft.png "図 4: 上の式を評価した後の本体の外観"  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのメッセージの記録を開始する"  
[DevToolsConsoleReference]: /microsoft-edge/devtools-guide-chromium/console/reference#run-javascript "本体のリファレンス"  
[DevToolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium//console/utilities "コンソールユーティリティ API リファレンス"  

[DevToolsJavascriptIndex]: /microsoft-edge/devtools-guide-chromium/javascript/index "Microsoft Edge DevTools のデバッグ JavaScript の概要"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript の式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値-拡張パラメーター処理-ECMAScript 6-新機能: 概要 & 比較"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "本体 Javascript の例 |故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "読み取り– eval – print loop-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="744d1-172">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="744d1-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="744d1-173">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="744d1-173">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="744d1-175">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="744d1-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
