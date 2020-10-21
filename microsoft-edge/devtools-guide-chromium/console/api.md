---
description: コンソール API を使って、コンソールにメッセージを書き込みます。
title: 本体の API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 38fb3ee2345530775423ac3ec8e53e0d8de76eaf
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125287"
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

# <span data-ttu-id="31daf-104">本体の API リファレンス</span><span class="sxs-lookup"><span data-stu-id="31daf-104">Console API Reference</span></span>  

<span data-ttu-id="31daf-105">コンソール API メソッドを使って、JavaScript からコンソールにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="31daf-105">Use the Console API methods to write messages to the Console from your JavaScript.</span></span>  <span data-ttu-id="31daf-106">このトピックの対話的な紹介については、「 [コンソールへのメッセージのログ記録の][DevtoolsConsoleLog]概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31daf-106">For an interactive introduction to the topic, navigate to [Get Started With Logging Messages To The Console][DevtoolsConsoleLog].</span></span>  <span data-ttu-id="31daf-107">このような便利なメソッド、 `debug()` または `monitorEvents()` **コンソール** ウィンドウからのみ利用できる便利なメソッドについては、[ [コンソールユーティリティ API リファレンス][DevtoolConsoleUtilities]] に移動します。</span><span class="sxs-lookup"><span data-stu-id="31daf-107">For the convenience methods like `debug()` or `monitorEvents()` which are only available from the **Console** pane, navigate to [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <span data-ttu-id="31daf-108">assert</span><span class="sxs-lookup"><span data-stu-id="31daf-108">assert</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="31daf-109">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-109">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

