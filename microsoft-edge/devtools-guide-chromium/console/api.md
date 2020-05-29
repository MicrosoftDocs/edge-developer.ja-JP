---
title: 本体の API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e54bae7c7c61584ccd39568f1bb54312cc2082c0
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601755"
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





# <span data-ttu-id="b311a-103">本体の API リファレンス</span><span class="sxs-lookup"><span data-stu-id="b311a-103">Console API Reference</span></span>   

  

<span data-ttu-id="b311a-104">コンソール API メソッドを使って、JavaScript からコンソールにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b311a-104">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="b311a-105">トピックの対話的な紹介については、「[コンソールにメッセージを記録][DevtoolsConsoleLog]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b311a-105">See [Get Started With Logging Messages To The Console][DevtoolsConsoleLog] for an interactive introduction to the topic.</span></span>  <span data-ttu-id="b311a-106">便宜上[Console Utilities API Reference] [DevtoolConsoleUtilities] 、 `debug()` または `monitorEvents()` 本体だけで利用できる便利なメソッドを探している場合は、「コンソールユーティリティ API リファレンス」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b311a-106">See [Console Utilities API Reference] [DevtoolConsoleUtilities] if you are looking for the convenience methods like `debug()` or `monitorEvents()` which are only available from the Console.</span></span>  

## <span data-ttu-id="b311a-107">assert</span><span class="sxs-lookup"><span data-stu-id="b311a-107">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="b311a-108">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-108">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="b311a-109">評価されたときに、本体に[エラー](#error)を書き込み `expression` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="b311a-109">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

> ##### <span data-ttu-id="b311a-110">図 1</span><span class="sxs-lookup"><span data-stu-id="b311a-110">Figure 1</span></span>  
> <span data-ttu-id="b311a-111">この例の結果 `console.assert()`</span><span class="sxs-lookup"><span data-stu-id="b311a-111">The result of the `console.assert()` example</span></span>  
> ![本体の assert () の結果][ImageAssert]  

## <span data-ttu-id="b311a-113">clear</span><span class="sxs-lookup"><span data-stu-id="b311a-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="b311a-114">本体をクリアします。</span><span class="sxs-lookup"><span data-stu-id="b311a-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="b311a-115">[[ログの保持][DevtoolsConsoleReferenceLevel]] が有効になっている場合、 [clear](#clear)メソッドは無効になります。</span><span class="sxs-lookup"><span data-stu-id="b311a-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

<span data-ttu-id="b311a-116">関連項目:[本体をクリアする][DevtoolsConsoleReferenceClear]</span><span class="sxs-lookup"><span data-stu-id="b311a-116">See also: [Clear the Console][DevtoolsConsoleReferenceClear]</span></span>  

## <span data-ttu-id="b311a-117">枚数</span><span class="sxs-lookup"><span data-stu-id="b311a-117">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="b311a-118">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-118">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-119">[Count](#count)メソッドが同じ行で呼び出され、同じ行にある回数を書き込み `label` ます。</span><span class="sxs-lookup"><span data-stu-id="b311a-119">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="b311a-120">[Countreset](#countreset)メソッドを使用して、カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b311a-120">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

> ##### <span data-ttu-id="b311a-121">図 2</span><span class="sxs-lookup"><span data-stu-id="b311a-121">Figure 2</span></span>  
> <span data-ttu-id="b311a-122">この例の結果 `console.count()`</span><span class="sxs-lookup"><span data-stu-id="b311a-122">The result of the `console.count()` example</span></span>  
> ![Console count () の例の結果][ImageCount]  

## <span data-ttu-id="b311a-124">countReset</span><span class="sxs-lookup"><span data-stu-id="b311a-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="b311a-125">カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b311a-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

## <span data-ttu-id="b311a-126">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b311a-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="b311a-127">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-128">[Log](#log)メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="b311a-128">Identical to the [log](#log) method.</span></span>  

```javascript
console.debug('debug');  
```  

> ##### <span data-ttu-id="b311a-129">図 3</span><span class="sxs-lookup"><span data-stu-id="b311a-129">Figure 3</span></span>  
> <span data-ttu-id="b311a-130">この例の結果 `console.debug()`</span><span class="sxs-lookup"><span data-stu-id="b311a-130">The result of the `console.debug()` example</span></span>  
> ![Xbox の debug () の例][ImageDebug]  

## <span data-ttu-id="b311a-132">dir</span><span class="sxs-lookup"><span data-stu-id="b311a-132">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="b311a-133">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-133">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-134">指定したオブジェクトの JSON 表現を出力します。</span><span class="sxs-lookup"><span data-stu-id="b311a-134">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

> ##### <span data-ttu-id="b311a-135">図 4</span><span class="sxs-lookup"><span data-stu-id="b311a-135">Figure 4</span></span>  
> <span data-ttu-id="b311a-136">この例の結果 `console.dir()`</span><span class="sxs-lookup"><span data-stu-id="b311a-136">The result of the `console.dir()` example</span></span>  
> ![Console () の例の結果][ImageDir]  

