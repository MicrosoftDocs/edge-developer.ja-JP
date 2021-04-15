---
description: メッセージをログに記録し、Microsoft Edge DevTools コンソールで JavaScript を実行する方法。
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
# <a name="log-messages-in-the-console-tool"></a><span data-ttu-id="91873-104">コンソール ツールでメッセージをログに記録する</span><span class="sxs-lookup"><span data-stu-id="91873-104">Log messages in the Console tool</span></span>  

<span data-ttu-id="91873-105">ブラウザーが開発者向けツールを提供し始めて以来、 **コンソールは好** みです。</span><span class="sxs-lookup"><span data-stu-id="91873-105">Ever since browsers started to offer developer tools, the **Console** is a favorite.</span></span>  <span data-ttu-id="91873-106">理由は簡単です。</span><span class="sxs-lookup"><span data-stu-id="91873-106">The reason is simple.</span></span>  

*   <span data-ttu-id="91873-107">ほとんどのプログラミング コースでは、何が起こるかについての洞察を得るために何らかの印刷コマンドを出力する方法を学ぶ。</span><span class="sxs-lookup"><span data-stu-id="91873-107">In most programming courses, you learn to output some kind of print command to gain insights about what happens.</span></span>  

<span data-ttu-id="91873-108">DevTools の前に、ブラウザーでデバッグする `alert()` ステートメント `document.write()` またはステートメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="91873-108">Before the DevTools, you were limited to an `alert()` or `document.write()` statement to debug in the browser.</span></span>  

<span data-ttu-id="91873-109">コンソールに情報を記録 **する場合は**、多くのメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="91873-109">If you want to log information in the **Console**, lots of methods are available to you.</span></span>  <span data-ttu-id="91873-110">API リファレンスで使用可能なすべてのメソッドを [確認します][DevtoolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="91873-110">Review all of available methods in the [API reference][DevtoolsConsoleApi].</span></span>  <span data-ttu-id="91873-111">次のコード スニペットは、最も重要なメソッドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="91873-111">The following code snippet lists the most important methods.</span></span>  

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

<span data-ttu-id="91873-112">前のコード スニペットをコンソールにコピーして貼り付ける **か、コンソール** メッセージの例 (ログ、情報、エラー、警告 [) に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]。</span><span class="sxs-lookup"><span data-stu-id="91873-112">Copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: log, info, error, and warn][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml].</span></span>  <span data-ttu-id="91873-113">**コンソール**で任意のメソッドを試してみると、メソッドとメソッドは同じことを行っているように見え、メソッドはメッセージの横にアイコンを表示し、メッセージのスタック トレースを検査する方法を示 `log()` `info()` `error()` `warn()` します[][WikiStackTrace]。</span><span class="sxs-lookup"><span data-stu-id="91873-113">When you try any method in the **Console**, the `log()` and `info()` methods seem to do the same thing, while the `error()` and `warn()` methods display an icon next to the message and a way to inspect the [stack trace][WikiStackTrace] of the message.</span></span>  

:::image type="complex" source="../media/console-log-examples.msft.png" alt-text="コンソールには、異なるログ API からのメッセージが表示されます。" lightbox="../media/console-log-examples.msft.png":::
   <span data-ttu-id="91873-115">コンソール **には、** 異なるログ API からのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91873-115">The **Console** displays the messages from different log APIs</span></span>  
:::image-end:::  

<span data-ttu-id="91873-116">ただし、コンソールの種類を使用してフィルター処理を行うことができますので、異なるログ タスクを使用して使用する方 `info()` `log()` [が良い方法です][DevtoolsConsoleConsoleFilters]。</span><span class="sxs-lookup"><span data-stu-id="91873-116">It is, however, still a good idea to use `info()` and `log()` for different log tasks as that allows you to [filter using type in the Console][DevtoolsConsoleConsoleFilters].</span></span>  

## <a name="different-types-of-logs"></a><span data-ttu-id="91873-117">さまざまな種類のログ</span><span class="sxs-lookup"><span data-stu-id="91873-117">Different types of logs</span></span>  

<span data-ttu-id="91873-118">ログ テキストの代わりに、有効な JavaScript または DOM 参照をコンソールに送信 **できます**。</span><span class="sxs-lookup"><span data-stu-id="91873-118">Instead of log text you may send any valid JavaScript or DOM references to the **Console**.</span></span>  <span data-ttu-id="91873-119">コンソール **は** エレガントで、送信する種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="91873-119">The **Console** is elegant and it determines the type that you send it.</span></span>  <span data-ttu-id="91873-120">次に、可能な限り最高の表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="91873-120">It then gives you the best possible representation.</span></span>  <span data-ttu-id="91873-121">コンソールに次のコード スニペットをコピー\*\*\*\* して貼り付けるか、結果を表示するには、[コンソール メッセージの例: ログの種類][に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]。</span><span class="sxs-lookup"><span data-stu-id="91873-121">Copy and paste the following code snippet in the **Console** or to display the results, navigate to [Console messages examples: logging different types][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml].</span></span>  

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

