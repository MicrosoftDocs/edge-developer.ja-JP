---
description: メッセージをログに記録し、DevTools コンソールで JavaScript をMicrosoft Edgeする方法。
title: コンソール ツールでメッセージをログに記録する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d48a48de7b261a628ac99f58680deb119268a980
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483542"
---
# <a name="log-messages-in-the-console-tool"></a>コンソール ツールでメッセージをログに記録する  

ブラウザーが開発者向けツールを提供し始めて以来、 **コンソールは好** みです。  理由は簡単です。  

*   ほとんどのプログラミング コースでは、何が起こるかについての洞察を得るために何らかの印刷コマンドを出力する方法を学ぶ。  

DevTools の前に、ブラウザーでデバッグする `alert()` ステートメント `document.write()` またはステートメントに制限されています。  

コンソールに情報を記録 **する場合は**、多くのメソッドを使用できます。  API リファレンスで使用可能なすべてのメソッドを [確認します][DevtoolsConsoleApi]。  次のコード スニペットは、最も重要なメソッドの一覧です。  

```javascript
// prints the text to the console as  a log message
console.log('This is a log message')
// prints the text to the console as an informational message
console.info('This is some information') 
// prints the text to the console as an error message
console.error('This is an error')
// prints the text to the console as a warning
console.warn('This is a warning') 
```  

前のコード スニペットをコンソールにコピーして貼り付ける **か、コンソール** メッセージの例 (ログ、情報、エラー、警告 [) に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]。  **コンソール**で任意のメソッドを試してみると、メソッドとメソッドは同じことを行っているように見え、メソッドはメッセージの横にアイコンを表示し、メッセージのスタック トレースを検査する方法を示 `log()` `info()` `error()` `warn()` します[][WikiStackTrace]。  

:::image type="complex" source="../media/console-log-examples.msft.png" alt-text="コンソールには、異なるログ API からのメッセージが表示されます。" lightbox="../media/console-log-examples.msft.png":::
   コンソール **には、** 異なるログ API からのメッセージが表示されます。  
:::image-end:::  

ただし、コンソールの種類を使用してフィルター処理を行うことができますので、異なるログ タスクを使用して使用する方 `info()` `log()` [が良い方法です][DevtoolsConsoleConsoleFilters]。  

## <a name="different-types-of-logs"></a>さまざまな種類のログ  

ログ テキストの代わりに、有効な JavaScript または DOM 参照をコンソールに送信 **できます**。  コンソール **は** エレガントで、送信する種類を決定します。  次に、可能な限り最高の表現を提供します。  コンソールに次のコード スニペットをコピー**** して貼り付けるか、結果を表示するには、[コンソール メッセージの例: ログの種類][に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]。  

```javascript
let x = 2;
// logs the value of x
console.log(x);
// logs the name x and value of x
console.log({x})   
// logs a DOM reference  
console.log(document.querySelector('body'));
// logs an Object
console.log({"type":"life", "meaning": 42});
let w3techs = ['HTML', 'CSS', 'SVG', 'MathML'];
// logs an Array
console.log(w3techs);
```  

各結果は異なる方法で表示されます。  三角形を使用して情報を切り替え、各情報を詳細に分析します。  変数の中かっこの文字は、値のみを取得するが、発生した場所がわかりませんが、ログ メッセージの多くを避けるための便利な小さな `{}` `x` トリックです。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types.msft.png" alt-text="コンソールでさまざまな種類の変数をログに記録する" lightbox="../media/console-log-types.msft.png":::
         コンソールでさまざまな種類の変数をログに記録 **する**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types-expanded.msft.png" alt-text="拡張された追加情報を使用して、コンソール内の異なる種類の変数をログに記録する" lightbox="../media/console-log-types-expanded.msft.png":::
         拡張された追加情報を使用して、 **コンソール** 内の異なる種類の変数をログに記録する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="format-and-convert-values-with-specifiers"></a>指定子を使用して値の書式設定と変換を行う

すべてのログ メソッドの特別な機能は、ログ メッセージで指定子を使用できる機能です。  指定子はログ メッセージの一部であり、パーセント記号 \( \) 文字で始まるので、異なる形式で特定の値をログに記録し、それぞれを `%` 変換することもできます。  

*   `%s` ログを文字列として記録する
*   `%i` または `%d` ログを整数として記録する
*   `%f` 浮動小数点値としてのログ
*   `%o` 拡張可能な DOM 要素としてのログ
*   `%O` 展開可能な JavaScript オブジェクトとしてのログ
*   `%c` CSS を使用してメッセージのスタイルを設定できます

```javascript
// logs "10x console developer"
console.log('%ix %s developer', 10, 'console');
// logs PI => 3.141592653589793
console.log(Math.PI); 
// logs PI as an integer = 3
console.log('%i', Math.PI); 
// logs the webpage body as a DOM node
console.log('%o', document.body); 
// logs the body of the webpage as a JavaScript object with all properties
console.log('%O', document.body); 
// Displays the message as red and big
console.log('%cImportant message follows','color:red;font-size:40px');
```  

最初の例では、指定子の置換順序が文字列に続くパラメーターの順序を表示します。  結果を表示するには、前のコード スニペットをコンソールにコピー**** して貼り付けるか、[コンソール メッセージの例: 指定子を使用してログを[記録する] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]。  ログ内の情報を展開して、大きな違いを表示 `%o` します `%O` 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers.msft.png" alt-text="指定子を使用して値をログに記録し、変換する" lightbox="../media/console-log-specifiers.msft.png":::
         指定子を使用して値をログに記録し、変換する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers-expanded.msft.png" alt-text="結果を展開すると、%O の差が表示されます。および %o指定子 - 本文は、展開可能な DOM ノードとして、または Web ページ本文上のすべての JavaScript プロパティの完全なリストとして表示されます。" lightbox="../media/console-log-specifiers-expanded.msft.png":::
        結果を展開すると、指定子と指定子の違いが表示されます。本文は展開可能な DOM ノードとして、または Web ページ本文のすべての JavaScript プロパティの完全なリストとして `%O` `%o` 表示されます。  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="group-log-messages"></a>グループ ログ メッセージ

