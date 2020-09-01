---
title: 本体の JavaScript の実行を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7e91d9844b2926bc8302331c6b9d971922d27ea3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982262"
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







# <span data-ttu-id="3d6e2-103">本体の JavaScript の実行を開始する</span><span class="sxs-lookup"><span data-stu-id="3d6e2-103">Get Started With Running JavaScript In The Console</span></span>   



<span data-ttu-id="3d6e2-104">この対話形式のチュートリアルでは、Microsoft Edge DevTools **コンソール**で JavaScript を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-104">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="3d6e2-105">**コンソール**へのメッセージのログの記録方法の詳細については、「[ログメッセージの使用を開始][DevToolsConsoleLoggingMessages]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-105">For more information about how to log messages to the **Console**, see [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="3d6e2-106">JavaScript コードを一時停止して一度に1行ずつ手順を実行する方法の詳細については、「 [Javascript のデバッグの概要][DevToolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-106">For more information about how to pause JavaScript code and step through it one line at a time, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="3d6e2-108">**本体**</span><span class="sxs-lookup"><span data-stu-id="3d6e2-108">The **Console**</span></span>  
:::image-end:::  

## <span data-ttu-id="3d6e2-109">概要</span><span class="sxs-lookup"><span data-stu-id="3d6e2-109">Overview</span></span>   

<span data-ttu-id="3d6e2-110">**本体**は[REPL][WikiReadEvalPrintLoop]であり、読み取り、評価、印刷、ループを意味します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-110">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="3d6e2-111">これは、入力した JavaScript を読み上げてコードを評価し、 [式][2alityExpressionsVersusStatements]の結果を出力した後、最初の手順にループします。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-111">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="3d6e2-112">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="3d6e2-112">Set up DevTools</span></span>   

<span data-ttu-id="3d6e2-113">このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-113">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="3d6e2-114">実際にフォローすると、後でワークフローを覚える可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-114">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="3d6e2-115">`Control` + `Shift` + `J` 本体を開くには、\ (Windows \) または `Command` + `Option` + `J` \ ( **Console**macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-115">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="3d6e2-116">`Control`[\ (Windows \)] または `Command` [\ (macOS \)] をクリックし、[**コンソール Javascript の例**] をクリックして新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-116">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="3d6e2-117">本体の Javascript の例</span><span class="sxs-lookup"><span data-stu-id="3d6e2-117">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左側の本体の JavaScript のサンプルページと右側の DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="3d6e2-119">左側の本体の JavaScript のサンプルページと右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="3d6e2-119">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3d6e2-120">ページの JavaScript または DOM を表示して変更する</span><span class="sxs-lookup"><span data-stu-id="3d6e2-120">View and change the JavaScript or DOM of the page</span></span>   

<span data-ttu-id="3d6e2-121">ページの作成またはデバッグ時には、ページの外観や実行方法を変更するために、 **コンソール** でステートメントを実行すると便利なことがあります。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-121">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="3d6e2-122">ボタンのテキストに注目してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-122">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="3d6e2-123">コンソールに入力し、を `document.getElementById('hello').textContent = 'Hello, Console!'` 押して式を評価し**Console** `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-123">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then press `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="3d6e2-124">ボタン内のテキストがどのように変化するかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-124">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="式を評価した後の本体の外観" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="3d6e2-126">式を評価した後の **本体** の外観</span><span class="sxs-lookup"><span data-stu-id="3d6e2-126">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="3d6e2-127">評価したコードの下に表示さ `"Hello, Console!"` れます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-127">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="3d6e2-128">REPL: read、evaluate、print、loop の4つの手順を取り消します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-128">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="3d6e2-129">コードを評価した後、REPL は式の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-129">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="3d6e2-130">そのため `"Hello, Console!"` 、評価の結果である必要があり `document.getElementById('hello').textContent = 'Hello, Console!'` ます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-130">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="3d6e2-131">ページに関連していない任意の JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-131">Run arbitrary JavaScript that is not related to the page</span></span>   

<span data-ttu-id="3d6e2-132">場合によっては、コードをテストできる場所でコードプレイグラウンドを使用したり、使い慣れていない新しい JavaScript 機能を試したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-132">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="3d6e2-133">このような種類の実験では、コンソールは最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-133">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="3d6e2-134">`5 + 15`本体に入力し、を押して `Enter` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-134">Type `5 + 15` in the Console and press `Enter` to evaluate the expression.</span></span> <span data-ttu-id="3d6e2-135">本体によって、コードの下に式の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-135">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="3d6e2-136">次の図では、式を評価した後に **コンソール** に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-136">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="3d6e2-137">**コンソール**に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-137">Type the following code into the **Console**.</span></span>  <span data-ttu-id="3d6e2-138">テキストをコピーして貼り付けるのではなく、文字で入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-138">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20) { return a + b; }
    ```  
    
    <span data-ttu-id="3d6e2-139">構文に慣れていない場合は `b=20` 、「 [関数の引数に既定値を定義][Esma6DefaultParameterValues]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-139">If you are unfamiliar with the `b=20` syntax, see [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="3d6e2-140">次に、定義した関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-140">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コードスニペットで式を評価した後にコンソールが表示される" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="3d6e2-142">コードスニペットで式を評価した後に **コンソール** が表示される</span><span class="sxs-lookup"><span data-stu-id="3d6e2-142">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="3d6e2-143">`45` `add` 2 番目の引数を指定せずに関数を呼び出した場合は、として評価され `b` ます。既定は、 `20` です。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-143">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="3d6e2-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3d6e2-144">Next steps</span></span>   

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="3d6e2-145">DevTools では、実行中にスクリプトを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-145">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="3d6e2-146">一時停止中は、 **本体** を使ってその時点でのページの表示や変更を行うことができ `window` `DOM` ます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-146">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="3d6e2-147">ワークフローによって、強力なデバッグワークフローが実現されます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-147">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="3d6e2-148">インタラクティブなチュートリアルについては、「 [JavaScript のデバッグを開始][DevToolsJavascriptIndex]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-148">For an interactive tutorial, see [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="3d6e2-149">**コンソール**には、ページを操作しやすくするための便利な機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-149">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="3d6e2-150">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-150">For example:</span></span>  

*   <span data-ttu-id="3d6e2-151">`document.querySelector()`要素を選択する代わりに、「」と入力 `$()` します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-151">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="3d6e2-152">この構文は jQuery が示していますが、実際は jQuery ではありません。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-152">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="3d6e2-153">これは、の別名にすぎ `document.querySelector()` ません。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-153">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="3d6e2-154">関数の最初の行に、効率的にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-154">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="3d6e2-155">指定されたオブジェクトのキーを含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-155">returns an array containing the keys of the specified object.</span></span>  

<!--See [Console Utilities API Reference][DevToolsConsoleUtilities] to explore all the convenience functions.  -->  

<!--todo: add console utilities api reference section when available  -->  

 



<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "コンソールリファレンス |Microsoft ドキュメント"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript の式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値-拡張パラメーター処理-ECMAScript 6-新機能: 概要 & 比較"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "本体 Javascript の例 |故障"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "読み取り– eval – print loop-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="3d6e2-164">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-164">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3d6e2-165">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-165">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3d6e2-167">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3d6e2-167">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