<span data-ttu-id="91873-122">各結果は異なる方法で表示されます。</span><span class="sxs-lookup"><span data-stu-id="91873-122">Each result is displayed in a different way.</span></span>  <span data-ttu-id="91873-123">三角形を使用して情報を切り替え、各情報を詳細に分析します。</span><span class="sxs-lookup"><span data-stu-id="91873-123">Use the triangles to toggle the information and analyze each one in more detail.</span></span>  <span data-ttu-id="91873-124">変数の中かっこの文字は、値のみを取得するが、発生した場所がわかりませんが、ログ メッセージの多くを避けるための便利な小さな `{}` `x` トリックです。</span><span class="sxs-lookup"><span data-stu-id="91873-124">The curly brace characters `{}` around the `x` variable are a nice little trick to avoid lots of log messages where you only get a value but you don't know where it originated.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types.msft.png" alt-text="コンソールでさまざまな種類の変数をログに記録する" lightbox="../media/console-log-types.msft.png":::
         <span data-ttu-id="91873-126">コンソールでさまざまな種類の変数をログに記録 **する**</span><span class="sxs-lookup"><span data-stu-id="91873-126">Log variables of different types in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-types-expanded.msft.png" alt-text="拡張された追加情報を使用して、コンソール内の異なる種類の変数をログに記録する" lightbox="../media/console-log-types-expanded.msft.png":::
         <span data-ttu-id="91873-128">拡張された追加情報を使用して、 **コンソール** 内の異なる種類の変数をログに記録する</span><span class="sxs-lookup"><span data-stu-id="91873-128">Log variables of different types in the **Console** with expanded extra information</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="format-and-convert-values-with-specifiers"></a><span data-ttu-id="91873-129">指定子を使用して値の書式設定と変換を行う</span><span class="sxs-lookup"><span data-stu-id="91873-129">Format and convert values with specifiers</span></span>

<span data-ttu-id="91873-130">すべてのログ メソッドの特別な機能は、ログ メッセージで指定子を使用できる機能です。</span><span class="sxs-lookup"><span data-stu-id="91873-130">A special feature of all the log methods is that you may use specifiers in your log message.</span></span>  <span data-ttu-id="91873-131">指定子はログ メッセージの一部であり、パーセント記号 \( \) 文字で始まるので、異なる形式で特定の値をログに記録し、それぞれを `%` 変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="91873-131">Specifiers are part of a log message and start with a percentage sign \(`%`\) character and allow you to log certain values in different formats and even convert each.</span></span>  

*   `%s` <span data-ttu-id="91873-132">ログを文字列として記録する</span><span class="sxs-lookup"><span data-stu-id="91873-132">logs as Strings</span></span>
*   `%i` <span data-ttu-id="91873-133">または `%d` ログを整数として記録する</span><span class="sxs-lookup"><span data-stu-id="91873-133">or `%d` logs as Integers</span></span>
*   `%f` <span data-ttu-id="91873-134">浮動小数点値としてのログ</span><span class="sxs-lookup"><span data-stu-id="91873-134">logs as a floating-point value</span></span>
*   `%o` <span data-ttu-id="91873-135">拡張可能な DOM 要素としてのログ</span><span class="sxs-lookup"><span data-stu-id="91873-135">logs as an expandable DOM element</span></span>
*   `%O` <span data-ttu-id="91873-136">展開可能な JavaScript オブジェクトとしてのログ</span><span class="sxs-lookup"><span data-stu-id="91873-136">logs as an expandable JavaScript object</span></span>
*   `%c` <span data-ttu-id="91873-137">CSS を使用してメッセージのスタイルを設定できます</span><span class="sxs-lookup"><span data-stu-id="91873-137">allows you to style you message with CSS</span></span>

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

