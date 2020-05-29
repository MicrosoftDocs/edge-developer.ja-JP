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





# 本体の API リファレンス   

  

コンソール API メソッドを使って、JavaScript からコンソールにメッセージを書き込みます。  トピックの対話的な紹介については、「[コンソールにメッセージを記録][DevtoolsConsoleLog]する」を参照してください。  便宜上[Console Utilities API Reference] [DevtoolConsoleUtilities] 、 `debug()` または `monitorEvents()` 本体だけで利用できる便利なメソッドを探している場合は、「コンソールユーティリティ API リファレンス」をご覧ください。  

## assert  

```javascript
console.assert(expression, object)
```

[ログレベル][DevtoolsConsoleReferencePersist]: `Error`  

<!--todo: add reference level (reference#persist-messages-across-page-loads) when available -->  

評価されたときに、本体に[エラー](#error)を書き込み `expression` `false` ます。  

```javascript
const x = 5;
const y = 3;
const reason = 'x is expected to be less than y';
console.assert(x < y, {x, y, reason});
```  

> ##### 図 1  
> この例の結果 `console.assert()`  
> ![本体の assert () の結果][ImageAssert]  

## clear  

```javascript
console.clear()
```

本体をクリアします。  

```javascript
console.clear();  
```  

[[ログの保持][DevtoolsConsoleReferenceLevel]] が有効になっている場合、 [clear](#clear)メソッドは無効になります。  

関連項目:[本体をクリアする][DevtoolsConsoleReferenceClear]  

## 枚数  

```javascript
console.count([label])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

[Count](#count)メソッドが同じ行で呼び出され、同じ行にある回数を書き込み `label` ます。  [Countreset](#countreset)メソッドを使用して、カウントをリセットします。  

```javascript
console.count();
console.count('coffee');
console.count();
console.count();
```  

> ##### 図 2  
> この例の結果 `console.count()`  
> ![Console count () の例の結果][ImageCount]  

## countReset  

```javascript
console.countReset([label])
```  

カウントをリセットします。  

```javascript
console.countReset();
console.countReset('coffee');
```  

## デバッグ  

```javascript
console.debug(object [, object, ...])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

[Log](#log)メソッドと同じです。  

```javascript
console.debug('debug');  
```  

> ##### 図 3  
> この例の結果 `console.debug()`  
> ![Xbox の debug () の例][ImageDebug]  

## dir  

```javascript
console.dir(object)
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

指定したオブジェクトの JSON 表現を出力します。  

```javascript
console.dir(document.head);
```  

> ##### 図 4  
> この例の結果 `console.dir()`  
> ![Console () の例の結果][ImageDir]  

## dirxml  

```javascript
console.dirxml(node)
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

の子の XML 表現を出力 `node` します。  

```javascript
console.dirxml(document);
```  

> ##### 図 5  
> この例の結果 `console.dirxml()`  
> ![コンソールの dirxml () 例の結果][ImageDirXml]  

## error (エラー)  

```javascript
console.error(object [, object, ...])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Error`  

`object`コンソールにを出力し、エラーとして書式設定し、スタックトレースを含めます。  

```javascript
console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
```  

> ##### 図 6  
> この例の結果 `console.error()`  
> ![本体の結果。エラー () の例][ImageError]  

## グループ  

```javascript
console.group(label)
```  

[Groupend](#groupend)メソッドが使われるまで、メッセージを視覚的にグループ化します。  グループが最初にコンソールにログインしたときに、グループを折りたたむには、 [Groupcollapsed](#groupcollapsed)れたメソッドを使います。  

```javascript
const label = 'Adolescent Irradiated Espionage Tortoises';
console.group(label);
console.info('Leo');
console.info('Mike');
console.info('Don');
console.info('Raph');
console.groupEnd(label);
```  

> ##### 図 7  
> この例の結果 `console.group()`  
> ![Console の結果。 group () の例][ImageGroup]  

## groupCollapsed れている  

```javascript
console.groupCollapsed(label)
```  

[Log](#log)メソッドと同じですが、グループをコンソールに記録したときに最初に折りたたまれている場合を除きます。  

## groupEnd  

```javascript
console.groupEnd(label)
```  

視覚的にメッセージをグループ化することを停止します。  [グループ](#group)のメソッドをご覧ください。  

## 情報  

```javascript
console.info(object [, object, ...])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

[Log](#log)メソッドと同じです。  

```javascript
console.info('info');
```  

> ##### 図 8  
> この例の結果 `console.info()`  
> ![Console.info () 例の結果][ImageInfo]  

## 出力  

```javascript
console.log(object [, object, ...])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

コンソールにメッセージを出力します。  

```javascript
console.log('log');
```  

> ##### 図 9  
> この例の結果 `console.log()`  
> ![Console .log () の例の結果][ImageLog]  

## '95'5c  

```javascript
console.table(array)
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

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

> ##### 図 10  
> この例の結果 `console.table()`  
> ![本体の結果 () 例][ImageTable]  

## time  

```javascript
console.time([label])
```  

新しいタイマーを開始します。  [Timeend](#timeend)メソッドを使ってタイマーを停止し、経過時間を本体に出力します。  

```javascript
console.time();
for (var i = 0; i < 100000; i++) {
    let square = i ** 2;
}
console.timeEnd();
```  

> ##### 図 11  
> この例の結果 `console.time()`  
> ![Console の結果。 time () の例][ImageTime]  

## timeEnd  

```javascript
console.timeEnd([label])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

タイマーを停止します。  [Time](#time)メソッドを参照してください。  

## trace  

```javascript
console.trace()
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Info`  

スタックトレースを本体に出力します。  

```javascript
const first = () => { second(); };
const second = () => { third(); };
const third = () => { fourth(); };
const fourth = () => { console.trace(); };
first();
```  

> ##### 図 12  
> この例の結果 `console.trace()`  
> ![本体のトレースの結果 () 例][ImageTrace]  

## warn  

```javascript
console.warn(object [, object, ...])
```  

[ログレベル][DevtoolsConsoleReferencePersist]: `Warning`  

コンソールに警告を出力します。  

```javascript
console.warn('warn');
```  

> ##### 図 13  
> この例の結果 `console.warn()`  
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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/console/api)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
