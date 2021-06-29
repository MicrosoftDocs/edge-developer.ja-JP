---
description: 開発者ツール内のコンソール ツールMicrosoft Edge紹介します。
title: コンソールの使用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: badcaae0ad637fe7a027f78d00daf9133789693e
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624746"
---
# <a name="use-the-console"></a><span data-ttu-id="83734-104">コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="83734-104">Use the Console</span></span>  

<span data-ttu-id="83734-105">**DevTools**のコンソール ツールは、いくつかのタスクを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="83734-105">The **Console** tool of the DevTools helps you with several tasks.</span></span>  <span data-ttu-id="83734-106">次の一覧には、いくつかのタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83734-106">The following list includes some of the tasks.</span></span>  

*   <span data-ttu-id="83734-107">現在のプロジェクトで何かが機能しない理由を確認し、 [問題を追跡します][DevtoolsConsoleConsoleDebugJavascript]。</span><span class="sxs-lookup"><span data-stu-id="83734-107">Find out why something isn't working in the current project and [track down problems][DevtoolsConsoleConsoleDebugJavascript].</span></span>  
*   <span data-ttu-id="83734-108">[ブラウザーの Web プロジェクトに関する][DevtoolsConsoleConsoleFilters] 情報をログ メッセージとして取得します。</span><span class="sxs-lookup"><span data-stu-id="83734-108">[Get information about the web project][DevtoolsConsoleConsoleFilters] in the browser as log messages.</span></span>  
*   <span data-ttu-id="83734-109">[デバッグの][DevtoolsConsoleConsoleLog] 目的でスクリプトに情報をログインします。</span><span class="sxs-lookup"><span data-stu-id="83734-109">[Log information][DevtoolsConsoleConsoleLog] in scripts for debugging purposes.</span></span>  
*   <span data-ttu-id="83734-110">[REPL 環境で JavaScript][DevtoolsConsoleConsoleJavascript] 式を [使用してみてください][WikiReadEvalPrintLoop] 。</span><span class="sxs-lookup"><span data-stu-id="83734-110">[Try JavaScript expressions][DevtoolsConsoleConsoleJavascript] live in a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  
*   <span data-ttu-id="83734-111">[JavaScript を使用してブラウザーで Web][DevtoolsConsoleConsoleDomInteraction] プロジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="83734-111">[Interact with the web project in the browser][DevtoolsConsoleConsoleDomInteraction] using JavaScript.</span></span>  
    
