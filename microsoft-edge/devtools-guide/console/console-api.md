---
description: コンソール API を使ってプログラムでコードのデバッグとプロファイルを行う
title: DevTools-本体と本体の API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、コンソール api
ms.custom: seodec18
ms.openlocfilehash: d722934c3694c3c23e367141158ad45f6d03b175
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570529"
---
# <span data-ttu-id="a9191-104">コンソール API</span><span class="sxs-lookup"><span data-stu-id="a9191-104">Console API</span></span>

<span data-ttu-id="a9191-105">*CONSOLE API*は、グローバルオブジェクトを通じて Devtools 本体へのコマンドラインとプログラムによるアクセスを提供し `console` 、次のことを可能にします。</span><span class="sxs-lookup"><span data-stu-id="a9191-105">The *Console API* provides command-line and programmatic access to the  DevTools Console through the global `console` object, allowing you to:</span></span>

 - <span data-ttu-id="a9191-106">コードから[カスタムメッセージをログに記録](#logging-custom-messages)する</span><span class="sxs-lookup"><span data-stu-id="a9191-106">[Log custom messages](#logging-custom-messages) from you code</span></span>
 - <span data-ttu-id="a9191-107">[オブジェクトと要素を検査](#inspecting-objects-and-elements)して情報を記録する</span><span class="sxs-lookup"><span data-stu-id="a9191-107">[Inspect objects and elements](#inspecting-objects-and-elements) and log their information</span></span>
 - <span data-ttu-id="a9191-108">アサーション、タイマー、カウンターを設定して、[コードのテストと測定を行う](#testing-and-measuring)</span><span class="sxs-lookup"><span data-stu-id="a9191-108">[Test and measure your code](#testing-and-measuring) by setting assertions, timers and counters</span></span>
 - <span data-ttu-id="a9191-109">[ヒープのスナップショットを取得](#taking-heap-snapshots)して、実行しているコードのメモリ使用量を評価し、メモリリークを特定する</span><span class="sxs-lookup"><span data-stu-id="a9191-109">[Take snapshots of the heap](#taking-heap-snapshots) to assess the memory consumption of your running code and identify memory leaks</span></span>
 - <span data-ttu-id="a9191-110">[Callstacks をトレース](#tracing-callstacks)して、コードの呼び出し元を把握してください。</span><span class="sxs-lookup"><span data-stu-id="a9191-110">[Trace your callstacks](#tracing-callstacks) to understand where your code is being called from</span></span> 
 - <span data-ttu-id="a9191-111">[ログ出力を整理](#organizing-log-output)してデバッグを効率化する</span><span class="sxs-lookup"><span data-stu-id="a9191-111">[Organize your log output](#organizing-log-output) to streamline your debugging</span></span>

<span data-ttu-id="a9191-112">Microsoft Edge で現在サポートされているコマンドと書式設定パラメーターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9191-112">The following are the commands and formatting parameters currently supported by Microsoft Edge.</span></span> <span data-ttu-id="a9191-113">主要なブラウザーでも同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="a9191-113">They work similarly on major browsers.</span></span>

## <span data-ttu-id="a9191-114">カスタムメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="a9191-114">Logging custom messages</span></span>

<span data-ttu-id="a9191-115">コードでは、次のようなさまざまな種類のカスタムメッセージをコンソールに送信できます。</span><span class="sxs-lookup"><span data-stu-id="a9191-115">Your code can send several types of custom messages to the console, including:</span></span>

<span data-ttu-id="a9191-116">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="a9191-116">Message type</span></span>  | &nbsp;   |
:------------------- | :------ |
<span data-ttu-id="a9191-117">[**error ()**](https://developer.mozilla.org/docs/Web/API/Console/error)と[ **exception ()**](https://developer.mozilla.org/docs/Web/API/Console/error)</span><span class="sxs-lookup"><span data-stu-id="a9191-117">[**error()**](https://developer.mozilla.org/docs/Web/API/Console/error) and [**exception()**](https://developer.mozilla.org/docs/Web/API/Console/error)</span></span>| <span data-ttu-id="a9191-118">重大なエラーとエラー</span><span class="sxs-lookup"><span data-stu-id="a9191-118">Critical errors and failures</span></span>
[**<span data-ttu-id="a9191-119">warn ()</span><span class="sxs-lookup"><span data-stu-id="a9191-119">warn()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/warn) | <span data-ttu-id="a9191-120">考えられるエラーまたは予期しない動作</span><span class="sxs-lookup"><span data-stu-id="a9191-120">Possible errors or unexpected behavior</span></span> 
[**<span data-ttu-id="a9191-121">info ()</span><span class="sxs-lookup"><span data-stu-id="a9191-121">info()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/info) | <span data-ttu-id="a9191-122">役立つが、重要ではない情報</span><span class="sxs-lookup"><span data-stu-id="a9191-122">Useful, but non-critical information</span></span>
<span data-ttu-id="a9191-123">[**log ()**](https://developer.mozilla.org/docs/Web/API/Console/log)と[ **debug ()**](https://developer.mozilla.org/docs/Web/API/Console/log)</span><span class="sxs-lookup"><span data-stu-id="a9191-123">[**log()**](https://developer.mozilla.org/docs/Web/API/Console/log) and [**debug()**](https://developer.mozilla.org/docs/Web/API/Console/log)</span></span> | <span data-ttu-id="a9191-124">一般的なデバッグ (本体にシステム警告アイコンを生成しない)</span><span class="sxs-lookup"><span data-stu-id="a9191-124">General debugging (without generating a system alert icon in the console)</span></span>

   
<span data-ttu-id="a9191-125">これらは、Microsoft Edge から生成された他のメッセージと共に、コンソールパネルからグループ化してフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a9191-125">You can group and filter these along with the other messages generated from Microsoft Edge from the  Console panel.</span></span> <span data-ttu-id="a9191-126">すべてのカスタムメッセージメソッドには、string (message) パラメーターとオプションの書式置換パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9191-126">All custom message methods require a string (message) parameter and optional format substitution parameters.</span></span> <span data-ttu-id="a9191-127">Microsoft Edge では、次の書式設定オプションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9191-127">Microsoft Edge supports the following formatting options:</span></span>

<span data-ttu-id="a9191-128">Format パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9191-128">Format parameter</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="a9191-129">% b</span><span class="sxs-lookup"><span data-stu-id="a9191-129">%b</span></span>** | <span data-ttu-id="a9191-130">バイナリ</span><span class="sxs-lookup"><span data-stu-id="a9191-130">Binary</span></span>
**<span data-ttu-id="a9191-131">% c</span><span class="sxs-lookup"><span data-stu-id="a9191-131">%c</span></span>** | <span data-ttu-id="a9191-132">インライン CSS スタイル (以下の例を参照)</span><span class="sxs-lookup"><span data-stu-id="a9191-132">Inline CSS style (see example below)</span></span>
<span data-ttu-id="a9191-133">**% d**、 **% i**</span><span class="sxs-lookup"><span data-stu-id="a9191-133">**%d**, **%i**</span></span> | <span data-ttu-id="a9191-134">Integer</span><span class="sxs-lookup"><span data-stu-id="a9191-134">Integer</span></span> 
**<span data-ttu-id="a9191-135">% f</span><span class="sxs-lookup"><span data-stu-id="a9191-135">%f</span></span>** | <span data-ttu-id="a9191-136">Float</span><span class="sxs-lookup"><span data-stu-id="a9191-136">Float</span></span>  
**<span data-ttu-id="a9191-137">% s</span><span class="sxs-lookup"><span data-stu-id="a9191-137">%s</span></span>** | <span data-ttu-id="a9191-138">String</span><span class="sxs-lookup"><span data-stu-id="a9191-138">String</span></span> 
**<span data-ttu-id="a9191-139">% x</span><span class="sxs-lookup"><span data-stu-id="a9191-139">%x</span></span>** | <span data-ttu-id="a9191-140">16進数</span><span class="sxs-lookup"><span data-stu-id="a9191-140">Hexadecimal</span></span> 
**<span data-ttu-id="a9191-141">% e</span><span class="sxs-lookup"><span data-stu-id="a9191-141">%e</span></span>** | <span data-ttu-id="a9191-142">指数</span><span class="sxs-lookup"><span data-stu-id="a9191-142">Exponent</span></span> 

<span data-ttu-id="a9191-143">たとえば、次のようにして、ログメッセージに文字列と整数の変数を含めます。</span><span class="sxs-lookup"><span data-stu-id="a9191-143">For example, here's how you would include string and integer variables in your log message:</span></span>

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

<span data-ttu-id="a9191-144">次に、インライン CSS () を使用してログメッセージに緑の強調表示効果を追加する方法について説明し `%c` ます。</span><span class="sxs-lookup"><span data-stu-id="a9191-144">And here's how you might add a green highlight effect to a log message with inline CSS (`%c`):</span></span>

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![インラインスタイルを使用したコンソールログ](../media/console_api_css.png)

## <span data-ttu-id="a9191-146">オブジェクトと要素の検査</span><span class="sxs-lookup"><span data-stu-id="a9191-146">Inspecting objects and elements</span></span>

<span data-ttu-id="a9191-147">Inspectable オブジェクトは、展開可能なノードを含む折りたたまれたツリービューのコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9191-147">Inspectable objects appear in the console in a collapsed tree view with expandable nodes.</span></span> <span data-ttu-id="a9191-148">コンソールは、DOM ノード (div など) または JavaScript オブジェクト (イベントなど) を送信するかどうかを検出し、検出された型として自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="a9191-148">The console detects whether you are sending a DOM node (like a div) or a JavaScript object (like an event) and displays them as the detected type automatically.</span></span>

<span data-ttu-id="a9191-149">特定の出力を強制的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9191-149">You can also force a specific output:</span></span>

<span data-ttu-id="a9191-150">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-150">Command</span></span> | &nbsp;
:------------------- | :--- |
[**<span data-ttu-id="a9191-151">dir ()</span><span class="sxs-lookup"><span data-stu-id="a9191-151">dir()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dir) | <span data-ttu-id="a9191-152">Inspectable JavaScript オブジェクトとして表示されます</span><span class="sxs-lookup"><span data-stu-id="a9191-152">Displays as inspectable JavaScript object</span></span>
[**<span data-ttu-id="a9191-153">dirxml ()</span><span class="sxs-lookup"><span data-stu-id="a9191-153">dirxml()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | <span data-ttu-id="a9191-154">Inspectable DOM ノードとして表示されます</span><span class="sxs-lookup"><span data-stu-id="a9191-154">Displays as inspectable DOM node</span></span>

<span data-ttu-id="a9191-155">たとえば、本体を開いて、 `<div id='main'>` このページの要素の次の出力を比較してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9191-155">For example, try opening the console and compare the following outputs for the `<div id='main'>` element on this page:</span></span>

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!["Dir" と "dirxml" の出力の比較](../media/console_api_dir.png)

### <span data-ttu-id="a9191-157">[**要素**] パネルでの要素の選択</span><span class="sxs-lookup"><span data-stu-id="a9191-157">Selecting an element in the **Elements** panel</span></span>

<span data-ttu-id="a9191-158">すぐにレイアウトとスタイルのデバッグを行うために、ページの HTML ツリーコンテキスト内の要素をコンソールから直接選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a9191-158">You can select an element within the HTML tree context of the page directly from the console for immediate layout and style debugging.</span></span>

<span data-ttu-id="a9191-159">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-159">Command</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="a9191-160">select ()</span><span class="sxs-lookup"><span data-stu-id="a9191-160">select()</span></span>** | <span data-ttu-id="a9191-161">**要素**パネルに切り替えて、指定された要素にフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9191-161">Switches to the **Elements** panel and sets focus to the specified element.</span></span>

<span data-ttu-id="a9191-162">たとえば、このページで本体を開いて、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a9191-162">For example, if you open the console on this page and type:</span></span>

```javascript
console.select(document.querySelector("body"));
```

<span data-ttu-id="a9191-163">DevTools が [**要素**] パネルに切り替わり (まだ現在のものではない場合)、 [*HTML ツリービュー*](../elements.md#html-tree-view)でフォーカスを指定された要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="a9191-163">The DevTools will switch to the **Elements** panel (if its not already the current) and set focus in the [*HTML tree view*](../elements.md#html-tree-view) to the specified element.</span></span>

![Select メソッドの例](../media/console_api_select.png)

## <span data-ttu-id="a9191-165">テストと測定</span><span class="sxs-lookup"><span data-stu-id="a9191-165">Testing and measuring</span></span>

### <span data-ttu-id="a9191-166">コードをテストする</span><span class="sxs-lookup"><span data-stu-id="a9191-166">Testing your code</span></span>

<span data-ttu-id="a9191-167">単体テストのコードに本体 API テストアサーションを追加し、ブラウザーで実行されるコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="a9191-167">Add Console API test assertions to your code for unit testing and debugging your code as it runs in the browser.</span></span>

<span data-ttu-id="a9191-168">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-168">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-169">assert ()</span><span class="sxs-lookup"><span data-stu-id="a9191-169">assert()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/assert) | <span data-ttu-id="a9191-170">指定した式が*false*に評価された場合に本体のエラーメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="a9191-170">Logs a console error message if the provided expression evaluates to *false*.</span></span>

<span data-ttu-id="a9191-171">テスト可能なアサーションとして指定した論理式に加えて、オプションのメッセージと書式設定パラメーターを追加することもできます。これには、他の[カスタムコンソールメッセージ](#logging-custom-messages)と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9191-171">In addition to the logical expression you supply as the testable assertion, you can add an optional message and formatting parameters as you would use with other [custom console messages](#logging-custom-messages).</span></span> <span data-ttu-id="a9191-172">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="a9191-172">For example:</span></span>

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!["Assert" メソッドの例](../media/console_api_assert.png)

### <span data-ttu-id="a9191-174">コードの実行回数をカウントする</span><span class="sxs-lookup"><span data-stu-id="a9191-174">Counting executions in your code</span></span>

<span data-ttu-id="a9191-175">コードでカウンターを設定することで、周囲のコードが実行される回数を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="a9191-175">You can set counters in your code to keep track of how many times the surrounding code gets executed.</span></span> <span data-ttu-id="a9191-176">カウンターを設定すると、コードが期待どおりに実行されるようになり、パフォーマンスのボトルネックを診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9191-176">Setting counters can help ensure your code is running as expected and assist you in diagnosing performance bottlenecks.</span></span>

<span data-ttu-id="a9191-177">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-177">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-178">count ()</span><span class="sxs-lookup"><span data-stu-id="a9191-178">count()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/count) | <span data-ttu-id="a9191-179">指定されたラベルの*count ()* 回数が実行された回数をインクリメントしてログに記録します。</span><span class="sxs-lookup"><span data-stu-id="a9191-179">Increments and logs the number of times *count()* for the given label has been executed.</span></span>
[**<span data-ttu-id="a9191-180">countReset ()</span><span class="sxs-lookup"><span data-stu-id="a9191-180">countReset()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | <span data-ttu-id="a9191-181">指定されたカウンターラベルのカウントを0にリセットします。</span><span class="sxs-lookup"><span data-stu-id="a9191-181">Resets the count to zero for the given counter label.</span></span>

<span data-ttu-id="a9191-182">たとえば、次のような行をコンソールで実行します。</span><span class="sxs-lookup"><span data-stu-id="a9191-182">For example, executing the following lines in console:</span></span>

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 <span data-ttu-id="a9191-183">.</span><span class="sxs-lookup"><span data-stu-id="a9191-183">.</span></span> <span data-ttu-id="a9191-184">.</span><span class="sxs-lookup"><span data-stu-id="a9191-184">.</span></span> <span data-ttu-id="a9191-185">.</span><span class="sxs-lookup"><span data-stu-id="a9191-185">.</span></span> <span data-ttu-id="a9191-186">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a9191-186">will result in:</span></span>
> <span data-ttu-id="a9191-187">自分のカウンター: 1</span><span class="sxs-lookup"><span data-stu-id="a9191-187">My Counter: 1</span></span>

### <span data-ttu-id="a9191-188">コードのタイミングを調整する</span><span class="sxs-lookup"><span data-stu-id="a9191-188">Timing your code</span></span>

<span data-ttu-id="a9191-189">ラベル付きタイマーを使って、特定の操作を完了するまでの時間を測定するコードをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="a9191-189">Instrument your code with labeled timers to measure how long it takes to complete a given operation.</span></span>

<span data-ttu-id="a9191-190">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-190">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-191">時刻 ()</span><span class="sxs-lookup"><span data-stu-id="a9191-191">time()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/time) | <span data-ttu-id="a9191-192">指定されたラベルのタイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="a9191-192">Starts a timer with the given label.</span></span>
[**<span data-ttu-id="a9191-193">timeEnd ()</span><span class="sxs-lookup"><span data-stu-id="a9191-193">timeEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | <span data-ttu-id="a9191-194">指定されたラベルのタイマーを終了し、経過時間 (ミリ秒単位) を報告します。</span><span class="sxs-lookup"><span data-stu-id="a9191-194">Ends the timer with the given label and reports the time elapsed (in milliseconds).</span></span>
[**<span data-ttu-id="a9191-195">timeStamp ()</span><span class="sxs-lookup"><span data-stu-id="a9191-195">timeStamp()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | <span data-ttu-id="a9191-196">現在のシステム時刻 (ミリ秒単位) を報告します。</span><span class="sxs-lookup"><span data-stu-id="a9191-196">Reports the current system time (in milliseconds).</span></span>

<span data-ttu-id="a9191-197">たとえば、次の行をコンソールで実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9191-197">For example, try executing the following lines in console:</span></span>

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### <span data-ttu-id="a9191-198">ヒープスナップショットの取得</span><span class="sxs-lookup"><span data-stu-id="a9191-198">Taking heap snapshots</span></span>

<span data-ttu-id="a9191-199">ヒープのスナップショットを取得して、実行しているコードのメモリ使用量を評価し、メモリリークを特定します。</span><span class="sxs-lookup"><span data-stu-id="a9191-199">Take snapshots of the heap to assess the memory consumption of your running code and identify memory leaks.</span></span>

<span data-ttu-id="a9191-200">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-200">Command</span></span> | &nbsp;
:------------ | :-------------
**<span data-ttu-id="a9191-201">Heapsnapshot () の場合</span><span class="sxs-lookup"><span data-stu-id="a9191-201">takeHeapSnapshot()</span></span>** | <span data-ttu-id="a9191-202">現在の JavaScript ヒープと割り当てられているオブジェクトに関する詳細をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a9191-202">Captures details about the current JavaScript heap and its allocated objects.</span></span>

<span data-ttu-id="a9191-203">ヒープスナップショットを取得するためには、DevTools[メモリプロファイラー](../memory.md#toolbar)が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9191-203">The  DevTools [memory profiler](../memory.md#toolbar) must be running in order to take heap snapshots.</span></span> <span data-ttu-id="a9191-204">各スナップショットは、[**メモリ**](../memory.md)パネルのスナップショットの[*概要*](../memory.md#snapshot-summary)のタイルとして表示され、さらに検査できます。</span><span class="sxs-lookup"><span data-stu-id="a9191-204">Each snapshot will appear as a tile in the [*Snapshot summary*](../memory.md#snapshot-summary) of the [**Memory**](../memory.md) panel for further inspection.</span></span>

## <span data-ttu-id="a9191-205">トレース callstacks</span><span class="sxs-lookup"><span data-stu-id="a9191-205">Tracing callstacks</span></span>

<span data-ttu-id="a9191-206">コードの呼び出し元、実行されているコード、実行にかかる時間を理解することは、遅く、または予期しない動作を分析するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9191-206">Understanding where your code is being called from, what code is running, and how long that execution takes can be useful in analyzing slowness or unexpected behavior.</span></span> <span data-ttu-id="a9191-207">スタックトレースには、コードから到達するために実行された実行パスが、トレース要求からパスを上向きに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9191-207">A stack trace shows you the execution path your code took to reach it, from the trace request upward through the path.</span></span> 

<span data-ttu-id="a9191-208">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-208">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-209">trace ()</span><span class="sxs-lookup"><span data-stu-id="a9191-209">trace()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/trace) | <span data-ttu-id="a9191-210">現在のスクリプト実行呼び出し履歴のトレースを出力します。</span><span class="sxs-lookup"><span data-stu-id="a9191-210">Outputs a trace of the current script execution callstack.</span></span>

<span data-ttu-id="a9191-211">たとえば、次のコードをコンソールで実行します。</span><span class="sxs-lookup"><span data-stu-id="a9191-211">For example, running the following code in the console:</span></span>

```javascript
function a(){
  c();
}
function b(){
  c();
}
function c(){
  console.trace()
}
function d(){
  b();
}

a();
d();
```

<span data-ttu-id="a9191-212">.</span><span class="sxs-lookup"><span data-stu-id="a9191-212">.</span></span> <span data-ttu-id="a9191-213">.</span><span class="sxs-lookup"><span data-stu-id="a9191-213">.</span></span> <span data-ttu-id="a9191-214">.</span><span class="sxs-lookup"><span data-stu-id="a9191-214">.</span></span> <span data-ttu-id="a9191-215">次のスタックトレースが出力されます。</span><span class="sxs-lookup"><span data-stu-id="a9191-215">will output the following stack traces:</span></span>
> <span data-ttu-id="a9191-216">console. trace () (eval コード: 8: 3) を、eval コード (eval コード:14: 1) で (eval コード: 2: 3)</span><span class="sxs-lookup"><span data-stu-id="a9191-216">console.trace() at c (eval code:8:3) at a (eval code:2:3) at eval code (eval code:14:1)</span></span>
> 
> <span data-ttu-id="a9191-217">console. trace () at c (eval コード: 8: 3) で、d (eval コード: 5: 3) を評価コード (eval コード:15: 1) で実行します。</span><span class="sxs-lookup"><span data-stu-id="a9191-217">console.trace() at c (eval code:8:3) at b (eval code:5:3) at d (eval code:11:3) at eval code (eval code:15:1)</span></span>

## <span data-ttu-id="a9191-218">ログ出力を整理する</span><span class="sxs-lookup"><span data-stu-id="a9191-218">Organizing log output</span></span>

<span data-ttu-id="a9191-219">単に以前のコンソール出力をすべてクリアするには、 *console. ()* (または) を使用 `CTRL + L` します。</span><span class="sxs-lookup"><span data-stu-id="a9191-219">To simply clear all previous console output, use *console.clear()* (or `CTRL + L`).</span></span> <span data-ttu-id="a9191-220">これにより、本体のコマンド履歴の backstack は消去されません (上下の方向キーを使って引き続きスキャンできます)。</span><span class="sxs-lookup"><span data-stu-id="a9191-220">This does not clear the backstack of your console command history (you can still traverse it with the up and down arrow keys).</span></span>

<span data-ttu-id="a9191-221">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-221">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-222">clear ()</span><span class="sxs-lookup"><span data-stu-id="a9191-222">clear()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/clear) | <span data-ttu-id="a9191-223">以前の本体の出力をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="a9191-223">Clears all previous console output.</span></span>

<span data-ttu-id="a9191-224">コードによって多くのコンソールメッセージが出力される場合は、次のコマンドを使用して、入れ子になったブロックに視覚的に整理できます。</span><span class="sxs-lookup"><span data-stu-id="a9191-224">If your code outputs a lot of console messages, you can visually organize them into nested blocks with the following commands:</span></span>

 <span data-ttu-id="a9191-225">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-225">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-226">group ()</span><span class="sxs-lookup"><span data-stu-id="a9191-226">group()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/group) | <span data-ttu-id="a9191-227">指定された (省略可能) ラベルを使って、コンソール出力に対して新しいレベルの入れ子を開始します。</span><span class="sxs-lookup"><span data-stu-id="a9191-227">Starts a new level of nesting for console output with the specified (optional) label.</span></span>
[**<span data-ttu-id="a9191-228">groupCollapsed れている ()</span><span class="sxs-lookup"><span data-stu-id="a9191-228">groupCollapsed()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | <span data-ttu-id="a9191-229">指定された (省略可能) ラベルを使って、コンソール出力に対して新しいレベルの入れ子を開始します。ただし、グループ化コントロールは既定で折りたたまれており、(矢印コントロールをクリックして) 子出力を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9191-229">Starts a new level of nesting for console output with the specified (optional) label, however the grouping control is collapsed by default and must be expanded (by clicking on the arrow control) to display the child output.</span></span>
[**<span data-ttu-id="a9191-230">groupEnd ()</span><span class="sxs-lookup"><span data-stu-id="a9191-230">groupEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | <span data-ttu-id="a9191-231">指定されたラベルのネストグループを終了します。</span><span class="sxs-lookup"><span data-stu-id="a9191-231">Ends the nesting group for the specified label.</span></span>

<span data-ttu-id="a9191-232">たとえば、コンソールで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a9191-232">For example, try entering the following commands in the console:</span></span>

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

<span data-ttu-id="a9191-233">.</span><span class="sxs-lookup"><span data-stu-id="a9191-233">.</span></span> <span data-ttu-id="a9191-234">.</span><span class="sxs-lookup"><span data-stu-id="a9191-234">.</span></span> <span data-ttu-id="a9191-235">.</span><span class="sxs-lookup"><span data-stu-id="a9191-235">.</span></span> <span data-ttu-id="a9191-236">次に、*グループ 1*と*グループの 1.1*コントロールを展開して、ログのコメントがどのようにネストされているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9191-236">and then expand the *Group 1* and *Group 1.1* controls to see how the log comments are nested:</span></span>

![コンソールでのメッセージのグループ化](../media/console_api_group.png)

<span data-ttu-id="a9191-238">JavaScript オブジェクトまたは配列を単純なリストではなく、表形式でビジュアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="a9191-238">Sometimes its easier to visualize a JavaScript object or array in tabular form, rather than a flat list.</span></span> <span data-ttu-id="a9191-239">そのためには、 *console ()* コマンドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9191-239">For that, you can use the *console.table()* command:</span></span>

<span data-ttu-id="a9191-240">コマンド</span><span class="sxs-lookup"><span data-stu-id="a9191-240">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="a9191-241">table ()</span><span class="sxs-lookup"><span data-stu-id="a9191-241">table()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/table) | <span data-ttu-id="a9191-242">指定した配列またはオブジェクトを、表形式でコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="a9191-242">Outputs the supplied array or object to the console in tabular form.</span></span>

<span data-ttu-id="a9191-243">たとえば、次のオブジェクト配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9191-243">For example, the following object array:</span></span>

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

<span data-ttu-id="a9191-244">.</span><span class="sxs-lookup"><span data-stu-id="a9191-244">.</span></span> <span data-ttu-id="a9191-245">.</span><span class="sxs-lookup"><span data-stu-id="a9191-245">.</span></span> <span data-ttu-id="a9191-246">.</span><span class="sxs-lookup"><span data-stu-id="a9191-246">.</span></span> <span data-ttu-id="a9191-247">コンソールに次の表のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9191-247">will render as this table in the console:</span></span>

![コンソールでオブジェクト配列を表として表示する](../media/console_api_table.png)