多くの情報をログに記録する場合は、and メソッドを使用して、コンソールにログ メッセージを展開可能なグループと折りたたみ可能なグループ `group` `groupCollapsed` として表示 **できます**。  データを理解しやすくするために、グループを入れ子にし、名前を付けすることができます。  

```javascript
console.group("Passengers: Heart of Gold");
console.log('Zaphod');
console.log('Trillian');
console.log('Ford');
console.log('Arthur');
console.log('Marvin');
console.groupCollapsed("Hidden");
console.log('(Frankie & Benjy)');
console.groupEnd("Hidden");
console.groupEnd("Passengers: Heart of Gold");

let technologies = {
  "Standards": ["HTML", "CSS", "SVG", "ECMAScript"],
  "Others": ["jQuery", "Markdown", "Textile", "Sass", "Pug"]
}
for (tech in technologies) {
  console.groupCollapsed(tech);
  technologies[tech].forEach(t => console.log(t));
  console.groupEnd(tech);
}
```  

また、2 番目の例では、グループ名を必要に応じて生成できます。  結果を表示するには、前のコード スニペットをコンソールにコピー**** して貼り付けるか、[コンソール メッセージの例: ログのグループ化[] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]。  各セクションを展開および折りたたみできます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups.msft.png" alt-text="多数の値をグループとしてログに記録する" lightbox="../media/console-log-groups.msft.png":::
         多数の値をグループとしてログに記録する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups-expanded.msft.png" alt-text="各グループは展開および折りたたみ可能" lightbox="../media/console-log-groups-expanded.msft.png":::
        各グループは展開および折りたたみ可能  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="display-complex-data-as-tables"></a>複雑なデータをテーブルとして表示する  

このメソッドは、折りたたみ可能で展開可能なオブジェクトとしてではなく、異なるヘッダーを使用して並べ替えるテーブルとして複雑な `console.table()` データをログに記録します。  並べ替えテーブルを使用すると、ユーザーが情報を簡単に確認できます。  例で表示するには、[コンソール メッセージの例: テーブルの [使用] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]。

```javascript
let technologies = {
  "Standards": ["HTML", "CSS", "SVG", "ECMAScript"],
  "Others": ["jQuery", "Markdown", "Textile", "Sass", "Pug"]
}
// log technologies as an object
console.log(technologies);
// display technologies as a table
console.table(technologies);

// get the dimensions of the webpage body
let bodyDimensions = document.body.getBoundingClientRect();
// display dimensions as an object
console.log(bodyDimensions);
// display dimensions as a table
console.table(bodyDimensions);
```  

:::image type="complex" source="../media/console-log-table.msft.png" alt-text="console.table を使用してデータを表示し、読みやすくする" lightbox="../media/console-log-table.msft.png":::
   データを表示 `console.table` して読みやすくする
:::image-end:::  

の出力 `console.table` は、コンソールに表示される場合だけでなく、テーブル形式 **を持ちます**。    たとえば、表形式データをサポートする Excel、Word、または他の製品にテーブルをコピーして貼り付ける場合、構造はそのまま残ります。  

<!--  The output of `console.table` has a table format not only when it displays in the **Console**.  For example, copy and paste a table in Excel, Word, or any other products that support tabular data.  -->  

データに名前付きパラメーターがある場合、メソッドでは、2 番目のパラメーターとして表示する各プロパティの列 `console.table()` `Array` を指定することもできます。  次の例では、読み取り可能な列の配列を指定する方法を示します。  

```javascript
// get all the h1, p and script elements 
let contentElements = document.querySelectorAll(':is(h1,p,script)');
// display the elements as an unfiltered table 
console.table(contentElements)
// display only relevant columns 
console.table(contentElements,['nodeName', 'innerText', 'offsetHeight'])
```  

:::image type="complex" source="../media/console-log-table-filtered.msft.png" alt-text="console.table が表示する情報をフィルター処理し、2 番目のパラメーターとして表示するプロパティの配列を提供する" lightbox="../media/console-log-table-filtered.msft.png":::
   2 番目の `console.table` パラメーターとして表示するプロパティの配列を表示および提供するフィルター情報  
:::image-end:::  

ログ メソッドは使いやすいため、ログ メソッドを主な手段として使用して Web ページをデバッグする場合があります。  要求の結果を検討 `console.log()` します。  ライブ製品は、デバッグに使用されたログを使用してはならない。  内部情報がユーザーに表示される場合があります。  コンソールで作成されるノイズ **は** 圧倒的です。  ブレークポイント デバッグまたは [Live 式][DevtoolsJavascriptBreakpoints] を [使用すると][DevtoolsConsoleLiveExpressions]、ワークフローの効果が高く、より良い結果が得られます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "Filter Console メッセージ |Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "Live 式を使用して JavaScript の変更を監視|Microsoft Docs"  

[DevtoolsJavascriptBreakpoints]: ../javascript/breakpoints.md "DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-examples.html "コンソール メッセージの例: ログ、情報、エラー、警告の|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-types.html "コンソール メッセージの例: さまざまな種類のログ|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-groups.html "コンソール メッセージの例: ログのグループ化|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-specifiers.html "コンソール メッセージの例: 指定子を使用したログ|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-table.html "コンソール メッセージの例: テーブル の使用|GitHub"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタック トレース |Wikipedia"  
