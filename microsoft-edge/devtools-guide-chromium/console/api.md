---
description: コンソール API を使用して、コンソールにメッセージを書き込みます。
title: コンソール API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f38a7403cf11fbec5f5833fc0b1ed10207b436de
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398050"
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

# <a name="console-api-reference"></a><span data-ttu-id="4ff3e-104">コンソール API リファレンス</span><span class="sxs-lookup"><span data-stu-id="4ff3e-104">Console API reference</span></span>  

<span data-ttu-id="4ff3e-105">コンソール API メソッドを使用して、JavaScript からコンソールにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-105">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="4ff3e-106">トピックの対話型の概要については、「コンソールへのログ メッセージの使用を開始する [」に移動します][DevtoolsConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-106">For an interactive introduction to the topic, navigate to [Get Started With Logging Messages To The Console][DevtoolsConsoleLog].</span></span>  <span data-ttu-id="4ff3e-107">コンソール ウィンドウからしか使用できない便利なメソッドや、コンソール ユーティリティ API リファレンス に `debug()` `monitorEvents()` [移動します][DevtoolConsoleUtilities]。 </span><span class="sxs-lookup"><span data-stu-id="4ff3e-107">For the convenience methods like `debug()` or `monitorEvents()` which are only available from the **Console** pane, navigate to [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <a name="assert"></a><span data-ttu-id="4ff3e-108">assert</span><span class="sxs-lookup"><span data-stu-id="4ff3e-108">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="4ff3e-109">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-109">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="4ff3e-110">評価時 [にコンソールに](#error) エラー `expression` を書き込みます `false` 。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-110">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert() の例の結果" lightbox="../media/console-demo-assert-button.msft.png":::
   <span data-ttu-id="4ff3e-112">図 1: 例の `console.assert()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-112">Figure 1:  The result of the `console.assert()` example</span></span>  
:::image-end:::  

---  

## <a name="clear"></a><span data-ttu-id="4ff3e-113">clear</span><span class="sxs-lookup"><span data-stu-id="4ff3e-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="4ff3e-114">コンソールをクリアします。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="4ff3e-115">[ [ログの保持]][DevtoolsConsoleReferenceLevel] が有効になっている場合 [、clear](#clear) メソッドは無効になります。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

### <a name="see-also"></a><span data-ttu-id="4ff3e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ff3e-116">See also</span></span>  

*   [<span data-ttu-id="4ff3e-117">コンソールをクリアする</span><span class="sxs-lookup"><span data-stu-id="4ff3e-117">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a><span data-ttu-id="4ff3e-118">count</span><span class="sxs-lookup"><span data-stu-id="4ff3e-118">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="4ff3e-119">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-119">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-120">count メソッドが同じ行[](#count)で呼び出された回数を同じ行で書き込みます `label` 。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-120">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="4ff3e-121">[countReset メソッドを使用して](#countreset)、カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-121">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count() の例の結果" lightbox="../media/console-demo-count-button.msft.png":::
   <span data-ttu-id="4ff3e-123">図 2: 例の `console.count()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-123">Figure 2:  The result of the `console.count()` example</span></span>  
:::image-end:::  

---  

## <a name="countreset"></a><span data-ttu-id="4ff3e-124">countReset</span><span class="sxs-lookup"><span data-stu-id="4ff3e-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="4ff3e-125">カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <a name="debug"></a><span data-ttu-id="4ff3e-126">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4ff3e-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="4ff3e-127">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`

<span data-ttu-id="4ff3e-128">異なるログ [レベルを除](#log) き、ログと同じです。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-128">Identical to [log](#log) except different log level.</span></span>  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug() の例の結果" lightbox="../media/console-demo-debug-button.msft.png":::
   <span data-ttu-id="4ff3e-130">図 3: 例の `console.debug()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-130">Figure 3:  The result of the `console.debug()` example</span></span>  
:::image-end:::  

---  

## <a name="dir"></a><span data-ttu-id="4ff3e-131">dir</span><span class="sxs-lookup"><span data-stu-id="4ff3e-131">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="4ff3e-132">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-133">指定したオブジェクトの JSON 表記を印刷します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-133">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir() の例の結果" lightbox="../media/console-demo-dir-button.msft.png":::
   <span data-ttu-id="4ff3e-135">図 4: 例の `console.dir()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-135">Figure 4:  The result of the `console.dir()` example</span></span>  
:::image-end:::  

---  

## <a name="dirxml"></a><span data-ttu-id="4ff3e-136">dirxml</span><span class="sxs-lookup"><span data-stu-id="4ff3e-136">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="4ff3e-137">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-137">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-138">の子孫の XML 表現を印刷します `node` 。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-138">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml() の例の結果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   <span data-ttu-id="4ff3e-140">図 5: 例の `console.dirxml()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-140">Figure 5:  The result of the `console.dirxml()` example</span></span>  
:::image-end:::  

---  

## <a name="error"></a><span data-ttu-id="4ff3e-141">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="4ff3e-141">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="4ff3e-142">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-142">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="4ff3e-143">コンソールに出力し、エラーとして書式設定し、 `object` スタック トレースを含みます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-143">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error() の例の結果" lightbox="../media/console-demo-error-button.msft.png":::
   <span data-ttu-id="4ff3e-145">図 6: 例の `console.error()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-145">Figure 6:  The result of the `console.error()` example</span></span>  
:::image-end:::  

---  

## <a name="group"></a><span data-ttu-id="4ff3e-146">グループ</span><span class="sxs-lookup"><span data-stu-id="4ff3e-146">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="4ff3e-147">groupEnd メソッドが使用されるまで、メッセージを [視覚的に](#groupend) グループ化します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-147">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="4ff3e-148">[groupCollapsed メソッドを使用](#groupcollapsed)して、コンソールに最初にログに記録するときにグループを折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-148">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

:::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="console.group() の例の結果" lightbox="../media/console-demo-group-button.msft.png":::
   <span data-ttu-id="4ff3e-150">図 7: 例の `console.group()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-150">Figure 7:  The result of the `console.group()` example</span></span>  
:::image-end:::  

---  

## <a name="groupcollapsed"></a><span data-ttu-id="4ff3e-151">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="4ff3e-151">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="4ff3e-152">log メソッド [と同](#log) じですが、グループはコンソールにログ記録するときに最初は折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-152">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

---  

## <a name="groupend"></a><span data-ttu-id="4ff3e-153">groupEnd</span><span class="sxs-lookup"><span data-stu-id="4ff3e-153">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="4ff3e-154">メッセージの視覚的なグループ化を停止します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-154">Stops visually grouping messages.</span></span>  <span data-ttu-id="4ff3e-155">group メソッドに [移動](#group) します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-155">Navigate to the [group](#group) method.</span></span>  

---  

## <a name="info"></a><span data-ttu-id="4ff3e-156">情報</span><span class="sxs-lookup"><span data-stu-id="4ff3e-156">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="4ff3e-157">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-157">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-158">log メソッド [と同](#log) じです。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-158">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="console.info() の例の結果" lightbox="../media/console-demo-info-button.msft.png":::
   <span data-ttu-id="4ff3e-160">図 8: 例の `console.info()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-160">Figure 8:  The result of the `console.info()` example</span></span>  
:::image-end:::  

---  

## <a name="log"></a><span data-ttu-id="4ff3e-161">log</span><span class="sxs-lookup"><span data-stu-id="4ff3e-161">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="4ff3e-162">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-163">コンソールにメッセージを印刷します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-163">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log() の例の結果" lightbox="../media/console-demo-log-button.msft.png":::
   <span data-ttu-id="4ff3e-165">図 9: 例の `console.log()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-165">Figure 9:  The result of the `console.log()` example</span></span>  
:::image-end:::  

---  

## <a name="table"></a><span data-ttu-id="4ff3e-166">table</span><span class="sxs-lookup"><span data-stu-id="4ff3e-166">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="4ff3e-167">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-167">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-168">オブジェクトの配列をテーブルとしてログに記録します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-168">Logs an array of objects as a table.</span></span>  

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

:::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="console.table() の例の結果" lightbox="../media/console-demo-table-button.msft.png":::
   <span data-ttu-id="4ff3e-170">図 10: 例の `console.table()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-170">Figure 10:  The result of the `console.table()` example</span></span>  
:::image-end:::  

---  

## <a name="time"></a><span data-ttu-id="4ff3e-171">time</span><span class="sxs-lookup"><span data-stu-id="4ff3e-171">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="4ff3e-172">新しいタイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-172">Starts a new timer.</span></span>  <span data-ttu-id="4ff3e-173">[timeEnd メソッドを](#timeend)使用してタイマーを停止し、経過時間をコンソールに印刷します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-173">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time() の例の結果" lightbox="../media/console-demo-time-button.msft.png":::
   <span data-ttu-id="4ff3e-175">図 11: 例の `console.time()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-175">Figure 11:  The result of the `console.time()` example</span></span>  
:::image-end:::  

---  

## <a name="timeend"></a><span data-ttu-id="4ff3e-176">timeEnd</span><span class="sxs-lookup"><span data-stu-id="4ff3e-176">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="4ff3e-177">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-177">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-178">タイマーを停止します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-178">Stops a timer.</span></span>  <span data-ttu-id="4ff3e-179">time メソッドに [移動](#time) します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-179">Navigate to the [time](#time) method.</span></span>  

---  

## <a name="trace"></a><span data-ttu-id="4ff3e-180">trace</span><span class="sxs-lookup"><span data-stu-id="4ff3e-180">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="4ff3e-181">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-181">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="4ff3e-182">スタック トレースをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-182">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace() の例の結果" lightbox="../media/console-demo-trace-button.msft.png":::
   <span data-ttu-id="4ff3e-184">図 12: 例の `console.trace()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-184">Figure 12:  The result of the `console.trace()` example</span></span>  
:::image-end:::  

---  

## <a name="warn"></a><span data-ttu-id="4ff3e-185">warn</span><span class="sxs-lookup"><span data-stu-id="4ff3e-185">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="4ff3e-186">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="4ff3e-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="4ff3e-187">コンソールに警告を出力します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-187">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn() の例の結果" lightbox="../media/console-demo-warn-button.msft.png":::
   <span data-ttu-id="4ff3e-189">図 13: 例の `console.warn()` 結果</span><span class="sxs-lookup"><span data-stu-id="4ff3e-189">Figure 13:  The result of the `console.warn()` example</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4ff3e-190">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4ff3e-190">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのログ メッセージの使用を開始する"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソール ユーティリティ API リファレンス"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "コンソールのクリア - コンソール リファレンス"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "ページ読み込み時にメッセージを保持する - コンソール リファレンス"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (クロム) 開発者ツール"  

> [!NOTE]
> <span data-ttu-id="4ff3e-197">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-197">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4ff3e-198">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/api) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-198">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4ff3e-200">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-200">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