<span data-ttu-id="83734-112">コンソール **は、** 他のツールと一緒に使うのに最適なコンパニオン ツールです。</span><span class="sxs-lookup"><span data-stu-id="83734-112">The **Console** is a great companion tool to use with others tools.</span></span>  <span data-ttu-id="83734-113">コンソール **は、JavaScript** を使用して現在の Web ページの機能のスクリプト作成、検査、操作を行う強力な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="83734-113">The **Console** provides a powerful way to script functionality, inspect, and manipulate the current webpage using JavaScript.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-main.msft.png" alt-text="上部パネルでコンソール ツールを開く" lightbox="../media/console-intro-console-main.msft.png":::
         <span data-ttu-id="83734-115">上部 **パネル** でコンソール ツールを開く</span><span class="sxs-lookup"><span data-stu-id="83734-115">The **Console** tool open in the upper panel</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-intro-console-panel.msft.png" alt-text="下部パネルのコンソールで、[要素] ツールを開きます。" lightbox="../media/console-intro-console-panel.msft.png":::
         <span data-ttu-id="83734-117">**下部** パネルのコンソールで、[要素] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="83734-117">**Console** in the lower panel with the **Elements** tool open above it</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="83734-118">コンソールを直接開く最も速**い方法**は `Control` + `Shift` + `J` 、\(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択する方法です。</span><span class="sxs-lookup"><span data-stu-id="83734-118">The fastest way to directly open the **Console** is to select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

## <a name="error-reports-and-console"></a><span data-ttu-id="83734-119">エラー レポートとコンソール</span><span class="sxs-lookup"><span data-stu-id="83734-119">Error reports and Console</span></span>  

<span data-ttu-id="83734-120">**コンソール** は、JavaScript と接続エラーが報告される既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="83734-120">**Console** is the default place where JavaScript and connectivity errors are reported.</span></span>  <span data-ttu-id="83734-121">エラーが発生した場合は、**エラー**と警告の数を提供\*\*\*\* する DevTools 設定アイコンの横に [問題] カウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83734-121">If any errors occur, the **Issues counter** is displayed next to the **Settings** icon in DevTools that provides the number of errors and warnings.</span></span>  <span data-ttu-id="83734-122">[問題 **] カウンターを選択** して [問題] ツール **を開** き、問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="83734-122">Select the **Issues counter** to open the **Issues** tool and display the problem.</span></span>  <span data-ttu-id="83734-123">詳細については、「コンソールで報告された [デバッグ エラー」に移動します][DevtoolsConsoleConsoleDebugJavascript]。</span><span class="sxs-lookup"><span data-stu-id="83734-123">For more information, navigate to [Debug errors reported in Console][DevtoolsConsoleConsoleDebugJavascript].</span></span>

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools は、コンソールでエラーに関する詳細情報を提供します。" lightbox="../media/console-debug-displays-error.msft.png":::
   <span data-ttu-id="83734-125">DevTools は、コンソールでエラーに関する詳細情報を提供 **します。**</span><span class="sxs-lookup"><span data-stu-id="83734-125">DevTools gives detailed information about the error in the **Console**</span></span>  
:::image-end:::  

## <a name="inspect-and-filter-information-on-the-current-webpage"></a><span data-ttu-id="83734-126">現在の Web ページの情報を検査してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="83734-126">Inspect and filter information on the current webpage</span></span>  

<span data-ttu-id="83734-127">Web ページで DevTools を開いた場合、コンソールに膨大な量の情報が表示される可能性 **があります**。</span><span class="sxs-lookup"><span data-stu-id="83734-127">When you open DevTools on a webpage, there may be an overwhelming amount of information in the **Console**.</span></span>  <span data-ttu-id="83734-128">重要な情報を特定する必要がある場合、情報の量が問題になります。</span><span class="sxs-lookup"><span data-stu-id="83734-128">The amount of information becomes a problem when you need to identify important information.</span></span>  <span data-ttu-id="83734-129">アクションが必要な重要な情報を表示するには、DevTools [の Issues][DevtoolsIssuesIndex] ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="83734-129">To view the important information that needs action, use the [Issues][DevtoolsIssuesIndex] tool in DevTools.</span></span>

<span data-ttu-id="83734-130">問題は、コンソールから [問題\*\*\*\*] ツールに徐**々に移動**されています。</span><span class="sxs-lookup"><span data-stu-id="83734-130">Issues are gradually being moved from the **Console** to the **Issues** tool.</span></span>  <span data-ttu-id="83734-131">ただし、コンソールには多くの情報がまだ残っています。\*\*\*\* コンソールの自動ログオプションとフィルター オプションについて知るのが良い理由**です**。</span><span class="sxs-lookup"><span data-stu-id="83734-131">However, there's still a lot of information in **Console**, which is why it's a good idea to know about the automated log and filter options in the **Console**.</span></span>  <span data-ttu-id="83734-132">詳細については、「Filter Console メッセージ [」に移動します][DevtoolsConsoleConsoleFilters]。</span><span class="sxs-lookup"><span data-stu-id="83734-132">For more information, navigate to [Filter Console messages][DevtoolsConsoleConsoleFilters].</span></span>

:::image type="complex" source="../media/console-intro-noise.msft.png" alt-text="メッセージの完全なコンソールを持つ DevTools" lightbox="../media/console-intro-noise.msft.png":::
   <span data-ttu-id="83734-134">メッセージの完全な **コンソールを持つ** DevTools</span><span class="sxs-lookup"><span data-stu-id="83734-134">DevTools with a **Console** full of messages</span></span>  
:::image-end:::  

## <a name="log-information-to-display-in-the-console"></a><span data-ttu-id="83734-135">コンソールに表示するログ情報</span><span class="sxs-lookup"><span data-stu-id="83734-135">Log information to display in the Console</span></span>  

<span data-ttu-id="83734-136">コンソールの最も一般的な **使用例は** 、メソッドまたは他の同様の方法を使用してスクリプトから情報 `console.log()` をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="83734-136">The most popular use case for the **Console** is logging information from your scripts using the `console.log()` method or other similar methods.</span></span>  <span data-ttu-id="83734-137">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-137">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-138">コンソールを**開く**場合は `Control` + `Shift` + `J` 、\(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="83734-138">To open **Console**, select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="83734-139">[コンソール メッセージ [の例: ログ、情報][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]、エラー、警告] に移動するか、コンソールで次のコード スニペットをコピーして実行 **します**。</span><span class="sxs-lookup"><span data-stu-id="83734-139">Navigate to [Console messages examples: log, info, error and warn][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml], or copy and run the following code snippet in the **Console**.</span></span>  
    
    ```javascript
    console.log('This is a log message');
    console.info('This is some information'); 
    console.error('This is an error');
    console.warn('This is a warning');
    console.log(document.body.getBoundingClientRect());
    console.table(document.body.getBoundingClientRect());
    let technologies = ["HTML", "CSS", "SVG", "ECMAScript"];
    console.groupCollapsed('Technolgies');
    technologies.forEach(tech => {console.info(tech);})
    console.groupEnd('Technolgies');
    ```  
    
1.  <span data-ttu-id="83734-140">コンソール **に結果** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83734-140">The **Console** displays the results.</span></span>  
    
    :::image type="complex" source="../media/console-intro-logging.msft.png" alt-text="デモ コードによって引き起こされたメッセージの完全なコンソール" lightbox="../media/console-intro-logging.msft.png":::
       <span data-ttu-id="83734-142">**デモ** コードによって引き起こされたメッセージの完全なコンソール</span><span class="sxs-lookup"><span data-stu-id="83734-142">**Console** full of messages caused by demo code</span></span>  
    :::image-end:::  
    
<span data-ttu-id="83734-143">コンソールを使用する場合は、多くの便利な方法を使用 **できます**。</span><span class="sxs-lookup"><span data-stu-id="83734-143">Many useful methods are available when you work with the **Console**.</span></span>  <span data-ttu-id="83734-144">詳細については、「コンソール ツールでメッセージ [をログに記録する」に移動します][DevtoolsConsoleConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="83734-144">For more information, navigate to [Log messages in the Console tool][DevtoolsConsoleConsoleLog].</span></span>  

## <a name="try-your-javascript-live-in-the-console"></a><span data-ttu-id="83734-145">コンソールで JavaScript をライブで試す</span><span class="sxs-lookup"><span data-stu-id="83734-145">Try your JavaScript live in the Console</span></span>  

<span data-ttu-id="83734-146">コンソール **は** 、情報をログに記録する場所ではない。</span><span class="sxs-lookup"><span data-stu-id="83734-146">The **Console** isn't only a place to log information.</span></span>  <span data-ttu-id="83734-147">コンソール **は** [REPL 環境][WikiReadEvalPrintLoop] です。</span><span class="sxs-lookup"><span data-stu-id="83734-147">The **Console** is a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  <span data-ttu-id="83734-148">コンソールに JavaScript を記述 **すると、コード**はすぐに実行されます。</span><span class="sxs-lookup"><span data-stu-id="83734-148">When you write any JavaScript in the **Console**, the code runs immediately.</span></span>  <span data-ttu-id="83734-149">いくつかの新しい JavaScript 機能をテストしたり、簡単な計算を行う場合に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="83734-149">You may find it useful to test some new JavaScript features or to do some quick calculations.</span></span>  <span data-ttu-id="83734-150">また、オートコンプリート、構文の強調表示、履歴など、最新の編集環境で必要なすべての機能を取得できます。</span><span class="sxs-lookup"><span data-stu-id="83734-150">Also, you get all of the features you expect from a modern editing environment, such as autocompletion, syntax highlighting, and history.</span></span>  <span data-ttu-id="83734-151">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-151">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-152">[コンソール] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="83734-152">Navigate to the **Console**.</span></span>  
1.  <span data-ttu-id="83734-153">「`2 + 2`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="83734-153">Type `2 + 2`.</span></span>  
    
<span data-ttu-id="83734-154">コンソール **は、** 次の行 `4` に結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="83734-154">The **Console** displays the result `4` on the following line.</span></span>  <span data-ttu-id="83734-155">この **熱心な評価** 機能は、コードで間違いを犯していないとデバッグして確認する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="83734-155">This **Eager evaluation** feature is useful to debug and verify that you aren't making mistakes in your code.</span></span>  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="コンソールには、入力時に 2 + 2 ライブの結果が表示されます。" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   <span data-ttu-id="83734-157">コンソール **は、** 入力時に `2 + 2` ライブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="83734-157">The **Console** displays the result of `2 + 2` live as you type it</span></span>  
:::image-end:::  

<span data-ttu-id="83734-158">コンソールで JavaScript 式を **実行し、** 必要に応じて結果を表示するには、 を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="83734-158">To run the JavaScript expression in the **Console** and optionally display a result, select `Enter`.</span></span>  <span data-ttu-id="83734-159">次に、コンソールで実行する次の JavaScript コードを記述 **できます**。</span><span class="sxs-lookup"><span data-stu-id="83734-159">Then, you can write the next JavaScript code to run in the **Console**.</span></span>  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="複数行の JavaScript コードを連続して実行する" lightbox="../media/console-javascript-several-expressions.msft.png":::
   <span data-ttu-id="83734-161">複数行の JavaScript コードを連続して実行する</span><span class="sxs-lookup"><span data-stu-id="83734-161">Run several lines of JavaScript code in succession</span></span>  
:::image-end:::  

<span data-ttu-id="83734-162">既定では、JavaScript コードを 1 行で実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-162">By default, you run JavaScript code on a single line.</span></span>  <span data-ttu-id="83734-163">行を実行するには、JavaScript を入力してから、 を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="83734-163">To run a line, type your JavaScript and then select `Enter`.</span></span>  <span data-ttu-id="83734-164">単一行の制限を回避するには、代わりに `Shift` + `Enter` を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="83734-164">To work around the single-line limitation, select `Shift`+`Enter` instead of `Enter`.</span></span>  <span data-ttu-id="83734-165">他のコマンド ライン エクスペリエンスと同様に、以前の JavaScript コマンドにアクセスするには、 を選択します `Arrow-Up` 。</span><span class="sxs-lookup"><span data-stu-id="83734-165">Similar to other command-line experiences, to access your previous JavaScript commands, select `Arrow-Up`.</span></span>  <span data-ttu-id="83734-166">コンソールのオートコンプリート機能 **は、不** 慣れなメソッドについて学ぶのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="83734-166">The autocompletion feature of the **Console** is a great way to learn about unfamiliar methods.</span></span>  <span data-ttu-id="83734-167">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-167">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-168">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="83734-168">Open the **Console**.</span></span>  
1.  <span data-ttu-id="83734-169">「`doc`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="83734-169">Type `doc`.</span></span>  
1.  <span data-ttu-id="83734-170">ドロップダウン `document` メニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="83734-170">Choose `document` from the dropdown menu.</span></span>  
1.  <span data-ttu-id="83734-171">キーを `tab` 選択して選択します。</span><span class="sxs-lookup"><span data-stu-id="83734-171">Select the `tab` key to choose it.</span></span>  
1.  <span data-ttu-id="83734-172">「`.bo`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="83734-172">Type `.bo`.</span></span>  
1.  <span data-ttu-id="83734-173">を `tab` 選択して取得します `document.body` 。</span><span class="sxs-lookup"><span data-stu-id="83734-173">Select `tab` to get `document.body`.</span></span>  
1.  <span data-ttu-id="83734-174">現在の Web ページの本文で使用できるプロパティとメソッドの完全な一覧を表示するには、別の値 `.` を入力します。</span><span class="sxs-lookup"><span data-stu-id="83734-174">Type another `.` to display the complete list of properties and methods available on the body of the current webpage.</span></span>  
    
<span data-ttu-id="83734-175">コンソールを操作する方法の詳細については **、「JavaScript**環境として [コンソール」に移動します][DevtoolsConsoleConsoleJavascript]。</span><span class="sxs-lookup"><span data-stu-id="83734-175">For more information about all the ways to work with **Console**, navigate to [Console as a JavaScript environment][DevtoolsConsoleConsoleJavascript].</span></span>  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 式のコンソールオートコンプリート" lightbox="../media/console-javascript-autocomplete.msft.png":::
   <span data-ttu-id="83734-177">JavaScript**式の**コンソールオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="83734-177">**Console** autocompletion of JavaScript expressions</span></span>  
:::image-end:::  

## <a name="interact-with-the-current-webpage-in-the-browser"></a><span data-ttu-id="83734-178">ブラウザーで現在の Web ページを操作する</span><span class="sxs-lookup"><span data-stu-id="83734-178">Interact with the current webpage in the browser</span></span>  

<span data-ttu-id="83734-179">コンソール **は** 、ブラウザーの [Window][MdnDocsWebApiWindow] オブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="83734-179">The **Console** has access to the [Window][MdnDocsWebApiWindow] object of the browser.</span></span>  <span data-ttu-id="83734-180">現在の Web ページを操作するスクリプトを記述できます。</span><span class="sxs-lookup"><span data-stu-id="83734-180">You can write scripts that interact with the current webpage.</span></span>  <span data-ttu-id="83734-181">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-181">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-182">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="83734-182">Open the **Console**.</span></span>  
1.  <span data-ttu-id="83734-183">次のコード スニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="83734-183">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    document.querySelector('h1').innerHTML
    ```  
    
:::image type="complex" source="../media/console-intro-reading-DOM.msft.png" alt-text="トップ 見出し (h1) コンテンツを DOM からコピーし、コンソールに表示する" lightbox="../media/console-intro-reading-DOM.msft.png":::
   <span data-ttu-id="83734-185">DOM からトップ 見出し \( \) コンテンツをコピーし `h1` 、コンソールに表示 **する**</span><span class="sxs-lookup"><span data-stu-id="83734-185">Copy the top heading \(`h1`\) content from the DOM and display in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="83734-186">Web ページからの読み取りだけでなく、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="83734-186">Instead of only reading from the webpage, you can also change it.</span></span>  <span data-ttu-id="83734-187">Web ページを変更するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-187">To try changing the webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-188">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="83734-188">Open the **Console**.</span></span>  
1.  <span data-ttu-id="83734-189">次のコード スニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="83734-189">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    document.querySelector('h1').innerHTML = 'Rocking the Console';
    ```  
    
:::image type="complex" source="../media/console-intro-wrtiting-DOM.msft.png" alt-text="コンソールで DOM にテキストを書き込む" lightbox="../media/console-intro-wrtiting-DOM.msft.png":::
   <span data-ttu-id="83734-191">コンソールで DOM にテキストを書 **き込む**</span><span class="sxs-lookup"><span data-stu-id="83734-191">Write text to the DOM in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="83734-192">Web ページのメイン見出しを [コンソールの **ロック] に変更しました**。</span><span class="sxs-lookup"><span data-stu-id="83734-192">You changed the main heading of the webpage to **Rocking the Console**.</span></span>  <span data-ttu-id="83734-193">コンソール **ユーティリティ メソッド** を使用すると、現在の Web ページに簡単にアクセスして操作できます。</span><span class="sxs-lookup"><span data-stu-id="83734-193">The **Console Utility** methods make it easy to access and manipulate the current webpage.</span></span>  <span data-ttu-id="83734-194">詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevtoolsConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="83734-194">For more information, navigate to [Console Utilities API reference][DevtoolsConsoleUtilities].</span></span>  <span data-ttu-id="83734-195">たとえば、現在の Web ページ内のすべてのリンクの周囲に緑の枠線を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83734-195">For example, to add a green border around all the links in the current webpage, complete the following actions.</span></span>  

1.  <span data-ttu-id="83734-196">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="83734-196">Open the **Console**.</span></span>  
1.  <span data-ttu-id="83734-197">次のコード スニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="83734-197">Copy and paste the following code snippet.</span></span>  
    
    ```javascript
    $$('a').forEach(a => a.style.border='1px solid lime');
    ```  
    
:::image type="complex" source="../media/console-intro-changing-styles.msft.png" alt-text="コンソールを使用して要素の選択を操作する" lightbox="../media/console-intro-changing-styles.msft.png":::
    <span data-ttu-id="83734-199">コンソールを使用して要素の選択を操作 **する**</span><span class="sxs-lookup"><span data-stu-id="83734-199">Manipulate a selection of elements using the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="83734-200">DOM の操作の詳細については、「コンソールを使用して DOM を操作する [」に移動します][DevtoolsConsoleConsoleDomInteraction]。</span><span class="sxs-lookup"><span data-stu-id="83734-200">For more information about working with the DOM, navigate to [Use the Console to interact with the DOM][DevtoolsConsoleConsoleDomInteraction].</span></span>  

## <a name="learn-more-about-console"></a><span data-ttu-id="83734-201">コンソールの詳細</span><span class="sxs-lookup"><span data-stu-id="83734-201">Learn more about Console</span></span>  

<span data-ttu-id="83734-202">コンソールの詳細については、「**コンソール**リファレンス」、「[コンソール ユーティリティ API][DevtoolsConsoleUtilities]リファレンス」、および「コンソール API[リファレンス」に移動します][DevtoolsConsoleApi]。 [][DevtoolsConsoleReference]</span><span class="sxs-lookup"><span data-stu-id="83734-202">For more information about the **Console**, navigate to [Console reference][DevtoolsConsoleReference], [Console Utilities API reference][DevtoolsConsoleUtilities], and [Console API reference][DevtoolsConsoleApi].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="83734-203">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="83734-203">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleDebugJavascript]: ./console-debug-javascript.md "コンソール ウィンドウで報告されたデバッグ エラー|Microsoft Docs"  
[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "コンソールを使用して DOM ファイルを操作|Microsoft Docs" 
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "Filter Console メッセージ |Microsoft Docs"  
[DevtoolsConsoleConsoleJavascript]: ./console-javascript.md "JavaScript 環境としてのコンソール |Microsoft Docs"  
[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール でメッセージをログに記録|Microsoft Docs"  
[DevtoolsConsoleReference]: ./reference.md "コンソール参照|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "[問題] ツール を使用して問題を見つけて修正|Microsoft Docs"  
<!-- external links -->
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingDemoHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-demo.html "コンソール メッセージの例: ログ、情報、エラー、警告の|GitHub"  
[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "ウィンドウ |MDN"  
[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval-print ループ |Wikipedia"  
