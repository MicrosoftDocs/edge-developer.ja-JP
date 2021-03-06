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

# <a name="console-api-reference"></a>コンソール API リファレンス  

コンソール API メソッドを使用して、JavaScript からコンソールにメッセージを書き込みます。  トピックの対話型の概要については、「コンソールへのログ メッセージの使用を開始する [」に移動します][DevtoolsConsoleLog]。  コンソール ウィンドウからしか使用できない便利なメソッドや、コンソール ユーティリティ API リファレンス に `debug()` `monitorEvents()` [移動します][DevtoolConsoleUtilities]。 ****  

---  

## <a name="assert"></a>assert  

```javascript
console.assert(expression, object)
```

[ログ レベル][DevtoolsConsoleReferencePersist]: `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

評価時 [にコンソールに](#error) エラー `expression` を書き込みます `false` 。  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

:::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert() の例の結果" lightbox="../media/console-demo-assert-button.msft.png":::
   図 1: 例の `console.assert()` 結果  
:::image-end:::  

---  

## <a name="clear"></a>clear  

```javascript
console.clear()
```

コンソールをクリアします。  

```javascript
console.clear();  
```  

[ [ログの保持]][DevtoolsConsoleReferenceLevel] が有効になっている場合 [、clear](#clear) メソッドは無効になります。  

### <a name="see-also"></a>関連項目  

*   [コンソールをクリアする][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a>count  

```javascript
console.count([label])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

count メソッドが同じ行[](#count)で呼び出された回数を同じ行で書き込みます `label` 。  [countReset メソッドを使用して](#countreset)、カウントをリセットします。  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

:::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count() の例の結果" lightbox="../media/console-demo-count-button.msft.png":::
   図 2: 例の `console.count()` 結果  
:::image-end:::  

---  

## <a name="countreset"></a>countReset  

```javascript
console.countReset([label])
```  

カウントをリセットします。  

```javascript
console.countReset();
console.countReset('coffee');
```  

---  

## <a name="debug"></a>デバッグ  

```javascript
console.debug(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Verbose`

異なるログ [レベルを除](#log) き、ログと同じです。  

```javascript
console.debug('debug');  
```  

:::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug() の例の結果" lightbox="../media/console-demo-debug-button.msft.png":::
   図 3: 例の `console.debug()` 結果  
:::image-end:::  

---  

## <a name="dir"></a>dir  

```javascript
console.dir(object)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

指定したオブジェクトの JSON 表記を印刷します。  

```javascript
console.dir(document.head);
```  

:::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir() の例の結果" lightbox="../media/console-demo-dir-button.msft.png":::
   図 4: 例の `console.dir()` 結果  
:::image-end:::  

---  

## <a name="dirxml"></a>dirxml  

```javascript
console.dirxml(node)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

の子孫の XML 表現を印刷します `node` 。  

```javascript
console.dirxml(document);
```  

:::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml() の例の結果" lightbox="../media/console-demo-dirxml-button.msft.png":::
   図 5: 例の `console.dirxml()` 結果  
:::image-end:::  

---  

## <a name="error"></a>error (エラー)  

```javascript
console.error(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Error`  

コンソールに出力し、エラーとして書式設定し、 `object` スタック トレースを含みます。  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

:::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error() の例の結果" lightbox="../media/console-demo-error-button.msft.png":::
   図 6: 例の `console.error()` 結果  
:::image-end:::  

---  

## <a name="group"></a>グループ  

```javascript
console.group(label)
```  

groupEnd メソッドが使用されるまで、メッセージを [視覚的に](#groupend) グループ化します。  [groupCollapsed メソッドを使用](#groupcollapsed)して、コンソールに最初にログに記録するときにグループを折りたたみます。  

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
   図 7: 例の `console.group()` 結果  
:::image-end:::  

---  

## <a name="groupcollapsed"></a>groupCollapsed  

```javascript
console.groupCollapsed(label)
```  

log メソッド [と同](#log) じですが、グループはコンソールにログ記録するときに最初は折りたたまれます。  

---  

## <a name="groupend"></a>groupEnd  

```javascript
console.groupEnd(label)
```  

メッセージの視覚的なグループ化を停止します。  group メソッドに [移動](#group) します。  

---  

## <a name="info"></a>情報  

```javascript
console.info(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

log メソッド [と同](#log) じです。  

```javascript
console.info('info');
```  

:::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="console.info() の例の結果" lightbox="../media/console-demo-info-button.msft.png":::
   図 8: 例の `console.info()` 結果  
:::image-end:::  

---  

## <a name="log"></a>log  

```javascript
console.log(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

コンソールにメッセージを印刷します。  

```javascript
console.log('log');
```  

:::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log() の例の結果" lightbox="../media/console-demo-log-button.msft.png":::
   図 9: 例の `console.log()` 結果  
:::image-end:::  

---  

## <a name="table"></a>table  

```javascript
console.table(array)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

オブジェクトの配列をテーブルとしてログに記録します。  

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
   図 10: 例の `console.table()` 結果  
:::image-end:::  

---  

## <a name="time"></a>time  

```javascript
console.time([label])
```  

新しいタイマーを開始します。  [timeEnd メソッドを](#timeend)使用してタイマーを停止し、経過時間をコンソールに印刷します。  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

:::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time() の例の結果" lightbox="../media/console-demo-time-button.msft.png":::
   図 11: 例の `console.time()` 結果  
:::image-end:::  

---  

## <a name="timeend"></a>timeEnd  

```javascript
console.timeEnd([label])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

タイマーを停止します。  time メソッドに [移動](#time) します。  

---  

## <a name="trace"></a>trace  

```javascript
console.trace()
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

スタック トレースをコンソールに出力します。  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

:::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace() の例の結果" lightbox="../media/console-demo-trace-button.msft.png":::
   図 12: 例の `console.trace()` 結果  
:::image-end:::  

---  

## <a name="warn"></a>warn  

```javascript
console.warn(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Warning`  

コンソールに警告を出力します。  

```javascript
console.warn('warn');
```  

:::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn() の例の結果" lightbox="../media/console-demo-warn-button.msft.png":::
   図 13: 例の `console.warn()` 結果  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleLog]: /microsoft-edge/devtools-guide-chromium/console/log "コンソールでのログ メッセージの使用を開始する"  
[DevtoolConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "コンソール ユーティリティ API リファレンス"  
[DevtoolsConsoleReferenceClear]: /microsoft-edge/devtools-guide-chromium/console/reference#clear-the-console "コンソールのクリア - コンソール リファレンス"  
[DevtoolsConsoleReferencePersist]: /microsoft-edge/devtools-guide-chromium/console/reference#persist-messages-across-page-loads "ページ読み込み時にメッセージを保持する - コンソール リファレンス"  
[DevtoolsConsoleReferenceLevel]: /microsoft-edge/devtools-guide-chromium/console/reference#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (クロム) 開発者ツール"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/api) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
