---
description: Microsoft Edge DevTools コンソールの主な用途として、メッセージの記録と JavaScript の実行があります。
title: 本体の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 32272c3f76f715566ced66d11346985dc95dd290
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125266"
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

# 本体の概要  

  

このページでは、Microsoft Edge DevTools コンソールを使用して web ページを簡単に開発する方法について説明します。  本体には2つの主な用途があります。ログに記録された [メッセージを表示](#viewing-logged-messages) し、JavaScript を [実行](#running-javascript)します。  

## ログメッセージの表示  

Web 開発者は、JavaScript が予期したとおりに動作することを確認するために、コンソールにメッセージを記録することがよくあります。  メッセージを記録するには、JavaScript に like として式を挿入し `console.log('Hello, Console!')` ます。  ブラウザーで JavaScript が実行され、そのような式が表示されたら、コンソールにメッセージが記録されます。  

:::row:::
   :::column span="":::
      ページの HTML と JavaScript。  
      
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
      次の図に、ページの読み込みの結果と3秒間の待機の結果 **が表示されてい** ます。  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="コンソールパネル" lightbox="../media/console-console-demo.msft.png":::
         **コンソール**パネル  
      :::image-end:::  
      
      ブラウザーがメッセージをログに記録したコード行を特定してみてください。  
   :::column-end:::
:::row-end:::  

次の2つの一般的な理由により、Web 開発者はメッセージをログに記録します。  

*   コードが正しい順序で実行されていることを確認します。  
*   ある時点での変数の値を調べます。  

詳細については、「ログ [メッセージの概要][DevtoolsConsoleLoggingMessages] 」を参照してください。  メソッドの完全な一覧を参照するには、 [CONSOLE API リファレンス][DevToolsConsoleAPI] を参照してください `console` 。  メソッドの主な違いは、ログに記録されるデータがどのように表示されるかです。  

## JavaScript の実行  

**本体**も[REPL][WikiREPLoop]です。  **コンソール**で JavaScript を実行して、検査対象のページを操作することができます。   

:::row:::
   :::column span="":::
      次の図では、DevTools のホームページの横に **コンソール** が表示されています。  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="コンソールパネル" lightbox="../media/devtools-console-empty.msft.png":::
         DevTools ホームページの横にある **コンソール** パネル  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      次の図では、 **本体** を使ってページの先頭見出しを変更した後に、同じページが表示されています。
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="コンソールパネル" lightbox="../media/devtools-console-h1-changed.msft.png":::
         **コンソール**を使用してページの先頭見出しを変更する  
      :::image-end:::  
   :::column-end:::
:::row-end:::

本体からページを変更する **ことができる** のは、 **コンソール** の [ウィンドウ][MDNWindow] に対して完全にアクセスできるためです。  DevTools には、ページを簡単に調べるための便利な機能がいくつか用意されています。  たとえば、JavaScript にはという関数が含まれていると `hideModal` します。  Running を実行すると `debug(hideModal)` 、次回の実行時の最初の行にコードが一時停止し `hideModal` ます。  ユーティリティ関数の完全な一覧については、「 [コンソールユーティリティ API リファレンス][DevtoolsConsoleUtilitiesDebug]」を参照してください。  

JavaScript を実行しても、ページを操作する必要はありません。  この **本体** を使うと、ページに関係のない新しいコードを試すことができます。  たとえば、組み込みの JavaScript 配列 [map ()][MDNMap] メソッドについて学習し、その方法を試してみるとします。  
この機能を試すには、 **コンソール** が適切な場所です。  

**コンソール**での javascript の実行に関する実践的な操作については、「 [javascript の実行を開始][DevtoolsConsoleRunningJavascript]する」を参照してください。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleAPI]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleLoggingMessages]: ./log.md "コンソールでのメッセージの記録を開始する |Microsoft ドキュメント"  
[DevtoolsConsoleRunningJavascript]: ./javascript.md "本体の JavaScript の実行を開始する |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesDebug]: ./utilities.md#debug "デバッグ-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  

[MDNMap]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map "配列. .map () |MDN"  
[MDNWindow]: https://developer.mozilla.org/docs/Web/API/Window "Window |MDN"  

[WikiREPLoop]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop "読み取り– eval – print loop-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