## <span data-ttu-id="b311a-138">dirxml</span><span class="sxs-lookup"><span data-stu-id="b311a-138">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="b311a-139">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-139">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-140">の子の XML 表現を出力 `node` します。</span><span class="sxs-lookup"><span data-stu-id="b311a-140">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

> ##### <span data-ttu-id="b311a-141">図 5</span><span class="sxs-lookup"><span data-stu-id="b311a-141">Figure 5</span></span>  
> <span data-ttu-id="b311a-142">この例の結果 `console.dirxml()`</span><span class="sxs-lookup"><span data-stu-id="b311a-142">The result of the `console.dirxml()` example</span></span>  
> ![コンソールの dirxml () 例の結果][ImageDirXml]  

## <span data-ttu-id="b311a-144">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="b311a-144">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="b311a-145">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-145">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="b311a-146">`object`コンソールにを出力し、エラーとして書式設定し、スタックトレースを含めます。</span><span class="sxs-lookup"><span data-stu-id="b311a-146">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

> ##### <span data-ttu-id="b311a-147">図 6</span><span class="sxs-lookup"><span data-stu-id="b311a-147">Figure 6</span></span>  
> <span data-ttu-id="b311a-148">この例の結果 `console.error()`</span><span class="sxs-lookup"><span data-stu-id="b311a-148">The result of the `console.error()` example</span></span>  
> ![本体の結果。エラー () の例][ImageError]  

## <span data-ttu-id="b311a-150">グループ</span><span class="sxs-lookup"><span data-stu-id="b311a-150">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="b311a-151">[Groupend](#groupend)メソッドが使われるまで、メッセージを視覚的にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="b311a-151">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="b311a-152">グループが最初にコンソールにログインしたときに、グループを折りたたむには、 [Groupcollapsed](#groupcollapsed)れたメソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="b311a-152">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

> ##### <span data-ttu-id="b311a-153">図 7</span><span class="sxs-lookup"><span data-stu-id="b311a-153">Figure 7</span></span>  
> <span data-ttu-id="b311a-154">この例の結果 `console.group()`</span><span class="sxs-lookup"><span data-stu-id="b311a-154">The result of the `console.group()` example</span></span>  
> ![Console の結果。 group () の例][ImageGroup]  

## <span data-ttu-id="b311a-156">groupCollapsed れている</span><span class="sxs-lookup"><span data-stu-id="b311a-156">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="b311a-157">[Log](#log)メソッドと同じですが、グループをコンソールに記録したときに最初に折りたたまれている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="b311a-157">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

## <span data-ttu-id="b311a-158">groupEnd</span><span class="sxs-lookup"><span data-stu-id="b311a-158">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="b311a-159">視覚的にメッセージをグループ化することを停止します。</span><span class="sxs-lookup"><span data-stu-id="b311a-159">Stops visually grouping messages.</span></span>  <span data-ttu-id="b311a-160">[グループ](#group)のメソッドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b311a-160">See the [group](#group) method.</span></span>  

## <span data-ttu-id="b311a-161">情報</span><span class="sxs-lookup"><span data-stu-id="b311a-161">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="b311a-162">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-163">[Log](#log)メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="b311a-163">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

> ##### <span data-ttu-id="b311a-164">図 8</span><span class="sxs-lookup"><span data-stu-id="b311a-164">Figure 8</span></span>  
> <span data-ttu-id="b311a-165">この例の結果 `console.info()`</span><span class="sxs-lookup"><span data-stu-id="b311a-165">The result of the `console.info()` example</span></span>  
> ![Console.info () 例の結果][ImageInfo]  

## <span data-ttu-id="b311a-167">出力</span><span class="sxs-lookup"><span data-stu-id="b311a-167">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="b311a-168">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-168">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-169">コンソールにメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="b311a-169">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

> ##### <span data-ttu-id="b311a-170">図 9</span><span class="sxs-lookup"><span data-stu-id="b311a-170">Figure 9</span></span>  
> <span data-ttu-id="b311a-171">この例の結果 `console.log()`</span><span class="sxs-lookup"><span data-stu-id="b311a-171">The result of the `console.log()` example</span></span>  
> ![Console .log () の例の結果][ImageLog]  

## <span data-ttu-id="b311a-173">'95'5c</span><span class="sxs-lookup"><span data-stu-id="b311a-173">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="b311a-174">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-174">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-175">オブジェクトの配列をテーブルとしてログに記録します。</span><span class="sxs-lookup"><span data-stu-id="b311a-175">Logs an array of objects as a table.</span></span>  

```javascript
console.table([
    {
        first: 'René',
        last: 'Magritte',
    },
    {
        first: 'Chaim',
        last: 'Soutine',
        birthday: '18930113',
    },
    {
        first: 'Henri',
        last: 'Matisse',
    }
]);
```  

> ##### <span data-ttu-id="b311a-176">図 10</span><span class="sxs-lookup"><span data-stu-id="b311a-176">Figure 10</span></span>  
> <span data-ttu-id="b311a-177">この例の結果 `console.table()`</span><span class="sxs-lookup"><span data-stu-id="b311a-177">The result of the `console.table()` example</span></span>  
> ![本体の結果 () 例][ImageTable]  