<span data-ttu-id="91873-138">最初の例では、指定子の置換順序が文字列に続くパラメーターの順序を表示します。</span><span class="sxs-lookup"><span data-stu-id="91873-138">The first example displays that the order of replacement of specifiers is the parameter order following the string.</span></span>  <span data-ttu-id="91873-139">結果を表示するには、前のコード スニペットをコンソールにコピー\*\*\*\* して貼り付けるか、[コンソール メッセージの例: 指定子を使用してログを[記録する] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]。</span><span class="sxs-lookup"><span data-stu-id="91873-139">To display the results, copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: Logging with specifiers][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml].</span></span>  <span data-ttu-id="91873-140">ログ内の情報を展開して、大きな違いを表示 `%o` します `%O` 。</span><span class="sxs-lookup"><span data-stu-id="91873-140">Expand the information in the log to display the huge difference between `%o` and `%O`.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers.msft.png" alt-text="指定子を使用して値をログに記録し、変換する" lightbox="../media/console-log-specifiers.msft.png":::
         <span data-ttu-id="91873-142">指定子を使用して値をログに記録し、変換する</span><span class="sxs-lookup"><span data-stu-id="91873-142">Use specifiers to log and convert values</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-specifiers-expanded.msft.png" alt-text="結果を展開すると、%O の差が表示されます。および %o指定子 - 本文は、展開可能な DOM ノードとして、または Web ページ本文上のすべての JavaScript プロパティの完全なリストとして表示されます。" lightbox="../media/console-log-specifiers-expanded.msft.png":::
        <span data-ttu-id="91873-144">結果を展開すると、指定子と指定子の違いが表示されます。本文は展開可能な DOM ノードとして、または Web ページ本文のすべての JavaScript プロパティの完全なリストとして `%O` `%o` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="91873-144">Expand the results displays the difference between the `%O` and `%o` specifier - the body is either displayed as an expandable DOM node or as a full list of all JavaScript properties on the webpage body</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="group-log-messages"></a><span data-ttu-id="91873-145">グループ ログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="91873-145">Group log messages</span></span>

<span data-ttu-id="91873-146">多くの情報をログに記録する場合は、and メソッドを使用して、コンソールにログ メッセージを展開可能なグループと折りたたみ可能なグループ `group` `groupCollapsed` として表示 **できます**。</span><span class="sxs-lookup"><span data-stu-id="91873-146">If you log much information, you may use the `group` and `groupCollapsed` methods to display log messages as expandable and collapsible groups in the **Console**.</span></span>  <span data-ttu-id="91873-147">データを理解しやすくするために、グループを入れ子にし、名前を付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="91873-147">Groups may be nested and named to make the data much easier to understand.</span></span>  

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

<span data-ttu-id="91873-148">また、2 番目の例では、グループ名を必要に応じて生成できます。</span><span class="sxs-lookup"><span data-stu-id="91873-148">Also in the second example, the group names may be optionally generated.</span></span>  <span data-ttu-id="91873-149">結果を表示するには、前のコード スニペットをコンソールにコピー\*\*\*\* して貼り付けるか、[コンソール メッセージの例: ログのグループ化[] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]。</span><span class="sxs-lookup"><span data-stu-id="91873-149">To display the results, copy and paste the previous code snippet in the **Console** or navigate to [Console messages examples: grouping logs][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml].</span></span>  <span data-ttu-id="91873-150">各セクションを展開および折りたたみできます。</span><span class="sxs-lookup"><span data-stu-id="91873-150">You may expand and collapse each of the sections.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups.msft.png" alt-text="多数の値をグループとしてログに記録する" lightbox="../media/console-log-groups.msft.png":::
         <span data-ttu-id="91873-152">多数の値をグループとしてログに記録する</span><span class="sxs-lookup"><span data-stu-id="91873-152">Log lots of values as groups</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-log-groups-expanded.msft.png" alt-text="各グループは展開および折りたたみ可能" lightbox="../media/console-log-groups-expanded.msft.png":::
        <span data-ttu-id="91873-154">各グループは展開および折りたたみ可能</span><span class="sxs-lookup"><span data-stu-id="91873-154">Each group may be expanded and collapsed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="display-complex-data-as-tables"></a><span data-ttu-id="91873-155">複雑なデータをテーブルとして表示する</span><span class="sxs-lookup"><span data-stu-id="91873-155">Display complex data as tables</span></span>  

<span data-ttu-id="91873-156">このメソッドは、折りたたみ可能で展開可能なオブジェクトとしてではなく、異なるヘッダーを使用して並べ替えるテーブルとして複雑な `console.table()` データをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="91873-156">The `console.table()` method logs complex data not as a collapsible and expandable object, but as a table that you may sort using different headers.</span></span>  <span data-ttu-id="91873-157">並べ替えテーブルを使用すると、ユーザーが情報を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="91873-157">A sorted table makes it much easier for people to review the information.</span></span>  <span data-ttu-id="91873-158">例で表示するには、[コンソール メッセージの例: テーブルの [使用] に移動します][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]。</span><span class="sxs-lookup"><span data-stu-id="91873-158">To display it in an example, navigate to [Console messages examples: Using table][GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml].</span></span>

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
   <span data-ttu-id="91873-160">データを表示 `console.table` して読みやすくする</span><span class="sxs-lookup"><span data-stu-id="91873-160">Display data with `console.table` to make it much easier to read</span></span>