<span data-ttu-id="31daf-110">評価されたときに、本体に [エラー](#error) を書き込み `expression` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="31daf-110">Writes an [error](#error) to the console when `expression` evaluates to `false`.</span></span>  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-assert-button.msft.png":::
   <span data-ttu-id="31daf-112">図 1: 例の結果 `console.assert()`</span><span class="sxs-lookup"><span data-stu-id="31daf-112">Figure 1:  The result of the `console.assert()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-113">clear</span><span class="sxs-lookup"><span data-stu-id="31daf-113">clear</span></span>  

```javascript
console.clear()
```

<span data-ttu-id="31daf-114">本体をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31daf-114">Clears the console.</span></span>  

```javascript
console.clear();  
```  

<span data-ttu-id="31daf-115">[ [ログの保持][DevtoolsConsoleReferenceLevel] ] が有効になっている場合、 [clear](#clear) メソッドは無効になります。</span><span class="sxs-lookup"><span data-stu-id="31daf-115">If [Preserve Log][DevtoolsConsoleReferenceLevel] is enabled, the [clear](#clear) method is disabled.</span></span>  

### <span data-ttu-id="31daf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="31daf-116">See also</span></span>  

*   [<span data-ttu-id="31daf-117">本体をクリアする</span><span class="sxs-lookup"><span data-stu-id="31daf-117">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <span data-ttu-id="31daf-118">枚数</span><span class="sxs-lookup"><span data-stu-id="31daf-118">count</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="31daf-119">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-119">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-120">[Count](#count)メソッドが同じ行で呼び出され、同じ行にある回数を書き込み `label` ます。</span><span class="sxs-lookup"><span data-stu-id="31daf-120">Writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="31daf-121">[Countreset](#countreset)メソッドを使用して、カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="31daf-121">Use the [countReset](#countreset) method to reset the count.</span></span>  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-count-button.msft.png":::
   <span data-ttu-id="31daf-123">図 2: 例の結果 `console.count()`</span><span class="sxs-lookup"><span data-stu-id="31daf-123">Figure 2:  The result of the `console.count()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-124">countReset</span><span class="sxs-lookup"><span data-stu-id="31daf-124">countReset</span></span>  

```javascript
console.countReset([label])
```  

<span data-ttu-id="31daf-125">カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="31daf-125">Resets a count.</span></span>  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <span data-ttu-id="31daf-126">デバッグ</span><span class="sxs-lookup"><span data-stu-id="31daf-126">debug</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="31daf-127">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-127">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`

<span data-ttu-id="31daf-128">異なるログレベルを除いて、 [ログ](#log) と同じです。</span><span class="sxs-lookup"><span data-stu-id="31daf-128">Identical to [log](#log) except different log level.</span></span>  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-debug-button.msft.png":::
   <span data-ttu-id="31daf-130">図 3: 例の結果 `console.debug()`</span><span class="sxs-lookup"><span data-stu-id="31daf-130">Figure 3:  The result of the `console.debug()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-131">dir</span><span class="sxs-lookup"><span data-stu-id="31daf-131">dir</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="31daf-132">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-133">指定したオブジェクトの JSON 表現を出力します。</span><span class="sxs-lookup"><span data-stu-id="31daf-133">Prints a JSON representation of the specified object.</span></span>  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-dir-button.msft.png":::
   <span data-ttu-id="31daf-135">図 4: この例の結果 `console.dir()`</span><span class="sxs-lookup"><span data-stu-id="31daf-135">Figure 4:  The result of the `console.dir()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-136">dirxml</span><span class="sxs-lookup"><span data-stu-id="31daf-136">dirxml</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="31daf-137">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-137">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-138">の子の XML 表現を出力 `node` します。</span><span class="sxs-lookup"><span data-stu-id="31daf-138">Prints an XML representation of the descendants of `node`.</span></span>  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   <span data-ttu-id="31daf-140">図 5: 例の結果 `console.dirxml()`</span><span class="sxs-lookup"><span data-stu-id="31daf-140">Figure 5:  The result of the `console.dirxml()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-141">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="31daf-141">error</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="31daf-142">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-142">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

<span data-ttu-id="31daf-143">`object`コンソールにを出力し、エラーとして書式設定し、スタックトレースを含めます。</span><span class="sxs-lookup"><span data-stu-id="31daf-143">Prints the `object` to the Console, formats it as an error, and includes a stack trace.</span></span>  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-error-button.msft.png":::
   <span data-ttu-id="31daf-145">図 6: 例の結果 `console.error()`</span><span class="sxs-lookup"><span data-stu-id="31daf-145">Figure 6:  The result of the `console.error()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-146">グループ</span><span class="sxs-lookup"><span data-stu-id="31daf-146">group</span></span>  

```javascript
console.group(label)
```  

<span data-ttu-id="31daf-147">[Groupend](#groupend)メソッドが使われるまで、メッセージを視覚的にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="31daf-147">Visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="31daf-148">グループが最初にコンソールにログインしたときに、グループを折りたたむには、 [Groupcollapsed](#groupcollapsed) れたメソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="31daf-148">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it is initially logged to the Console.</span></span>  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

:::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-group-button.msft.png":::
   <span data-ttu-id="31daf-150">図 7: 例の結果 `console.group()`</span><span class="sxs-lookup"><span data-stu-id="31daf-150">Figure 7:  The result of the `console.group()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-151">groupCollapsed れている</span><span class="sxs-lookup"><span data-stu-id="31daf-151">groupCollapsed</span></span>  

```javascript
console.groupCollapsed(label)
```  

<span data-ttu-id="31daf-152">[Log](#log)メソッドと同じですが、グループをコンソールに記録したときに最初に折りたたまれている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="31daf-152">Same as the [log](#log) method, except the group is initially collapsed when it is logged to the Console.</span></span>  

---  

## <span data-ttu-id="31daf-153">groupEnd</span><span class="sxs-lookup"><span data-stu-id="31daf-153">groupEnd</span></span>  

```javascript
console.groupEnd(label)
```  

<span data-ttu-id="31daf-154">視覚的にメッセージをグループ化することを停止します。</span><span class="sxs-lookup"><span data-stu-id="31daf-154">Stops visually grouping messages.</span></span>  <span data-ttu-id="31daf-155">[グループ](#group)のメソッドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="31daf-155">See the [group](#group) method.</span></span>  

---  

## <span data-ttu-id="31daf-156">情報</span><span class="sxs-lookup"><span data-stu-id="31daf-156">info</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="31daf-157">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-157">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-158">[Log](#log)メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="31daf-158">Identical to the [log](#log) method.</span></span>  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-info-button.msft.png":::
   <span data-ttu-id="31daf-160">図 8: 例の結果 `console.info()`</span><span class="sxs-lookup"><span data-stu-id="31daf-160">Figure 8:  The result of the `console.info()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-161">出力</span><span class="sxs-lookup"><span data-stu-id="31daf-161">log</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="31daf-162">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-162">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-163">コンソールにメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="31daf-163">Prints a message to the Console.</span></span>  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-log-button.msft.png":::
   <span data-ttu-id="31daf-165">図 9: 例の結果 `console.log()`</span><span class="sxs-lookup"><span data-stu-id="31daf-165">Figure 9:  The result of the `console.log()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-166">'95'5c</span><span class="sxs-lookup"><span data-stu-id="31daf-166">table</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="31daf-167">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-167">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-168">オブジェクトの配列をテーブルとしてログに記録します。</span><span class="sxs-lookup"><span data-stu-id="31daf-168">Logs an array of objects as a table.</span></span>  

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

:::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-table-button.msft.png":::
   <span data-ttu-id="31daf-170">図 10: 例の結果 `console.table()`</span><span class="sxs-lookup"><span data-stu-id="31daf-170">Figure 10:  The result of the `console.table()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-171">time</span><span class="sxs-lookup"><span data-stu-id="31daf-171">time</span></span>  

```javascript
console.time([label])
```  

<span data-ttu-id="31daf-172">新しいタイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="31daf-172">Starts a new timer.</span></span>  <span data-ttu-id="31daf-173">[Timeend](#timeend)メソッドを使ってタイマーを停止し、経過時間を本体に出力します。</span><span class="sxs-lookup"><span data-stu-id="31daf-173">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the Console.</span></span>  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-time-button.msft.png":::
   <span data-ttu-id="31daf-175">図 11: 例の結果 `console.time()`</span><span class="sxs-lookup"><span data-stu-id="31daf-175">Figure 11:  The result of the `console.time()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-176">timeEnd</span><span class="sxs-lookup"><span data-stu-id="31daf-176">timeEnd</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="31daf-177">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-177">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-178">タイマーを停止します。</span><span class="sxs-lookup"><span data-stu-id="31daf-178">Stops a timer.</span></span>  <span data-ttu-id="31daf-179">[Time](#time)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31daf-179">See the [time](#time) method.</span></span>  

---  

## <span data-ttu-id="31daf-180">trace</span><span class="sxs-lookup"><span data-stu-id="31daf-180">trace</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="31daf-181">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-181">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

<span data-ttu-id="31daf-182">スタックトレースを本体に出力します。</span><span class="sxs-lookup"><span data-stu-id="31daf-182">Prints a stack trace to the Console.</span></span>  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-trace-button.msft.png":::
   <span data-ttu-id="31daf-184">図 12: 例の結果 `console.trace()`</span><span class="sxs-lookup"><span data-stu-id="31daf-184">Figure 12:  The result of the `console.trace()` example</span></span>  
:::image-end:::  

---  

## <span data-ttu-id="31daf-185">warn</span><span class="sxs-lookup"><span data-stu-id="31daf-185">warn</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="31daf-186">[ログレベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="31daf-186">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

<span data-ttu-id="31daf-187">コンソールに警告を出力します。</span><span class="sxs-lookup"><span data-stu-id="31daf-187">Prints a warning to the Console.</span></span>  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="本体の assert () の結果" lightbox="../media/console-demo-warn-button.msft.png":::
   <span data-ttu-id="31daf-189">図 13: 例の結果 `console.warn()`</span><span class="sxs-lookup"><span data-stu-id="31daf-189">Figure 13:  The result of the `console.warn()` example</span></span>  
:::image-end:::  

## <span data-ttu-id="31daf-190">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="31daf-190">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのメッセージの記録を開始する"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソールユーティリティ API リファレンス"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "本体本体のリファレンスをクリアする"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "ページの読み込み中にメッセージを保持-本体のリファレンス"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログレベルによるフィルター-コンソールリファレンス"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

> [!NOTE]
> <span data-ttu-id="31daf-197">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="31daf-197">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="31daf-198">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/api) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="31daf-198">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="31daf-200">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="31daf-200">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
