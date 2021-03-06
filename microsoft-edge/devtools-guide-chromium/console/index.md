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

# <a name="console-overview"></a>コンソールの概要  

  

このページでは、Microsoft Edge DevTools コンソールによって Web ページの開発が容易になる方法について説明します。  コンソール**には、** ログに記録されたメッセージ[](#viewing-logged-messages)の表示と JavaScript の実行という 2[つの主な用途があります](#running-javascript)。  

## <a name="viewing-logged-messages"></a>ログに記録されたメッセージの表示  

Web 開発者は、多くの場合、コンソールにメッセージをログに記録して、JavaScript が期待通り動作しているのを確認します。  メッセージをログに記録するには、JavaScript のような `console.log('Hello, Console!')` 式を挿入します。  ブラウザーで JavaScript を実行し、その式を処理すると、ブラウザーはメッセージをコンソールに記録 **します**。  

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
      次の図では、 **ページ** を読み込み、3 秒待機した結果がコンソールに表示されます。  
      
      :::image type="complex" source="../media/console-console-demo.msft.png" alt-text="[コンソール] パネル" lightbox="../media/console-console-demo.msft.png":::
         コンソール**ツール**  
      :::image-end:::  
      
      ブラウザーがメッセージをログに記録する原因となるコード行を調してみてください。  
   :::column-end:::
:::row-end:::  

Web 開発者は、次の 2 つの一般的な理由でメッセージをログに記録します。  

*   コードが正しい順序で実行されている必要があります。  
*   特定の時点での変数の値の検査。  

ログ記録の実践的なエクスペリエンスを得る場合は、「ログ メッセージの [使用を開始する」に移動します][DevtoolsConsoleLoggingMessages]。  メソッドの完全な一覧 `console` を参照するには、コンソール [API リファレンス に移動します][DevToolsConsoleAPI]。  メソッドの主な違いは、ログに記録されるデータの表示方法です。  

## <a name="running-javascript"></a>JavaScript の実行  

コンソール **も** [REPL です][WikiREPLoop]。  コンソールで JavaScript を実行 **して、** 検査するページを操作できます。   

:::row:::
   :::column span="":::
      次の図では **、DevTools** ホームページの横にコンソールが表示されています。  
      
      :::image type="complex" source="../media/devtools-console-empty.msft.png" alt-text="DevTools ホームページの横にあるコンソール ツール" lightbox="../media/devtools-console-empty.msft.png":::
         **DevTools**ホームページの横にあるコンソール ツール  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      次の図では、コンソールを使用してページの上部見出しを **変更した後** 、同じページが表示されます。
      
      :::image type="complex" source="../media/devtools-console-h1-changed.msft.png" alt-text="コンソールを使用してページの上部見出しを変更する" lightbox="../media/devtools-console-h1-changed.msft.png":::
         コンソールを **使用して** ページの上部見出しを変更する  
      :::image-end:::  
   :::column-end:::
:::row-end:::

コンソールからページ**を変更すると**、コンソールがページのウィンドウ**** に完全にアクセス[できます][MDNWindow]。  DevTools には、ページの検査を容易にする便利な機能がいくつか含まれています。  たとえば、JavaScript にという関数が含まれているとします `hideModal` 。  実行 `debug(hideModal)` すると、次に実行するコードの最初の行でコード `hideModal` が一時停止します。  ユーティリティ関数の完全な一覧の詳細については、「コンソール ユーティリティ [API リファレンス」に移動します][DevtoolsConsoleUtilitiesDebug]。  

JavaScript を実行する場合は、ページを操作する必要があります。  コンソールを使用して **、** ページに関係のない新しいコードを試してみてください。  たとえば、組み込みの JavaScript Array [map()][MDNMap] メソッドについて学習し、それを試したいとします。  
コンソール **は** 、関数を試してみるのに便利な場所です。  

コンソールで JavaScript を実行する方法の詳細**** については、「JavaScript の実行を開始する[」に移動します][DevtoolsConsoleRunningJavascript]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

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
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