## <span data-ttu-id="b311a-179">time</span><span class="sxs-lookup"><span data-stu-id="b311a-179">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="b311a-180">新しいタイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="b311a-180">Starts a new timer.</span></span>  <span data-ttu-id="b311a-181">[Timeend](#timeend)メソッドを使ってタイマーを停止し、経過時間を本体に出力します。</span><span class="sxs-lookup"><span data-stu-id="b311a-181">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

> ##### <span data-ttu-id="b311a-182">図 11</span><span class="sxs-lookup"><span data-stu-id="b311a-182">Figure 11</span></span>  
> <span data-ttu-id="b311a-183">この例の結果 `console.time()`</span><span class="sxs-lookup"><span data-stu-id="b311a-183">The result of the `console.time()` example</span></span>  
> ![Console の結果。 time () の例][ImageTime]  

## <span data-ttu-id="b311a-185">timeEnd</span><span class="sxs-lookup"><span data-stu-id="b311a-185">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="b311a-186">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-187">タイマーを停止します。</span><span class="sxs-lookup"><span data-stu-id="b311a-187">Stops a timer.</span></span>  <span data-ttu-id="b311a-188">[Time](#time)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b311a-188">See the [time](#time) method.</span></span>  

## <span data-ttu-id="b311a-189">trace</span><span class="sxs-lookup"><span data-stu-id="b311a-189">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="b311a-190">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-190">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="b311a-191">スタックトレースを本体に出力します。</span><span class="sxs-lookup"><span data-stu-id="b311a-191">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

> ##### <span data-ttu-id="b311a-192">図 12</span><span class="sxs-lookup"><span data-stu-id="b311a-192">Figure 12</span></span>  
> <span data-ttu-id="b311a-193">この例の結果 `console.trace()`</span><span class="sxs-lookup"><span data-stu-id="b311a-193">The result of the `console.trace()` example</span></span>  
> ![本体のトレースの結果 () 例][ImageTrace]  

## <span data-ttu-id="b311a-195">warn</span><span class="sxs-lookup"><span data-stu-id="b311a-195">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="b311a-196">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="b311a-196">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="b311a-197">コンソールに警告を出力します。</span><span class="sxs-lookup"><span data-stu-id="b311a-197">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

> ##### <span data-ttu-id="b311a-198">図 13</span><span class="sxs-lookup"><span data-stu-id="b311a-198">Figure 13</span></span>  
> <span data-ttu-id="b311a-199">この例の結果 `console.warn()`</span><span class="sxs-lookup"><span data-stu-id="b311a-199">The result of the `console.warn()` example</span></span>  
> ![本体の結果。 warn () の例][ImageWarn]  

   

  

<!-- image links -->  

[ImageAssert]: /microsoft-edge/devtools-guide-chromium/media/console-demo-assert-button.msft.png "図 1: assert () の例"  
[ImageCount]: /microsoft-edge/devtools-guide-chromium/media/console-demo-count-button.msft.png "図 2: console () の例の結果"  
[ImageDebug]: /microsoft-edge/devtools-guide-chromium/media/console-demo-debug-button.msft.png "図 3: xbox の debug () の例"  
[ImageDir]: /microsoft-edge/devtools-guide-chromium/media/console-demo-dir-button.msft.png "図 4: console () の例"  
[ImageDirXml]: /microsoft-edge/devtools-guide-chromium/media/console-demo-dirxml-button.msft.png "図 5: この例では、コンソールの dirxml () の結果"  
[ImageError]: /microsoft-edge/devtools-guide-chromium/media/console-demo-error-button.msft.png "図 6: 本体の結果。エラー () の例"  
[ImageGroup]: /microsoft-edge/devtools-guide-chromium/media/console-demo-group-button.msft.png "図 7: "group () の実行結果" の例"  
[ImageInfo]: /microsoft-edge/devtools-guide-chromium/media/console-demo-info-button.msft.png "図 8: console.info () の例の結果"  
[ImageLog]: /microsoft-edge/devtools-guide-chromium/media/console-demo-log-button.msft.png "図 9: console () の例の結果"  
[ImageTable]: /microsoft-edge/devtools-guide-chromium/media/console-demo-table-button.msft.png "図 10: console () の結果"  
[ImageTime]: /microsoft-edge/devtools-guide-chromium/media/console-demo-time-button.msft.png "図 11: time () の例"  
[ImageTrace]: /microsoft-edge/devtools-guide-chromium/media/console-demo-trace-button.msft.png "図 12: trace () の例"  
[ImageWarn]: /microsoft-edge/devtools-guide-chromium/media/console-demo-warn-button.msft.png "図 13: console の結果 () の例"  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのメッセージの記録を開始する"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソールユーティリティ API リファレンス"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "本体本体のリファレンスをクリアする"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "ページの読み込み中にメッセージを保持-本体のリファレンス"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログレベルによるフィルター-コンソールリファレンス"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

> [!NOTE]
> <span data-ttu-id="b311a-220">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b311a-220">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b311a-221">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/api)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="b311a-221">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b311a-223">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b311a-223">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
