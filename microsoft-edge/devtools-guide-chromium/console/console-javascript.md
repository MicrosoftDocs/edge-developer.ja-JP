---
description: JavaScript 環境として Microsoft Edge Developer Tools 内でコンソール ツールを使用する方法について説明します。
title: JavaScript 環境としてのコンソール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, JavaScript, Web 開発, f12 ツール, devtools
ms.openlocfilehash: f75ac6d728c9a69542b2f58df85248759267f76d
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483536"
---
# <a name="the-console-as-a-javascript-environment"></a><span data-ttu-id="1e172-104">JavaScript 環境としてのコンソール</span><span class="sxs-lookup"><span data-stu-id="1e172-104">The Console as a JavaScript environment</span></span>  

<span data-ttu-id="1e172-105">ブラウザー **DevTools** 内のコンソール ツールは [REPL 環境][WikiReadEvalPrintLoop] です。</span><span class="sxs-lookup"><span data-stu-id="1e172-105">The **Console** tool inside the browser DevTools is a [REPL][WikiReadEvalPrintLoop] environment.</span></span>  <span data-ttu-id="1e172-106">これは、直ちに実行される JavaScript を **コンソール** に記述できるという意味です。</span><span class="sxs-lookup"><span data-stu-id="1e172-106">It means that you may write any JavaScript in the **Console** that runs immediately.</span></span>

