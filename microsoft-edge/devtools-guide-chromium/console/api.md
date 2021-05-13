---
description: コンソール API を使用して、コンソールにメッセージを書き込みます。
title: コンソール API リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 08a29db4dec05de0a21a0e6a9de9a0fb6e0d3f56
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564512"
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
# <a name="console-api-reference"></a><span data-ttu-id="18d43-104">コンソール API リファレンス</span><span class="sxs-lookup"><span data-stu-id="18d43-104">Console API reference</span></span>  

<span data-ttu-id="18d43-105">コンソール **ツール** は、DevTools で複数のタスクを完了するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="18d43-105">The **Console** tool is helpful when you complete multiple tasks in the DevTools.</span></span>  <span data-ttu-id="18d43-106">API は、スクリプトに含める場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18d43-106">APIs are available to include in your scripts.</span></span> <span data-ttu-id="18d43-107">便利なメソッドは、コンソール ツール (and **メソッドなど** ) `debug()` でのみ `monitorEvents()` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="18d43-107">Convenience methods are only available for use in the **Console** tool, such as the `debug()` and `monitorEvents()` methods.</span></span>  <span data-ttu-id="18d43-108">コンソールの使用を開始する方法の詳細 **については、「コンソール**へのメッセージのログ記録の開始 [」に移動します][DevtoolsConsoleConsoleLog]。</span><span class="sxs-lookup"><span data-stu-id="18d43-108">For more information on getting started with the **Console**, navigate to [Get started with logging messages to the Console][DevtoolsConsoleConsoleLog].</span></span>  <span data-ttu-id="18d43-109">コンソールの便利なメソッドの詳細については、「 **コンソール**ユーティリティ [API リファレンス」に移動します][DevtoolConsoleUtilities]。</span><span class="sxs-lookup"><span data-stu-id="18d43-109">For more information on the convenience methods in the **Console**, navigate to [Console Utilities API Reference][DevtoolConsoleUtilities].</span></span>  

---  

## <a name="assert"></a><span data-ttu-id="18d43-110">assert</span><span class="sxs-lookup"><span data-stu-id="18d43-110">assert</span></span>  

