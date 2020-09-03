---
description: Microsoft Edge DevTools コンソールの主な用途として、メッセージの記録と JavaScript の実行があります。
title: 本体の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0cdce953b22d22f9a2bf8048a6eff89388aa6e2e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993157"
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





# <span data-ttu-id="12ab1-104">本体の概要</span><span class="sxs-lookup"><span data-stu-id="12ab1-104">Console Overview</span></span>   

  

<span data-ttu-id="12ab1-105">このページでは、Microsoft Edge DevTools コンソールを使用して web ページを簡単に開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12ab1-105">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span></span>  <span data-ttu-id="12ab1-106">本体には2つの主な用途があります。ログに記録された [メッセージを表示](#viewing-logged-messages) し、JavaScript を [実行](#running-javascript)します。</span><span class="sxs-lookup"><span data-stu-id="12ab1-106">The Console has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span></span>  

## <span data-ttu-id="12ab1-107">ログメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="12ab1-107">Viewing logged messages</span></span>   

<span data-ttu-id="12ab1-108">Web 開発者は、JavaScript が予期したとおりに動作することを確認するために、コンソールにメッセージを記録することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="12ab1-108">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span></span>  <span data-ttu-id="12ab1-109">メッセージを記録するには、JavaScript に like として式を挿入し `console.log('Hello, Console!')` ます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-109">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span></span>  <span data-ttu-id="12ab1-110">ブラウザーで JavaScript が実行され、そのような式が表示されたら、コンソールにメッセージが記録されます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-110">When the browser runs your JavaScript and sees an expression like that, it logs the message to the Console.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="12ab1-111">ページの HTML と JavaScript。</span><span class="sxs-lookup"><span data-stu-id="12ab1-111">The HTML and JavaScript for the page.</span></span>  
      
      ```html
      <!doctype html>
      <html>
          <head>
              <title>Console Demo</title>
          </head>
          <body>
              <h1>Hello, World!</h1>
              <script>
                  console.log('Loading!');
                  const h1 = document.querySelector('h1');
                  console.log(h1.textContent);
                  console.assert(document.querySelector('h2'), 'h2 not found!');
                  const artists = [
                      { first: 'René', last: 'Magritte' },
                      { first: 'Chaim', last: 'Soutine' },
                      { first: 'Henri', last: 'Matisse' }
                  ];
                  console.table(artists);
                  setTimeout(() => {
                      h1.textContent = 'Hello, Console!';
                      console.log(h1.textContent);
                  }, 3000);
              </script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12ab1-112">次の図に、ページの読み込みの結果と3秒間の待機の結果 **が表示されてい** ます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-112">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span></span>  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="コンソールパネル" lightbox="../media/console-console-demo.msft.png":::
         <span data-ttu-id="12ab1-114">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="12ab1-114">The **Console** panel</span></span>  
      :::image-end:::  
      
      <span data-ttu-id="12ab1-115">ブラウザーがメッセージをログに記録したコード行を特定してみてください。</span><span class="sxs-lookup"><span data-stu-id="12ab1-115">Try to determine which lines of code caused the browser to log the messages.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="12ab1-116">次の2つの一般的な理由により、Web 開発者はメッセージをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="12ab1-116">Web developers log messages for the following 2 general reasons.</span></span>  

*   <span data-ttu-id="12ab1-117">コードが正しい順序で実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="12ab1-117">Making sure that code is running in the right order.</span></span>  
*   <span data-ttu-id="12ab1-118">ある時点での変数の値を調べます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-118">Inspecting the values of variables at a certain moment in time.</span></span>  

<span data-ttu-id="12ab1-119">詳細については、「ログ [メッセージの概要][DevtoolsConsoleLoggingMessages] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ab1-119">See [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages] to get hands-on experience with logging.</span></span>  <span data-ttu-id="12ab1-120">メソッドの完全な一覧を参照するには、 [CONSOLE API リファレンス][DevToolsConsoleAPI] を参照してください `console` 。</span><span class="sxs-lookup"><span data-stu-id="12ab1-120">See the [Console API Reference][DevToolsConsoleAPI] to browse the full list of `console` methods.</span></span>  <span data-ttu-id="12ab1-121">メソッドの主な違いは、ログに記録されるデータがどのように表示されるかです。</span><span class="sxs-lookup"><span data-stu-id="12ab1-121">The main difference between the methods is how the data being logged is displayed.</span></span>  

## <span data-ttu-id="12ab1-122">JavaScript の実行</span><span class="sxs-lookup"><span data-stu-id="12ab1-122">Running JavaScript</span></span>   

<span data-ttu-id="12ab1-123">**本体**も[REPL][WikiREPLoop]です。</span><span class="sxs-lookup"><span data-stu-id="12ab1-123">The **Console** is also a [REPL][WikiREPLoop].</span></span>  <span data-ttu-id="12ab1-124">**コンソール**で JavaScript を実行して、検査対象のページを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-124">You may run JavaScript in the **Console** to interact with the page being inspected.</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="12ab1-125">次の図では、DevTools のホームページの横に **コンソール** が表示されています。</span><span class="sxs-lookup"><span data-stu-id="12ab1-125">In the following figure, the **Console** is shown next to the DevTools homepage.</span></span>  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools ホームページの横にあるコンソールパネル" lightbox="../media/devtools-console-empty.msft.png":::
         <span data-ttu-id="12ab1-127">DevTools ホームページの横にある **コンソール** パネル</span><span class="sxs-lookup"><span data-stu-id="12ab1-127">The **Console** panel next to the DevTools homepage</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12ab1-128">次の図では、 **本体** を使ってページの先頭見出しを変更した後に、同じページが表示されています。</span><span class="sxs-lookup"><span data-stu-id="12ab1-128">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span></span>
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="コンソールを使用してページの先頭見出しを変更する" lightbox="../media/devtools-console-h1-changed.msft.png":::
         <span data-ttu-id="12ab1-130">**コンソール**を使用してページの先頭見出しを変更する</span><span class="sxs-lookup"><span data-stu-id="12ab1-130">Use the **Console** to change the top heading of the page</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="12ab1-131">本体からページを変更する **ことができる** のは、 **コンソール** の [ウィンドウ][MDNWindow] に対して完全にアクセスできるためです。</span><span class="sxs-lookup"><span data-stu-id="12ab1-131">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span></span>  <span data-ttu-id="12ab1-132">DevTools には、ページを簡単に調べるための便利な機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="12ab1-132">DevTools has a few convenience functions that make it easier to inspect a page.</span></span>  <span data-ttu-id="12ab1-133">たとえば、JavaScript にはという関数が含まれていると `hideModal` します。</span><span class="sxs-lookup"><span data-stu-id="12ab1-133">For example, suppose that your JavaScript contains a function called `hideModal`.</span></span>  <span data-ttu-id="12ab1-134">Running を実行すると `debug(hideModal)` 、次回の実行時の最初の行にコードが一時停止し `hideModal` ます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-134">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span></span>  <span data-ttu-id="12ab1-135">ユーティリティ関数の完全な一覧について詳しくは、「 [コンソールユーティリティ API リファレンス][DevtoolsConsoleUtilitiesDebug]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12ab1-135">For more information about the full list of utility functions, see [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span></span>  

<span data-ttu-id="12ab1-136">JavaScript を実行しても、ページを操作する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12ab1-136">When you run JavaScript you do not have to interact with the page.</span></span>  <span data-ttu-id="12ab1-137">この **本体** を使うと、ページに関係のない新しいコードを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-137">You may use the **Console** to try out new code unrelated to the page.</span></span>  <span data-ttu-id="12ab1-138">たとえば、組み込みの JavaScript 配列 [map ()][MDNMap] メソッドについて学習し、その方法を試してみるとします。</span><span class="sxs-lookup"><span data-stu-id="12ab1-138">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span></span>  
<span data-ttu-id="12ab1-139">この機能を試すには、 **コンソール** が適切な場所です。</span><span class="sxs-lookup"><span data-stu-id="12ab1-139">The **Console** is a good place to try out the function.</span></span>  

<span data-ttu-id="12ab1-140">**コンソール**での javascript の実行に関する実践的な操作方法については、「[実行中の javascript の使用を開始][DevtoolsConsoleRunningJavascript]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ab1-140">For more hands-on experience with running JavaScript in the **Console**, see [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span></span>  

   

  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleLoggingMessages]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "本体の JavaScript の実行を開始する |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "デバッグ-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "配列. .map () |MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "Window |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "読み取り– eval – print loop-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="12ab1-148">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="12ab1-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="12ab1-149">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="12ab1-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="12ab1-151">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="12ab1-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