<span data-ttu-id="1e172-107">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e172-107">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="1e172-108">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="1e172-108">Open the **Console**.</span></span>  
    *   <span data-ttu-id="1e172-109">`Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e172-109">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  
1.  <span data-ttu-id="1e172-110">「`2 + 2`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1e172-110">Type `2 + 2`.</span></span>  <span data-ttu-id="1e172-111">コンソール **では、** 入力中に次 `4` の行に結果が既に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e172-111">The **Console** already displays the result `4` on the next line while you type it.</span></span>  <span data-ttu-id="1e172-112">この `Eager evaluation` 機能は、有効な JavaScript を記述するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e172-112">The `Eager evaluation` feature helps you write valid JavaScript.</span></span>  <span data-ttu-id="1e172-113">間違っているかどうか、または有効な結果が存在するかどうかを入力すると、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e172-113">It displays the result while you type whether it's wrong or if a valid result exists.</span></span>  

:::image type="complex" source="../media/console-javascript-eager-evaluation.msft.png" alt-text="コンソールは、入力時に 2 + 2 ライブの結果を表示します。" lightbox="../media/console-javascript-eager-evaluation.msft.png":::
   <span data-ttu-id="1e172-115">**コンソールは** 、入力時に `2 + 2` ライブの結果を表示します</span><span class="sxs-lookup"><span data-stu-id="1e172-115">**Console** displays the result of `2 + 2` live as you type it</span></span>  
:::image-end:::  

<span data-ttu-id="1e172-116">[コンソール] を選択すると、JavaScript コマンドが実行され、結果が表示され、次の `Enter` コマンドを記述できます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1e172-116">If you select `Enter`, the **Console** runs the JavaScript command, gives you the result, and allows you to write the next command.</span></span>  

:::image type="complex" source="../media/console-javascript-several-expressions.msft.png" alt-text="複数の JavaScript 式を連続して実行する" lightbox="../media/console-javascript-several-expressions.msft.png":::
   <span data-ttu-id="1e172-118">複数の JavaScript 式を連続して実行する</span><span class="sxs-lookup"><span data-stu-id="1e172-118">Run several JavaScript expressions in succession</span></span>  
:::image-end:::  

## <a name="autocompletion-to-write-complex-expressions"></a><span data-ttu-id="1e172-119">複雑な式を記述するオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="1e172-119">Autocompletion to write complex expressions</span></span>

<span data-ttu-id="1e172-120">最後の例は恐ろしいと思われるかもしれませんが\*\*\*\*、コンソールは優れたオートコンプリート機能を使用して複雑な JavaScript を記述するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e172-120">The last example may seem scary, but the **Console** helps you write complex JavaScript using an excellent autocompletion feature.</span></span>  <span data-ttu-id="1e172-121">この機能は、以前知らなかったメソッドについて学ぶのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="1e172-121">This feature is a great way to learn about methods you didn't know before.</span></span>  

<span data-ttu-id="1e172-122">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e172-122">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="1e172-123">「`doc`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1e172-123">Type `doc`.</span></span>  
1.  <span data-ttu-id="1e172-124">ドロップダウン `document` メニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="1e172-124">Choose `document` from the dropdown menu.</span></span>  
1.  <span data-ttu-id="1e172-125">キーを `tab` 選択して選択します。</span><span class="sxs-lookup"><span data-stu-id="1e172-125">Select the `tab` key to choose it.</span></span>  
1.  <span data-ttu-id="1e172-126">「`.bo`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1e172-126">Type `.bo`.</span></span>  
1.  <span data-ttu-id="1e172-127">を `tab` 選択して取得します `document.body` 。</span><span class="sxs-lookup"><span data-stu-id="1e172-127">Select `tab` to get `document.body`.</span></span>  
1.  <span data-ttu-id="1e172-128">現在の Web ページの本文で使用可能なプロパティとメソッドの大きな一覧を取得するには、別のプロパティ `.` を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e172-128">Type another `.` to get a large list of possible properties and methods available on the body of the current webpage.</span></span>  

:::image type="complex" source="../media/console-javascript-autocomplete.msft.png" alt-text="JavaScript 式のコンソールオートコンプリート" lightbox="../media/console-javascript-autocomplete.msft.png":::
   <span data-ttu-id="1e172-130">JavaScript**式の**コンソールオートコンプリート</span><span class="sxs-lookup"><span data-stu-id="1e172-130">**Console** autocompletion of JavaScript expressions</span></span>  
:::image-end:::  

## <a name="console-history"></a><span data-ttu-id="1e172-131">コンソールの履歴</span><span class="sxs-lookup"><span data-stu-id="1e172-131">Console history</span></span>

<span data-ttu-id="1e172-132">他の多くのコマンド ライン エクスペリエンスと同様に、コマンドの履歴も持っています。</span><span class="sxs-lookup"><span data-stu-id="1e172-132">As with many other command-line experiences, you also have a history of commands.</span></span>  <span data-ttu-id="1e172-133">前 `Arrow Up` に入力したコマンドを表示する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="1e172-133">Select `Arrow Up` to display the commands you entered before.</span></span>  <span data-ttu-id="1e172-134">オートコンプリートでは、以前に入力したコマンドの履歴も保持されます。</span><span class="sxs-lookup"><span data-stu-id="1e172-134">Autocompletion also keeps a history of the commands you previously typed.</span></span>  <span data-ttu-id="1e172-135">以前のコマンドの最初の数文字を入力すると、テキスト ボックスに以前の選択肢が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e172-135">You may type the first few letters of earlier commands and your previous choices display in a textbox.</span></span>  

<span data-ttu-id="1e172-136">また、**コンソールには、** 生活を容易にする[][DevtoolsConsoleUtilities]ユーティリティメソッドもいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="1e172-136">Also, the **Console** also offers quite a few [utility methods][DevtoolsConsoleUtilities] that make your life easier.</span></span>  <span data-ttu-id="1e172-137">たとえば、コンソールで実行した最後の式の結果が常 `$_` に含 **まれるとします**。</span><span class="sxs-lookup"><span data-stu-id="1e172-137">For example, `$_` always contains the result of the last expression you ran in the **Console**.</span></span>

:::image type="complex" source="../media/console-javascript-console-history.msft.png" alt-text="コンソール$ $_ 式には、常に最後の結果が含まれる" lightbox="../media/console-javascript-console-history.msft.png":::
    <span data-ttu-id="1e172-139">コンソール `$_` の式には\*\*\*\* 常に最後の結果が含まれる</span><span class="sxs-lookup"><span data-stu-id="1e172-139">The `$_` expression in the **Console** always contains the last result</span></span>  
:::image-end:::  

## <a name="multiline-edits"></a><span data-ttu-id="1e172-140">複数行の編集</span><span class="sxs-lookup"><span data-stu-id="1e172-140">Multiline edits</span></span>

<span data-ttu-id="1e172-141">既定では、 **コンソールには JavaScript** 式を記述する行が 1 行しか表示されません。</span><span class="sxs-lookup"><span data-stu-id="1e172-141">By default, the **Console** only gives you one line to write your JavaScript expression.</span></span>  <span data-ttu-id="1e172-142">を選択すると、コードが実行されます `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1e172-142">You code runs when you select `Enter`.</span></span> <span data-ttu-id="1e172-143">1 行の制限は、ユーザーをイライラさせる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e172-143">The one line limitation may frustrate you.</span></span>  <span data-ttu-id="1e172-144">1 行の制限を回避するには、代わりに `Shift` + `Enter` を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1e172-144">To work around the one line limitation, select `Shift`+`Enter` instead of `Enter`.</span></span>  <span data-ttu-id="1e172-145">次の例では、表示される値は、すべての行が順番に実行された結果です。</span><span class="sxs-lookup"><span data-stu-id="1e172-145">In the following example, the value displayed is the result of all the lines run in order.</span></span>  