:::image-end:::  

<span data-ttu-id="91873-161">の出力 `console.table` は、コンソールに表示される場合だけでなく、テーブル形式 **を持ちます**。</span><span class="sxs-lookup"><span data-stu-id="91873-161">The output of `console.table` has a table format not only when it displays in the **Console**.</span></span>    <span data-ttu-id="91873-162">たとえば、テーブルをコピーして Excel、Word、または表形式データをサポートする他の製品に貼り付ける場合、構造はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="91873-162">For example, if you copy and paste a table into Excel, Word, or any other product that supports tabular data, the structure remains intact.</span></span>  

<!--  The output of `console.table` has a table format not only when it displays in the **Console**.  For example, copy and paste a table in Excel, Word, or any other products that support tabular data.  -->  

<span data-ttu-id="91873-163">データに名前付きパラメーターがある場合、メソッドでは、2 番目のパラメーターとして表示する各プロパティの列 `console.table()` `Array` を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="91873-163">If the data has named parameters, the `console.table()` method also allows you to specify an `Array` of columns for each property to display as a second parameter.</span></span>  <span data-ttu-id="91873-164">次の例では、読み取り可能な列の配列を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="91873-164">The following example displays how to specify an array of columns that is more readable.</span></span>  

```javascript
// get all the h1, p and script elements 
let contentElements = document.querySelectorAll(':is(h1,p,script)');
// display the elements as an unfiltered table 
console.table(contentElements)
// display only relevant columns 
console.table(contentElements,['nodeName', 'innerText', 'offsetHeight'])
```  

:::image type="complex" source="../media/console-log-table-filtered.msft.png" alt-text="console.table が表示する情報をフィルター処理し、2 番目のパラメーターとして表示するプロパティの配列を提供する" lightbox="../media/console-log-table-filtered.msft.png":::
   <span data-ttu-id="91873-166">2 番目の `console.table` パラメーターとして表示するプロパティの配列を表示および提供するフィルター情報</span><span class="sxs-lookup"><span data-stu-id="91873-166">Filter information that `console.table` displays and provide an array of properties to display as a second parameter</span></span>  
:::image-end:::  

<span data-ttu-id="91873-167">ログ メソッドは使いやすいため、ログ メソッドを主な手段として使用して Web ページをデバッグする場合があります。</span><span class="sxs-lookup"><span data-stu-id="91873-167">You may be tempted to use the log methods as your main means to debug webpages, because log methods are simple to use.</span></span>  <span data-ttu-id="91873-168">要求の結果を検討 `console.log()` します。</span><span class="sxs-lookup"><span data-stu-id="91873-168">Consider the result of any `console.log()` request.</span></span>  <span data-ttu-id="91873-169">ライブ製品は、デバッグに使用されたログを使用してはならない。</span><span class="sxs-lookup"><span data-stu-id="91873-169">Live products shouldn't use any log that was used to debug.</span></span>  <span data-ttu-id="91873-170">内部情報がユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="91873-170">It may reveal inside information to people.</span></span>  <span data-ttu-id="91873-171">コンソールで作成されるノイズ **は** 圧倒的です。</span><span class="sxs-lookup"><span data-stu-id="91873-171">And the noise created in the **Console** is overwhelming.</span></span>  <span data-ttu-id="91873-172">ブレークポイント デバッグまたは [Live 式][DevtoolsJavascriptBreakpoints] を [使用すると][DevtoolsConsoleLiveExpressions]、ワークフローの効果が高く、より良い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="91873-172">When you use [Breakpoint Debugging][DevtoolsJavascriptBreakpoints] or [Live Expressions][DevtoolsConsoleLiveExpressions], you may find that your workflows are more effective and you get better results.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="91873-173">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="91873-173">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevtoolsConsoleConsoleFilters]: ./console-filters.md "Filter Console メッセージ |Microsoft Docs"  
[DevtoolsConsoleLiveExpressions]: ./live-expressions.md "Live 式を使用して JavaScript の変更を監視|Microsoft Docs"  

[DevtoolsJavascriptBreakpoints]: ../javascript/breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingExamplesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-examples.html "コンソール メッセージの例: ログ、情報、エラー、警告の|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingTypesHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-types.html "コンソール メッセージの例: さまざまな種類のログ|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithGroupsHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-groups.html "コンソール メッセージの例: ログのグループ化|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithSpecifiersHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-specifiers.html "コンソール メッセージの例: 指定子を使用したログ|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleLoggingWithTableHtml]: https://microsoftedge.github.io/DevToolsSamples/console/logging-with-table.html "コンソール メッセージの例: テーブル の使用|GitHub"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタック トレース |Wikipedia"  
