---
description: コンソールで JavaScript を実行する方法について説明します。
title: 本体の JavaScript の実行を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6537cb07b52ef6b8be4b1ea7d9420bf2307d3fd5
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125245"
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

# <span data-ttu-id="01c63-104">本体の JavaScript の実行を開始する</span><span class="sxs-lookup"><span data-stu-id="01c63-104">Get Started With Running JavaScript In The Console</span></span>  

<span data-ttu-id="01c63-105">この対話形式のチュートリアルでは、Microsoft Edge DevTools **コンソール**で JavaScript を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="01c63-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="01c63-106">**コンソール**へのメッセージのログの記録方法の詳細については、「[ログメッセージの使用を開始][DevToolsConsoleLoggingMessages]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-106">For more information about how to log messages to the **Console**, navigate to [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="01c63-107">JavaScript コードを一時停止して一度に1行ずつ手順を実行する方法の詳細については、「 [デバッグ Javascript の概要][DevToolsJavascriptIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-107">For more information about how to pause JavaScript code and step through it one line at a time, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="01c63-109">**本体**</span><span class="sxs-lookup"><span data-stu-id="01c63-109">The **Console**</span></span>  
:::image-end:::  

## <span data-ttu-id="01c63-110">概要</span><span class="sxs-lookup"><span data-stu-id="01c63-110">Overview</span></span>  

<span data-ttu-id="01c63-111">**本体**は[REPL][WikiReadEvalPrintLoop]であり、読み取り、評価、印刷、ループを意味します。</span><span class="sxs-lookup"><span data-stu-id="01c63-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="01c63-112">これは、入力した JavaScript を読み上げてコードを評価し、 [式][2alityExpressionsVersusStatements]の結果を出力した後、最初の手順にループします。</span><span class="sxs-lookup"><span data-stu-id="01c63-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <span data-ttu-id="01c63-113">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="01c63-113">Set up DevTools</span></span>  

<span data-ttu-id="01c63-114">このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="01c63-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="01c63-115">実際にフォローすると、後でワークフローを覚える可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="01c63-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="01c63-116">`Control` + `Shift` + `J` 本体を開くには、\ (Windows, Linux \) または `Command` + `Option` + `J` \ ( **Console**macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c63-116">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="01c63-117">" `Control` \ (Windows, Linux \)" または " `Command` \ (macOS \)" を保持し、新しいウィンドウで開くには [ **本体] Javascript の例** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c63-117">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="01c63-118">本体の Javascript の例</span><span class="sxs-lookup"><span data-stu-id="01c63-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="01c63-120">左側の本体の JavaScript のサンプルページと右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="01c63-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="01c63-121">ページの JavaScript または DOM を表示して変更する</span><span class="sxs-lookup"><span data-stu-id="01c63-121">View and change the JavaScript or DOM of the page</span></span>  

<span data-ttu-id="01c63-122">ページの作成またはデバッグ時には、ページの外観や実行方法を変更するために、 **コンソール** でステートメントを実行すると便利なことがあります。</span><span class="sxs-lookup"><span data-stu-id="01c63-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="01c63-123">ボタンのテキストに注目してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-123">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="01c63-124">`document.getElementById('hello').textContent = 'Hello, Console!'`**本体**に入力し、[ `Enter` 式の評価] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c63-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then select `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="01c63-125">ボタン内のテキストがどのように変化するかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-125">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="01c63-127">式を評価した後の **本体** の外観</span><span class="sxs-lookup"><span data-stu-id="01c63-127">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="01c63-128">評価したコードの下に表示さ `"Hello, Console!"` れます。</span><span class="sxs-lookup"><span data-stu-id="01c63-128">Below the code that you evaluated you see `"Hello, Console!"`.</span></span>  <span data-ttu-id="01c63-129">REPL: read、evaluate、print、loop の4つの手順を取り消します。</span><span class="sxs-lookup"><span data-stu-id="01c63-129">Recall the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="01c63-130">コードを評価した後、REPL は式の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="01c63-130">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="01c63-131">そのため `"Hello, Console!"` 、評価の結果である必要があり `document.getElementById('hello').textContent = 'Hello, Console!'` ます。</span><span class="sxs-lookup"><span data-stu-id="01c63-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <span data-ttu-id="01c63-132">ページに関連していない任意の JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="01c63-132">Run arbitrary JavaScript that is not related to the page</span></span>  

<span data-ttu-id="01c63-133">場合によっては、コードをテストできる場所でコードプレイグラウンドを使用したり、使い慣れていない新しい JavaScript 機能を試したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="01c63-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="01c63-134">このような種類の実験では、コンソールは最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="01c63-134">The Console is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="01c63-135">コンソールに入力し、 `5 + 15` を選択して式を評価し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="01c63-135">Type `5 + 15` in the Console and select `Enter` to evaluate the expression.</span></span> <span data-ttu-id="01c63-136">本体によって、コードの下に式の結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="01c63-136">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="01c63-137">次の図では、式を評価した後に **コンソール** に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01c63-137">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="01c63-138">**コンソール**に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="01c63-138">Type the following code into the **Console**.</span></span>  <span data-ttu-id="01c63-139">テキストをコピーして貼り付けるのではなく、文字で入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="01c63-139">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    <span data-ttu-id="01c63-140">構文をよく理解していない場合は `b=20` 、「 [関数引数の既定値の定義][Esma6DefaultParameterValues]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-140">If you are unfamiliar with the `b=20` syntax, navigate to [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="01c63-141">次に、定義した関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="01c63-141">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="本体" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="01c63-143">コードスニペットで式を評価した後に **コンソール** が表示される</span><span class="sxs-lookup"><span data-stu-id="01c63-143">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="01c63-144">`45` `add` 2 番目の引数を指定せずに関数を呼び出した場合は、として評価され `b` ます。既定は、 `20` です。</span><span class="sxs-lookup"><span data-stu-id="01c63-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <span data-ttu-id="01c63-145">次のステップ</span><span class="sxs-lookup"><span data-stu-id="01c63-145">Next steps</span></span>  

<!--See [Run JavaScript][DevToolsConsoleReference] to explore more features related to running JavaScript in the Console.  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="01c63-146">DevTools では、実行中にスクリプトを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="01c63-146">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="01c63-147">一時停止中は、 **本体** を使ってその時点でのページの表示や変更を行うことができ `window` `DOM` ます。</span><span class="sxs-lookup"><span data-stu-id="01c63-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="01c63-148">ワークフローによって、強力なデバッグワークフローが実現されます。</span><span class="sxs-lookup"><span data-stu-id="01c63-148">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="01c63-149">インタラクティブなチュートリアルについては、「 [JavaScript のデバッグを開始][DevToolsJavascriptIndex]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-149">For an interactive tutorial, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="01c63-150">**コンソール**には、ページを操作しやすくするための便利な機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="01c63-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="01c63-151">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="01c63-151">For example:</span></span>  

*   <span data-ttu-id="01c63-152">`document.querySelector()`要素を選択する代わりに、「」と入力 `$()` します。</span><span class="sxs-lookup"><span data-stu-id="01c63-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="01c63-153">この構文は jQuery が示していますが、実際は jQuery ではありません。</span><span class="sxs-lookup"><span data-stu-id="01c63-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="01c63-154">これは、の別名にすぎ `document.querySelector()` ません。</span><span class="sxs-lookup"><span data-stu-id="01c63-154">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="01c63-155">関数の最初の行に、効率的にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="01c63-155">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="01c63-156">指定されたオブジェクトのキーを含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="01c63-156">returns an array containing the keys of the specified object.</span></span>  

<span data-ttu-id="01c63-157">便利な関数の詳細については、「 [コンソールユーティリティ API リファレンス][DevToolsConsoleUtilities]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c63-157">For more information about the convenience functions, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <span data-ttu-id="01c63-158">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="01c63-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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
> <span data-ttu-id="01c63-167">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="01c63-167">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="01c63-168">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="01c63-168">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="01c63-170">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="01c63-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