:::image type="complex" source="../media/console-javascript-multiline.msft.png" alt-text="Shift + Enter キーを押して複数行の JavaScript を記述すると、結果の値が順番に実行されます。" lightbox="../media/console-javascript-multiline.msft.png":::
   <span data-ttu-id="1e172-147">複数 `Shift` + `Enter` 行の JavaScript を記述する場合に選択すると、結果の値が順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e172-147">Select `Shift`+`Enter` to write several lines of JavaScript and the resulting value is run in order</span></span>  
:::image-end:::  

<span data-ttu-id="1e172-148">コンソールで複数行のステートメントを開始すると\*\*\*\*、自動的に認識されインデントされます。</span><span class="sxs-lookup"><span data-stu-id="1e172-148">If you start a multiline statement in the **Console**, it gets automatically recognized and indented.</span></span>  <span data-ttu-id="1e172-149">たとえば、中かっこでブロック ステートメントを開始する場合です。</span><span class="sxs-lookup"><span data-stu-id="1e172-149">For example, if you start a block statement with a curly brace.</span></span>  

:::image type="complex" source="../media/console-javascript-automatic-lineindent.msft.png" alt-text="コンソールでは、中かっことインデントを使用して複数行式が既に認識されています。" lightbox="../media/console-javascript-automatic-lineindent.msft.png":::
    <span data-ttu-id="1e172-151">**コンソール** では、中かっことインデントを使用して複数行式が既に認識されています。</span><span class="sxs-lookup"><span data-stu-id="1e172-151">**Console** already recognizes multiline expressions using curly braces and indents each for you</span></span>  
:::image-end:::  

## <a name="network-requests-using-top-level-await"></a><span data-ttu-id="1e172-152">トップ レベルの await() を使用したネットワーク要求</span><span class="sxs-lookup"><span data-stu-id="1e172-152">Network requests using top-level await()</span></span>  

<span data-ttu-id="1e172-153">独自のスクリプト以外に、**コンソール**は任意[][GithubTc39ProposalTopLevelAwait]の非同期 JavaScript を実行するためのトップ レベルの await をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1e172-153">Other than in your own scripts, **Console** supports [top level await][GithubTc39ProposalTopLevelAwait] to run arbitrary asynchronous JavaScript in it.</span></span>  <span data-ttu-id="1e172-154">たとえば、非同期関数で `fetch` ステートメントをラップ `await` せずに API を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e172-154">For example, use the `fetch` API without wrapping the `await` statement with an async function.</span></span>  

<span data-ttu-id="1e172-155">Microsoft Edge Developer Tools for microsoft Edge Developer Tools for Visual Studio [GitHub][GithubMicrosoftVscodeEdgeDevtools] リポジトリで最後の 50 の問題を取得するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e172-155">To get the last 50 issues filed on the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] GitHub repo, complete the following actions.</span></span>  