<span data-ttu-id="18d43-111">このメソッドは、評価[時に](#error)**コンソール**に `expression` エラーを書き込みます `false` 。</span><span class="sxs-lookup"><span data-stu-id="18d43-111">This method writes an [error](#error) to the **Console** when `expression` evaluates to `false`.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-112">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-112">JavaScript syntax</span></span>  

```javascript
console.assert(expression, object)
```

<span data-ttu-id="18d43-113">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-113">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-114">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-114">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-115">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-115">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const x = 5;
      const y = 3;
      const reason = 'x is expected to be less than y';
      console.assert(x < y, {x, y, reason});
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-116">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-116">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert() の例の結果" lightbox="../media/console-demo-assert-button.msft.png":::
         <span data-ttu-id="18d43-118">例の `console.assert()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-118">The result of the `console.assert()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="clear"></a><span data-ttu-id="18d43-119">clear</span><span class="sxs-lookup"><span data-stu-id="18d43-119">clear</span></span>  

<span data-ttu-id="18d43-120">このメソッドは、コンソールをクリア **します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-120">This method clears the **Console**.</span></span>  

<span data-ttu-id="18d43-121">[ [ログの保持]][DevtoolsConsoleReferenceFilter] がオンの場合 [、clear](#clear) メソッドはオフになります。</span><span class="sxs-lookup"><span data-stu-id="18d43-121">If [Preserve Log][DevtoolsConsoleReferenceFilter] is turned on, the [clear](#clear) method is turned off.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-122">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-122">JavaScript syntax</span></span>  

```javascript
console.clear()
```

### <a name="javascript-example"></a><span data-ttu-id="18d43-123">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-123">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-124">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-124">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.clear();  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-125">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-125">Output</span></span>
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

### <a name="see-also"></a><span data-ttu-id="18d43-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="18d43-126">See also</span></span>  

*   [<span data-ttu-id="18d43-127">コンソールをクリアする</span><span class="sxs-lookup"><span data-stu-id="18d43-127">Clear the Console</span></span>][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a><span data-ttu-id="18d43-128">count</span><span class="sxs-lookup"><span data-stu-id="18d43-128">count</span></span>  

<span data-ttu-id="18d43-129">このメソッドは、count メソッドが同[](#count)じ行で呼び出された回数を同じ行で書き込みます `label` 。</span><span class="sxs-lookup"><span data-stu-id="18d43-129">This method writes the number of times that the [count](#count) method has been invoked at the same line and with the same `label`.</span></span>  <span data-ttu-id="18d43-130">[countReset メソッドを使用して](#countreset)、カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="18d43-130">Use the [countReset](#countreset) method to reset the count.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-131">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-131">JavaScript syntax</span></span>  

```javascript
console.count([label])
```  

<span data-ttu-id="18d43-132">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-132">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-133">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-133">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-134">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-134">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.count();
      console.count('coffee');
      console.count();
      console.count();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-135">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-135">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count() の例の結果" lightbox="../media/console-demo-count-button.msft.png":::
         <span data-ttu-id="18d43-137">例の `console.count()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-137">The result of the `console.count()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="countreset"></a><span data-ttu-id="18d43-138">countReset</span><span class="sxs-lookup"><span data-stu-id="18d43-138">countReset</span></span>  

<span data-ttu-id="18d43-139">このメソッドは、カウントをリセットします。</span><span class="sxs-lookup"><span data-stu-id="18d43-139">This method resets a count.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-140">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-140">JavaScript syntax</span></span>  

```javascript
console.countReset([label])
```  

### <a name="javascript-example"></a><span data-ttu-id="18d43-141">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-141">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-142">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-142">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.countReset();
      console.countReset('coffee');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-143">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-143">Output</span></span>
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

---  

## <a name="debug"></a><span data-ttu-id="18d43-144">デバッグ</span><span class="sxs-lookup"><span data-stu-id="18d43-144">debug</span></span>  

<span data-ttu-id="18d43-145">このメソッドは、異なるログ レベルを [除き、log](#log) メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="18d43-145">This method is identical to the [log](#log) method, except different log level.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-146">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-146">JavaScript syntax</span></span>  

```javascript
console.debug(object [, object, ...])
```  

<span data-ttu-id="18d43-147">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-147">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Verbose`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-148">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-148">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-149">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-149">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.debug('debug');  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-150">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-150">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug() の例の結果" lightbox="../media/console-demo-debug-button.msft.png":::
         <span data-ttu-id="18d43-152">例の `console.debug()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-152">The result of the `console.debug()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dir"></a><span data-ttu-id="18d43-153">dir</span><span class="sxs-lookup"><span data-stu-id="18d43-153">dir</span></span>  

<span data-ttu-id="18d43-154">このメソッドは、指定したオブジェクトの JSON 表記を出力します。</span><span class="sxs-lookup"><span data-stu-id="18d43-154">This method prints a JSON representation of the specified object.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-155">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-155">JavaScript syntax</span></span>  

```javascript
console.dir(object)
```  

<span data-ttu-id="18d43-156">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-156">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-157">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-157">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-158">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-158">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dir(document.head);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-159">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-159">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir() の例の結果" lightbox="../media/console-demo-dir-button.msft.png":::
         <span data-ttu-id="18d43-161">例の `console.dir()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-161">The result of the `console.dir()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dirxml"></a><span data-ttu-id="18d43-162">dirxml</span><span class="sxs-lookup"><span data-stu-id="18d43-162">dirxml</span></span>  

<span data-ttu-id="18d43-163">このメソッドは、 の子孫の XML 表現を出力します `node` 。</span><span class="sxs-lookup"><span data-stu-id="18d43-163">This method prints an XML representation of the descendants of `node`.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-164">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-164">JavaScript syntax</span></span>  

```javascript
console.dirxml(node)
```  

<span data-ttu-id="18d43-165">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-165">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-166">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-166">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-167">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-167">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dirxml(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-168">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-168">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml() の例の結果" lightbox="../media/console-demo-dirxml-button.msft.png":::
         <span data-ttu-id="18d43-170">例の `console.dirxml()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-170">The result of the `console.dirxml()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="error"></a><span data-ttu-id="18d43-171">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="18d43-171">error</span></span>  

<span data-ttu-id="18d43-172">このメソッドは、コンソール `object` に出力\*\*\*\* され、エラーとして書式設定され、スタック トレースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18d43-172">This method prints the `object` to the **Console**, formats it as an error, and includes a stack trace.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-173">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-173">JavaScript syntax</span></span>  

```javascript
console.error(object [, object, ...])
```  

<span data-ttu-id="18d43-174">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-174">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Error`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-175">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-175">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-176">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-176">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-177">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-177">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error() の例の結果" lightbox="../media/console-demo-error-button.msft.png":::
         <span data-ttu-id="18d43-179">例の `console.error()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-179">The result of the `console.error()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="group"></a><span data-ttu-id="18d43-180">グループ</span><span class="sxs-lookup"><span data-stu-id="18d43-180">group</span></span>  

<span data-ttu-id="18d43-181">このメソッドは [、groupEnd](#groupend) メソッドが使用されるまで、メッセージを視覚的にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="18d43-181">This method visually groups messages together until the [groupEnd](#groupend) method is used.</span></span>  <span data-ttu-id="18d43-182">[groupCollapsed メソッドを使用](#groupcollapsed)して、コンソールに最初にログを記録するときにグループを折りたたみ**します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-182">Use the [groupCollapsed](#groupcollapsed) method to collapse the group when it initially logs to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-183">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-183">JavaScript syntax</span></span>  

```javascript
console.group(label)
```  

### <a name="javascript-example"></a><span data-ttu-id="18d43-184">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-184">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-185">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-185">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const label = 'Adolescent Irradiated Espionage Tortoises';
      console.group(label);
      console.info('Leo');
      console.info('Mike');
      console.info('Don');
      console.info('Raph');
      console.groupEnd(label);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-186">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-186">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="console.group() の例の結果" lightbox="../media/console-demo-group-button.msft.png":::
         <span data-ttu-id="18d43-188">例の `console.group()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-188">The result of the `console.group()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="groupcollapsed"></a><span data-ttu-id="18d43-189">groupCollapsed</span><span class="sxs-lookup"><span data-stu-id="18d43-189">groupCollapsed</span></span>  

<span data-ttu-id="18d43-190">このメソッドは log [メソッドと同](#log) じですが、コンソールにログを記録するときにグループが最初に折りたたまれる場合を除 **きます**。</span><span class="sxs-lookup"><span data-stu-id="18d43-190">This method is identical to the [log](#log) method, except the group is initially collapsed when it logs to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-191">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-191">JavaScript syntax</span></span>  

```javascript
console.groupCollapsed(label)
```  

---  

## <a name="groupend"></a><span data-ttu-id="18d43-192">groupEnd</span><span class="sxs-lookup"><span data-stu-id="18d43-192">groupEnd</span></span>  

<span data-ttu-id="18d43-193">このメソッドは、メッセージの視覚的なグループ化を停止します。</span><span class="sxs-lookup"><span data-stu-id="18d43-193">This method stops visually grouping messages.</span></span>  <span data-ttu-id="18d43-194">group メソッドに [移動](#group) します。</span><span class="sxs-lookup"><span data-stu-id="18d43-194">Navigate to the [group](#group) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-195">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-195">JavaScript syntax</span></span>  

```javascript
console.groupEnd(label)
```  

---  

## <a name="info"></a><span data-ttu-id="18d43-196">情報</span><span class="sxs-lookup"><span data-stu-id="18d43-196">info</span></span>  

<span data-ttu-id="18d43-197">このメソッドは log メソッドと [同](#log) じです。</span><span class="sxs-lookup"><span data-stu-id="18d43-197">This method is identical to the [log](#log) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-198">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-198">JavaScript syntax</span></span>  

```javascript
console.info(object [, object, ...])
```  

<span data-ttu-id="18d43-199">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-199">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-200">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-200">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-201">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-201">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.info('info');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-202">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-202">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="console.info() の例の結果" lightbox="../media/console-demo-info-button.msft.png":::
         <span data-ttu-id="18d43-204">例の `console.info()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-204">The result of the `console.info()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="log"></a><span data-ttu-id="18d43-205">log</span><span class="sxs-lookup"><span data-stu-id="18d43-205">log</span></span>  

<span data-ttu-id="18d43-206">このメソッドは、コンソールにメッセージを出力 **します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-206">This method prints a message to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-207">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-207">JavaScript syntax</span></span>  

```javascript
console.log(object [, object, ...])
```  

<span data-ttu-id="18d43-208">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-208">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-209">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-209">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-210">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-210">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.log('log');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-211">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-211">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log() の例の結果" lightbox="../media/console-demo-log-button.msft.png":::
         <span data-ttu-id="18d43-213">例の `console.log()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-213">The result of the `console.log()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a><span data-ttu-id="18d43-214">table</span><span class="sxs-lookup"><span data-stu-id="18d43-214">table</span></span>  

<span data-ttu-id="18d43-215">このメソッドは、オブジェクトの配列をテーブルとしてログに記録します。</span><span class="sxs-lookup"><span data-stu-id="18d43-215">This method logs an array of objects as a table.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-216">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-216">JavaScript syntax</span></span>  

```javascript
console.table(array)
```  

<span data-ttu-id="18d43-217">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-217">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-218">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-218">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-219">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-219">Input</span></span>  
   :::column-end:::
   :::column span="3":::
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
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-220">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-220">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="console.table() の例の結果" lightbox="../media/console-demo-table-button.msft.png":::
         <span data-ttu-id="18d43-222">例の `console.table()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-222">The result of the `console.table()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="time"></a><span data-ttu-id="18d43-223">time</span><span class="sxs-lookup"><span data-stu-id="18d43-223">time</span></span>  

<span data-ttu-id="18d43-224">このメソッドは、新しいタイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="18d43-224">This method starts a new timer.</span></span>  <span data-ttu-id="18d43-225">[timeEnd メソッドを使用](#timeend)してタイマーを停止し、経過時間をコンソールに出力**します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-225">Use the [timeEnd](#timeend) method to stop the timer and print the elapsed time to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-226">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-226">JavaScript syntax</span></span>  

```javascript
console.time([label])
```  

### <a name="javascript-example"></a><span data-ttu-id="18d43-227">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-227">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-228">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-228">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.time();
      for (var i = 0; i < 100000; i++) {
          let square = i ** 2;
      }
      console.timeEnd();
      ```
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-229">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-229">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time() の例の結果" lightbox="../media/console-demo-time-button.msft.png":::
         <span data-ttu-id="18d43-231">例の `console.time()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-231">The result of the `console.time()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="timeend"></a><span data-ttu-id="18d43-232">timeEnd</span><span class="sxs-lookup"><span data-stu-id="18d43-232">timeEnd</span></span>  

<span data-ttu-id="18d43-233">このメソッドはタイマーを停止します。</span><span class="sxs-lookup"><span data-stu-id="18d43-233">This method stops a timer.</span></span>  <span data-ttu-id="18d43-234">詳細については、time メソッドに [移動](#time) します。</span><span class="sxs-lookup"><span data-stu-id="18d43-234">For more information, navigate to the [time](#time) method.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-235">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-235">JavaScript syntax</span></span>  

```javascript
console.timeEnd([label])
```  

<span data-ttu-id="18d43-236">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-236">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

---  

## <a name="trace"></a><span data-ttu-id="18d43-237">trace</span><span class="sxs-lookup"><span data-stu-id="18d43-237">trace</span></span>  

<span data-ttu-id="18d43-238">このメソッドは、スタック トレースをコンソールに出力 **します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-238">This method prints a stack trace to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-239">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-239">JavaScript syntax</span></span>  

```javascript
console.trace()
```  

<span data-ttu-id="18d43-240">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-240">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Info`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-241">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-241">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-242">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-242">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      const first = () => { second(); };
      const second = () => { third(); };
      const third = () => { fourth(); };
      const fourth = () => { console.trace(); };
      first();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-243">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-243">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace() の例の結果" lightbox="../media/console-demo-trace-button.msft.png":::
         <span data-ttu-id="18d43-245">例の `console.trace()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-245">The result of the `console.trace()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="warn"></a><span data-ttu-id="18d43-246">warn</span><span class="sxs-lookup"><span data-stu-id="18d43-246">warn</span></span>  

<span data-ttu-id="18d43-247">このメソッドは、コンソールに警告を出力 **します**。</span><span class="sxs-lookup"><span data-stu-id="18d43-247">This method prints a warning to the **Console**.</span></span>  

### <a name="javascript-syntax"></a><span data-ttu-id="18d43-248">JavaScript 構文</span><span class="sxs-lookup"><span data-stu-id="18d43-248">JavaScript syntax</span></span>  

```javascript
console.warn(object [, object, ...])
```  

<span data-ttu-id="18d43-249">[ログ レベル][DevtoolsConsoleReferencePersist]:</span><span class="sxs-lookup"><span data-stu-id="18d43-249">[Log level][DevtoolsConsoleReferencePersist]:</span></span> `Warning`  

### <a name="javascript-example"></a><span data-ttu-id="18d43-250">JavaScript の例</span><span class="sxs-lookup"><span data-stu-id="18d43-250">JavaScript example</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-251">入力</span><span class="sxs-lookup"><span data-stu-id="18d43-251">Input</span></span>  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.warn('warn');
      ```
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="18d43-252">出力</span><span class="sxs-lookup"><span data-stu-id="18d43-252">Output</span></span>
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn() の例の結果" lightbox="../media/console-demo-warn-button.msft.png":::
         <span data-ttu-id="18d43-254">例の `console.warn()` 結果</span><span class="sxs-lookup"><span data-stu-id="18d43-254">The result of the `console.warn()` example</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="18d43-255">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="18d43-255">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール にログイン|Microsoft Docs"  
[DevtoolConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleReferenceClear]: ./reference.md#clear-the-console "[コンソール ] - [コンソール] リファレンス をクリア|Microsoft Docs"  
[DevtoolsConsoleReferenceFilter]: ./reference.md#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferencePersist]: ./reference.md#persist-messages-across-page-loads "ページの読み込み時にメッセージを保持する - コンソール参照|Microsoft Docs"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツールの概要 |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="18d43-262">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="18d43-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="18d43-263">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/api) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="18d43-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/api) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="18d43-265">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="18d43-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
