---
description: Microsoft Edge DevTools コンソールの主な用途は、メッセージのログ記録と JavaScript の実行です。
title: コンソールの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 496caa4d304d9511d4b1c341846f377899ba4597
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399121"
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

# <a name="console-overview"></a><span data-ttu-id="3064e-104">コンソールの概要</span><span class="sxs-lookup"><span data-stu-id="3064e-104">Console overview</span></span>  

  

<span data-ttu-id="3064e-105">このページでは、Microsoft Edge DevTools コンソールによって Web ページの開発が容易になる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3064e-105">This page explains how the Microsoft Edge DevTools Console makes it easier to develop web pages.</span></span>  <span data-ttu-id="3064e-106">コンソール**には、** ログに記録されたメッセージ[](#viewing-logged-messages)の表示と JavaScript の実行という 2[つの主な用途があります](#running-javascript)。</span><span class="sxs-lookup"><span data-stu-id="3064e-106">The **Console** has 2 main uses: [viewing logged messages](#viewing-logged-messages) and [running JavaScript](#running-javascript).</span></span>  

## <a name="viewing-logged-messages"></a><span data-ttu-id="3064e-107">ログに記録されたメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="3064e-107">Viewing logged messages</span></span>  

<span data-ttu-id="3064e-108">Web 開発者は、多くの場合、コンソールにメッセージをログに記録して、JavaScript が期待通り動作しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="3064e-108">Web developers often log messages to the Console to make sure that their JavaScript is working as expected.</span></span>  <span data-ttu-id="3064e-109">メッセージをログに記録するには、JavaScript のような `console.log('Hello, Console!')` 式を挿入します。</span><span class="sxs-lookup"><span data-stu-id="3064e-109">To log a message, you insert an expression like `console.log('Hello, Console!')` into your JavaScript.</span></span>  <span data-ttu-id="3064e-110">ブラウザーで JavaScript を実行し、その式を処理すると、ブラウザーはメッセージをコンソールに記録 **します**。</span><span class="sxs-lookup"><span data-stu-id="3064e-110">When the browser runs your JavaScript and processes an expression like it, the browser logs the message to the **Console**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3064e-111">ページの HTML と JavaScript。</span><span class="sxs-lookup"><span data-stu-id="3064e-111">The HTML and JavaScript for the page.</span></span>  
      
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
      <span data-ttu-id="3064e-112">次の図では、 **ページ** を読み込み、3 秒待機した結果がコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3064e-112">In the following figure, the **Console** displays the results of loading the page and waiting 3 seconds.</span></span>  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="[コンソール] パネル" lightbox="../media/console-console-demo.msft.png":::
         <span data-ttu-id="3064e-114">コンソール**ツール**</span><span class="sxs-lookup"><span data-stu-id="3064e-114">The **Console** tool</span></span>  
      :::image-end:::  
      
      <span data-ttu-id="3064e-115">ブラウザーがメッセージをログに記録する原因となるコード行を調してみてください。</span><span class="sxs-lookup"><span data-stu-id="3064e-115">Try to determine which lines of code caused the browser to log the messages.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3064e-116">Web 開発者は、次の 2 つの一般的な理由でメッセージをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3064e-116">Web developers log messages for the following 2 general reasons.</span></span>  

*   <span data-ttu-id="3064e-117">コードが正しい順序で実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3064e-117">Making sure that code is running in the right order.</span></span>  
*   <span data-ttu-id="3064e-118">特定の時点での変数の値の検査。</span><span class="sxs-lookup"><span data-stu-id="3064e-118">Inspecting the values of variables at a certain moment in time.</span></span>  

<span data-ttu-id="3064e-119">ログ記録の実践的なエクスペリエンスを得る場合は、「ログ メッセージの [使用を開始する」に移動します][DevtoolsConsoleLoggingMessages]。</span><span class="sxs-lookup"><span data-stu-id="3064e-119">To get hands-on experience with logging, navigate to [Get Started With Logging Messages][DevtoolsConsoleLoggingMessages].</span></span>  <span data-ttu-id="3064e-120">メソッドの完全な一覧 `console` を参照するには、コンソール [API リファレンス に移動します][DevToolsConsoleAPI]。</span><span class="sxs-lookup"><span data-stu-id="3064e-120">To browse the full list of `console` methods, navigate to the [Console API Reference][DevToolsConsoleAPI].</span></span>  <span data-ttu-id="3064e-121">メソッドの主な違いは、ログに記録されるデータの表示方法です。</span><span class="sxs-lookup"><span data-stu-id="3064e-121">The main difference between the methods is how the data being logged is displayed.</span></span>  

## <a name="running-javascript"></a><span data-ttu-id="3064e-122">JavaScript の実行</span><span class="sxs-lookup"><span data-stu-id="3064e-122">Running JavaScript</span></span>  