1.  <span data-ttu-id="1e172-156">コンソールを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="1e172-156">Open the **Console**.</span></span>  
1.  <span data-ttu-id="1e172-157">次のコード スニペットをコピーして貼り付け、10 エントリを含むオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e172-157">Copy and paste the following code snippet to get an object that contains 10 entries.</span></span>  
    
    ```javascript
    await ( await fetch(
    'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
    )).json();
    ```  
    
:::image type="complex" source="../media/console-javascript-top-level-await.msft.png" alt-text="コンソールは、トップ レベルの非同期フェッチ要求の結果を表示します。" lightbox="../media/console-javascript-top-level-await.msft.png":::
    <span data-ttu-id="1e172-159">**コンソール** は、トップ レベルの非同期要求の結果を表示 `fetch` します。</span><span class="sxs-lookup"><span data-stu-id="1e172-159">**Console** displays the result of a top-level async `fetch` request</span></span>  
:::image-end:::  

<span data-ttu-id="1e172-160">多くの情報が表示されますので、10 のエントリを認識するのは難しいです。</span><span class="sxs-lookup"><span data-stu-id="1e172-160">The 10 entries are hard to recognize, since a lot of information is displayed.</span></span>  <span data-ttu-id="1e172-161">幸いなことに、log メソッドを使用して、興味のある情報 `console.table()` のみを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e172-161">Luckily enough, you may use the `console.table()` log method to only receive the information in which you're interested.</span></span>  

:::image type="complex" source="../media/console-javascript-filtered-with-table.msft.png" alt-text="console.table を使用して、人間が読み取り可能な形式で最後の結果を表示する" lightbox="../media/console-javascript-filtered-with-table.msft.png":::
    <span data-ttu-id="1e172-163">使用して人間が読み取り可能な形式で最後の結果を表示する</span><span class="sxs-lookup"><span data-stu-id="1e172-163">Display the last result in a human readable format using</span></span> `console.table`  
:::image-end:::  

<span data-ttu-id="1e172-164">式から返されるデータを再利用するには、Console のユーティリティ `copy()` メソッドを使用 **します**。</span><span class="sxs-lookup"><span data-stu-id="1e172-164">To reuse the data returned from an expression, you may use the `copy()` utility method of the **Console**.</span></span>  <span data-ttu-id="1e172-165">次のコード スニペットは要求を送信し、応答からクリップボードにデータをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1e172-165">The following code snippet sends the request and copies the data from the response to the clipboard.</span></span>  

```javascript
copy(await (await fetch(
'https://api.github.com/repos/microsoft/vscode-edge-devtools/issues?state=all&per_page=50&page=1'
)).json())
```  

<span data-ttu-id="1e172-166">JavaScript **の機能** を実践し、簡単な計算を行う最適な方法としてコンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e172-166">Use the **Console** as a great way to practice JavaScript functionality and to do some quick calculations.</span></span>  <span data-ttu-id="1e172-167">実際の機能は、window オブジェクトにアクセスできる [という事実][MdnDocsWebApiWindow] です。</span><span class="sxs-lookup"><span data-stu-id="1e172-167">The real power is the fact that you have access to the [window][MdnDocsWebApiWindow] object.</span></span>  <span data-ttu-id="1e172-168">コンソールで [DOM を操作できます][DevtoolsConsoleConsoleDomInteraction]。</span><span class="sxs-lookup"><span data-stu-id="1e172-168">You may [interact with the DOM in Console][DevtoolsConsoleConsoleDomInteraction].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1e172-169">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1e172-169">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleDomInteraction]: ./console-dom-interaction.md "コンソールを使用して DOM ファイルを操作|Microsoft Docs"  
[DevtoolsConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubTc39ProposalTopLevelAwait]: https://github.com/tc39/proposal-top-level-await "ECMAScript 提案: トップ レベルの await - tc39/proposal-top-level-await |GitHub"

[MdnDocsWebApiWindow]: https://developer.mozilla.org/docs/Web/API/Window "ウィンドウ |MDN"  

[WikiReadEvalPrintLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval-print ループ |Wikipedia"  
