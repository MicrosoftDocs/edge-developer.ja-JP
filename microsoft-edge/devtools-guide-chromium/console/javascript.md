---
description: コンソールで JavaScript を実行する方法について説明します。
title: コンソールでの JavaScript の実行の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c1d6c393b6278f4622cf80576ccc8f9c70bdb6b5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398820"
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

# <a name="get-started-with-running-javascript-in-the-console"></a><span data-ttu-id="cb282-104">コンソールでの JavaScript の実行の開始</span><span class="sxs-lookup"><span data-stu-id="cb282-104">Get started with running JavaScript in the Console</span></span>  

<span data-ttu-id="cb282-105">この対話型チュートリアルでは、Microsoft Edge DevTools コンソールで JavaScript を実行する方法を示 **します**。</span><span class="sxs-lookup"><span data-stu-id="cb282-105">This interactive tutorial shows you how to run JavaScript in the Microsoft Edge DevTools **Console**.</span></span>  <span data-ttu-id="cb282-106">コンソールにメッセージをログに記録する方法の詳細については **、「** ログ メッセージの概要 [」に移動します][DevToolsConsoleLoggingMessages]。</span><span class="sxs-lookup"><span data-stu-id="cb282-106">For more information about how to log messages to the **Console**, navigate to [Get Started With Logging Messages][DevToolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="cb282-107">JavaScript コードを一時停止し、一度に 1 行の手順を実行する方法の詳細については、「JavaScript のデバッグを開始する」 [に移動します][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="cb282-107">For more information about how to pause JavaScript code and step through it one line at a time, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

:::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コンソール" lightbox="../media/console-javascript-example-console-playground.msft.png":::
   <span data-ttu-id="cb282-109">**コンソール**</span><span class="sxs-lookup"><span data-stu-id="cb282-109">The **Console**</span></span>  
:::image-end:::  

## <a name="overview"></a><span data-ttu-id="cb282-110">概要</span><span class="sxs-lookup"><span data-stu-id="cb282-110">Overview</span></span>  

<span data-ttu-id="cb282-111">コンソール **は** [REPL で、][WikiReadEvalPrintLoop]読み取り、評価、印刷、ループを表します。</span><span class="sxs-lookup"><span data-stu-id="cb282-111">The **Console** is a [REPL][WikiReadEvalPrintLoop], which stands for Read, Evaluate, Print, and Loop.</span></span>  <span data-ttu-id="cb282-112">入力した JavaScript を読み取り、コードを評価し、式の結果を出力し[][2alityExpressionsVersusStatements]、最初の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="cb282-112">It reads the JavaScript that you type into it, evaluates your code, prints out the result of your [expression][2alityExpressionsVersusStatements], and then loops back to the first step.</span></span>  

## <a name="set-up-devtools"></a><span data-ttu-id="cb282-113">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="cb282-113">Set up DevTools</span></span>  

<span data-ttu-id="cb282-114">このチュートリアルは、デモを開き、すべてのワークフローを自分で試す目的で設計されています。</span><span class="sxs-lookup"><span data-stu-id="cb282-114">This tutorial is designed for you to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="cb282-115">物理的にフォローすると、後でワークフローを覚えておく可能性が高い。</span><span class="sxs-lookup"><span data-stu-id="cb282-115">When you physically follow along, you are more likely to remember the workflows later.</span></span>

1.  <span data-ttu-id="cb282-116">`Control` + `Shift` + `J` \(Windows,Linux\) または `Command` + `Option` + `J` \(macOS\) を選択してコンソールを開**きます**。</span><span class="sxs-lookup"><span data-stu-id="cb282-116">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console**.</span></span>  
1.  <span data-ttu-id="cb282-117">`Control`\(Windows,Linux\) または `Command` \(macOS\) を保持し、[**コンソール Javascript の例**] を選択して新しいウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb282-117">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Javascript Example** to open in a new window.</span></span>  
    
    *   [<span data-ttu-id="cb282-118">コンソール Javascript の例</span><span class="sxs-lookup"><span data-stu-id="cb282-118">Console Javascript Example</span></span>][GlitchConsoleJavascriptExample]  
    
    :::image type="complex" source="../media/console-javascript-example-console-empty.msft.png" alt-text="左側の [コンソール JavaScript の例] ページと右側の DevTools" lightbox="../media/console-javascript-example-console-empty.msft.png":::
       <span data-ttu-id="cb282-120">左側の [コンソール JavaScript の例] ページと右側の DevTools</span><span class="sxs-lookup"><span data-stu-id="cb282-120">The Console JavaScript Example page on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
## <a name="view-and-change-the-javascript-or-dom-of-the-page"></a><span data-ttu-id="cb282-121">ページの JavaScript または DOM を表示および変更する</span><span class="sxs-lookup"><span data-stu-id="cb282-121">View and change the JavaScript or DOM of the page</span></span>  

<span data-ttu-id="cb282-122">ページを構築またはデバッグする場合、ページの外観や実行方法を変更するために、 コンソールでステートメントを実行すると便利です。</span><span class="sxs-lookup"><span data-stu-id="cb282-122">When building or debugging a page, it is often useful to run statements in the **Console** in order to change how the page looks or runs.</span></span>  
    
1.  <span data-ttu-id="cb282-123">ボタンのテキストに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb282-123">Notice the text in the button.</span></span>  
1.  <span data-ttu-id="cb282-124">コンソール `document.getElementById('hello').textContent = 'Hello, Console!'` に入力 **し、** 式を `Enter` 評価するために選択します。</span><span class="sxs-lookup"><span data-stu-id="cb282-124">Type `document.getElementById('hello').textContent = 'Hello, Console!'` in the **Console** and then select `Enter` to evaluate the expression.</span></span>  <span data-ttu-id="cb282-125">ボタン内のテキストがどのように変化するのか注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb282-125">Notice how the text inside the button changes.</span></span>  
    
    :::image type="complex" source="../media/console-javascript-example-console-change-button-text.msft.png" alt-text="式の評価後のコンソールの外観" lightbox="../media/console-javascript-example-console-change-button-text.msft.png":::
       <span data-ttu-id="cb282-127">式の **評価** 後のコンソールの外観</span><span class="sxs-lookup"><span data-stu-id="cb282-127">How the **Console** looks after evaluating the expression</span></span>  
    :::image-end:::  
    
    `"Hello, Console!"`<span data-ttu-id="cb282-128">は、評価したコードの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb282-128">, is displayed below the code that you evaluated.</span></span>  <span data-ttu-id="cb282-129">REPL の 4 つの手順(読み取り、評価、印刷、ループ)を覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="cb282-129">Remember the 4 steps of REPL: read, evaluate, print, loop.</span></span>  <span data-ttu-id="cb282-130">コードを評価した後、REPL は式の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="cb282-130">After evaluating your code, a REPL prints the result of the expression.</span></span>  <span data-ttu-id="cb282-131">したがって `"Hello, Console!"` 、評価の結果である必要があります `document.getElementById('hello').textContent = 'Hello, Console!'` 。</span><span class="sxs-lookup"><span data-stu-id="cb282-131">So `"Hello, Console!"` must be the result of evaluating `document.getElementById('hello').textContent = 'Hello, Console!'`.</span></span>  
    
## <a name="run-arbitrary-javascript-that-is-not-related-to-the-page"></a><span data-ttu-id="cb282-132">ページに関連しない任意の JavaScript を実行する</span><span class="sxs-lookup"><span data-stu-id="cb282-132">Run arbitrary JavaScript that is not related to the page</span></span>  

<span data-ttu-id="cb282-133">場合によっては、コードをテストしたり、使い慣れしていない新しい JavaScript 機能を試したりできるコードプレイグラウンドが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb282-133">Sometimes, you just want a code playground where you are able to test some code, or try out new JavaScript features you are not familiar with.</span></span>  <span data-ttu-id="cb282-134">コンソール **は** 、このような実験に最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="cb282-134">The **Console** is a perfect place for these kinds of experiments.</span></span>  

1.  <span data-ttu-id="cb282-135">コンソール `5 + 15` に入力し、式 `Enter` を評価するを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb282-135">Type `5 + 15` in the Console and select `Enter` to evaluate the expression.</span></span> <span data-ttu-id="cb282-136">コンソールは、コードの下に式の結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="cb282-136">The Console prints out the result of the expression below your code.</span></span>  <span data-ttu-id="cb282-137">次の図では **、式を** 評価した後、コンソールに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb282-137">In the following figure, your **Console** should display the result after evaluating the expression.</span></span>  

1.  <span data-ttu-id="cb282-138">コンソールに次のコードを **入力します**。</span><span class="sxs-lookup"><span data-stu-id="cb282-138">Type the following code into the **Console**.</span></span>  <span data-ttu-id="cb282-139">コピー貼り付けではなく、文字別に入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="cb282-139">Try typing it out, character-by-character, rather than copy-pasting it.</span></span>  
    
    ```javascript
    function add(a, b=20)
    ```  
    
    <span data-ttu-id="cb282-140">構文に慣れていない場合は、関数の引数の既定値 `b=20` [を][Esma6DefaultParameterValues]定義します。</span><span class="sxs-lookup"><span data-stu-id="cb282-140">If you are unfamiliar with the `b=20` syntax, navigate to [define default values for function arguments][Esma6DefaultParameterValues].</span></span>  
    
1.  <span data-ttu-id="cb282-141">次に、定義した関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb282-141">Now, run the function that you just defined.</span></span>  
    
    :::row:::
       :::column span="":::
          ```javascript
          add(25);
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/console-javascript-example-console-playground.msft.png" alt-text="コード スニペット内の式を評価した後にコンソールが表示される" lightbox="../media/console-javascript-example-console-playground.msft.png":::
             <span data-ttu-id="cb282-143">コード **スニペット内** の式を評価した後にコンソールが表示される</span><span class="sxs-lookup"><span data-stu-id="cb282-143">The **Console** displays after evaluating the expressions in the code snippet</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
    `add(25)` <span data-ttu-id="cb282-144">2 番目の `45` 引数を指定せずに関数を呼び出す場合、既定値は `add` `b` `20` .</span><span class="sxs-lookup"><span data-stu-id="cb282-144">evaluates to `45` because when the `add` function is called without a second argument, `b` defaults to `20`.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="cb282-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="cb282-145">Next steps</span></span>  

<!--To explore more features related to running JavaScript in the **Console**, navigate to [Run JavaScript][DevToolsConsoleReference].  -->  

<!--todo: add console reference (run javascript) section when available  -->  

<span data-ttu-id="cb282-146">DevTools を使用すると、実行中にスクリプトを一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="cb282-146">DevTools lets you pause a script in the middle of running.</span></span>  <span data-ttu-id="cb282-147">一時停止中に、コンソールを使用して、 その時点でページまたはページを表示および `window` `DOM` 変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb282-147">While you are paused, you may use the **Console** to view and change the `window` or `DOM` of the page at that moment in time.</span></span>  <span data-ttu-id="cb282-148">ワークフローは強力なデバッグ ワークフローになります。</span><span class="sxs-lookup"><span data-stu-id="cb282-148">The workflow makes for a powerful debugging workflow.</span></span>  <span data-ttu-id="cb282-149">対話型のチュートリアルでは、[JavaScript のデバッグの開始] [に移動します][DevToolsJavascriptIndex]。</span><span class="sxs-lookup"><span data-stu-id="cb282-149">For an interactive tutorial, navigate to [Get Started With Debugging JavaScript][DevToolsJavascriptIndex].</span></span>  

<span data-ttu-id="cb282-150">コンソール **には** 、ページの操作を容易にする一連の便利な機能もあります。</span><span class="sxs-lookup"><span data-stu-id="cb282-150">The **Console** also has a set of convenience functions that make it easier to interact with a page.</span></span>  <span data-ttu-id="cb282-151">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb282-151">For example:</span></span>  

*   <span data-ttu-id="cb282-152">要素を選択するために入力 `document.querySelector()` するのではなく、と入力します `$()` 。</span><span class="sxs-lookup"><span data-stu-id="cb282-152">Rather than typing `document.querySelector()` to select an element, type `$()`.</span></span>  <span data-ttu-id="cb282-153">この構文は jQuery にインスパイアされますが、実際には jQuery ではありません。</span><span class="sxs-lookup"><span data-stu-id="cb282-153">This syntax is inspired by jQuery, but it is not actually jQuery.</span></span>  <span data-ttu-id="cb282-154">これは単なるエイリアスです `document.querySelector()` 。</span><span class="sxs-lookup"><span data-stu-id="cb282-154">It is just an alias for `document.querySelector()`.</span></span>  
*   `debug(function)` <span data-ttu-id="cb282-155">その関数の最初の行にブレークポイントを効果的に設定します。</span><span class="sxs-lookup"><span data-stu-id="cb282-155">effectively sets a breakpoint on the first line of that function.</span></span>  
*   `keys(object)` <span data-ttu-id="cb282-156">指定したオブジェクトのキーを含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="cb282-156">returns an array containing the keys of the specified object.</span></span>  

<span data-ttu-id="cb282-157">便利な関数の詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevToolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="cb282-157">For more information about the convenience functions, navigate to [Console Utilities API Reference][DevToolsConsoleUtilities].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="cb282-158">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="cb282-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleLoggingMessages]: ./log.md "コンソール ウィンドウでメッセージをログに記録する方法を|Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md#run-javascript "コンソール参照|Microsoft Docs"  
[DevToolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevToolsJavascriptIndex]: ../javascript/index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  

[2alityExpressionsVersusStatements]: https://2ality.com/2012/09/expressions-vs-statements.html "JavaScript の式とステートメント"  

[Esma6DefaultParameterValues]: https://es6-features.org/index#DefaultParameterValues "既定のパラメーター値 - 拡張パラメーター処理 - ECMAScript 6 - 新機能: 概要と&比較"  

[GlitchConsoleJavascriptExample]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/javascript/index.html "コンソール Javascript の例 |Glitch"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read–eval–print_loop "Read-eval-print ループ - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="cb282-167">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb282-167">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cb282-168">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/javascript) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="cb282-168">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/javascript) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cb282-170">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cb282-170">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