<span data-ttu-id="3064e-123">コンソール **も** [REPL です][WikiREPLoop]。</span><span class="sxs-lookup"><span data-stu-id="3064e-123">The **Console** is also a [REPL][WikiREPLoop].</span></span>  <span data-ttu-id="3064e-124">コンソールで JavaScript を実行 **して、** 検査するページを操作できます。</span><span class="sxs-lookup"><span data-stu-id="3064e-124">You may run JavaScript in the **Console** to interact with the page being inspected.</span></span>   

:::row:::
   :::column span="":::
      <span data-ttu-id="3064e-125">次の図では **、DevTools** ホームページの横にコンソールが表示されています。</span><span class="sxs-lookup"><span data-stu-id="3064e-125">In the following figure, the **Console** is shown next to the DevTools homepage.</span></span>  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools ホームページの横にあるコンソール ツール" lightbox="../media/devtools-console-empty.msft.png":::
         <span data-ttu-id="3064e-127">**DevTools**ホームページの横にあるコンソール ツール</span><span class="sxs-lookup"><span data-stu-id="3064e-127">The **Console** tool next to the DevTools homepage</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3064e-128">次の図では、コンソールを使用してページの上部見出しを **変更した後** 、同じページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3064e-128">In the following figure, the same page is shown after using the **Console** to change the top heading of the page.</span></span>
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="コンソールを使用してページの上部見出しを変更する" lightbox="../media/devtools-console-h1-changed.msft.png":::
         <span data-ttu-id="3064e-130">コンソールを **使用して** ページの上部見出しを変更する</span><span class="sxs-lookup"><span data-stu-id="3064e-130">Use the **Console** to change the top heading of the page</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="3064e-131">コンソールからページ**を変更すると**、コンソールがページのウィンドウ\*\*\*\* に完全にアクセス[できます][MDNWindow]。</span><span class="sxs-lookup"><span data-stu-id="3064e-131">Modifying the page from the **Console** is possible because the **Console** has full access to the [window][MDNWindow] of the page.</span></span>  <span data-ttu-id="3064e-132">DevTools には、ページの検査を容易にする便利な機能がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="3064e-132">DevTools has a few convenience functions that make it easier to inspect a page.</span></span>  <span data-ttu-id="3064e-133">たとえば、JavaScript にという関数が含まれているとします `hideModal` 。</span><span class="sxs-lookup"><span data-stu-id="3064e-133">For example, suppose that your JavaScript contains a function called `hideModal`.</span></span>  <span data-ttu-id="3064e-134">実行 `debug(hideModal)` すると、次に実行するコードの最初の行でコード `hideModal` が一時停止します。</span><span class="sxs-lookup"><span data-stu-id="3064e-134">Running `debug(hideModal)` pauses your code on the first line of `hideModal` the next time that you run it.</span></span>  <span data-ttu-id="3064e-135">ユーティリティ関数の完全な一覧の詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevtoolsConsoleUtilitiesDebug]。</span><span class="sxs-lookup"><span data-stu-id="3064e-135">For more information about the full list of utility functions, navigate to [Console Utilities API Reference][DevtoolsConsoleUtilitiesDebug].</span></span>  

<span data-ttu-id="3064e-136">JavaScript を実行する場合は、ページを操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3064e-136">When you run JavaScript you do not have to interact with the page.</span></span>  <span data-ttu-id="3064e-137">コンソールを使用して **、** ページに関係のない新しいコードを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="3064e-137">You may use the **Console** to try out new code unrelated to the page.</span></span>  <span data-ttu-id="3064e-138">たとえば、組み込みの JavaScript Array [map()][MDNMap] メソッドについて学習し、それを試したいとします。</span><span class="sxs-lookup"><span data-stu-id="3064e-138">For example, suppose you just learned about the built-in JavaScript Array [map()][MDNMap] method, and you want to experiment with it.</span></span>  
<span data-ttu-id="3064e-139">コンソール **は** 、関数を試してみるのに便利な場所です。</span><span class="sxs-lookup"><span data-stu-id="3064e-139">The **Console** is a good place to try out the function.</span></span>  

<span data-ttu-id="3064e-140">コンソールで JavaScript を実行する方法の詳細\*\*\*\* については、「JavaScript の実行を開始する[」に移動します][DevtoolsConsoleRunningJavascript]。</span><span class="sxs-lookup"><span data-stu-id="3064e-140">For more hands-on experience with running JavaScript in the **Console**, navigate to [Get Started With Running JavaScript][DevtoolsConsoleRunningJavascript].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3064e-141">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3064e-141">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleLoggingMessages]: ./log.md "コンソール ウィンドウでメッセージをログに記録する方法を|Microsoft Docs"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "コンソール ウィンドウでの JavaScript の実行の開始|Microsoft Docs"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "debug - コンソール ユーティリティ API リファレンス |Microsoft Docs"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "Array.prototype.map() |MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "ウィンドウ |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "Read-eval-print ループ - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="3064e-149">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3064e-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3064e-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="3064e-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3064e-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3064e-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
