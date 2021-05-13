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
# <a name="console-api-reference"></a>コンソール API リファレンス  

コンソール **ツール** は、DevTools で複数のタスクを完了するときに役立ちます。  API は、スクリプトに含める場合に使用できます。 便利なメソッドは、コンソール ツール (and **メソッドなど** ) `debug()` でのみ `monitorEvents()` 使用できます。  コンソールの使用を開始する方法の詳細 **については、「コンソール**へのメッセージのログ記録の開始 [」に移動します][DevtoolsConsoleConsoleLog]。  コンソールの便利なメソッドの詳細については、「 **コンソール**ユーティリティ [API リファレンス」に移動します][DevtoolConsoleUtilities]。  

---  

## <a name="assert"></a>assert  

このメソッドは、評価[時に](#error)**コンソール**に `expression` エラーを書き込みます `false` 。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.assert(expression, object)
```

[ログ レベル][DevtoolsConsoleReferencePersist]: `Error`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-assert-button.msft.png" alt-text="console.assert() の例の結果" lightbox="../media/console-demo-assert-button.msft.png":::
         例の `console.assert()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="clear"></a>clear  

このメソッドは、コンソールをクリア **します**。  

[ [ログの保持]][DevtoolsConsoleReferenceFilter] がオンの場合 [、clear](#clear) メソッドはオフになります。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.clear()
```

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.clear();  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

### <a name="see-also"></a>関連項目  

*   [コンソールをクリアする][DevtoolsConsoleReferenceClear]  

---  

## <a name="count"></a>count  

このメソッドは、count メソッドが同[](#count)じ行で呼び出された回数を同じ行で書き込みます `label` 。  [countReset メソッドを使用して](#countreset)、カウントをリセットします。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.count([label])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-count-button.msft.png" alt-text="console.count() の例の結果" lightbox="../media/console-demo-count-button.msft.png":::
         例の `console.count()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="countreset"></a>countReset  

このメソッドは、カウントをリセットします。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.countReset([label])
```  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      
   :::column-end:::
:::row-end:::  

---  

## <a name="debug"></a>デバッグ  

このメソッドは、異なるログ レベルを [除き、log](#log) メソッドと同じです。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.debug(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Verbose`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.debug('debug');  
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-debug-button.msft.png" alt-text="console.debug() の例の結果" lightbox="../media/console-demo-debug-button.msft.png":::
         例の `console.debug()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dir"></a>dir  

このメソッドは、指定したオブジェクトの JSON 表記を出力します。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.dir(object)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dir(document.head);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dir-button.msft.png" alt-text="console.dir() の例の結果" lightbox="../media/console-demo-dir-button.msft.png":::
         例の `console.dir()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="dirxml"></a>dirxml  

このメソッドは、 の子孫の XML 表現を出力します `node` 。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.dirxml(node)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.dirxml(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-dirxml-button.msft.png" alt-text="console.dirxml() の例の結果" lightbox="../media/console-demo-dirxml-button.msft.png":::
         例の `console.dirxml()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="error"></a>error (エラー)  

このメソッドは、コンソール `object` に出力**** され、エラーとして書式設定され、スタック トレースが含まれます。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.error(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Error`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.error("I'm sorry, Dave.  I'm afraid I can't do that.");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-error-button.msft.png" alt-text="console.error() の例の結果" lightbox="../media/console-demo-error-button.msft.png":::
         例の `console.error()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="group"></a>グループ  

このメソッドは [、groupEnd](#groupend) メソッドが使用されるまで、メッセージを視覚的にグループ化します。  [groupCollapsed メソッドを使用](#groupcollapsed)して、コンソールに最初にログを記録するときにグループを折りたたみ**します**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.group(label)
```  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-group-button.msft.png" alt-text="console.group() の例の結果" lightbox="../media/console-demo-group-button.msft.png":::
         例の `console.group()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="groupcollapsed"></a>groupCollapsed  

このメソッドは log [メソッドと同](#log) じですが、コンソールにログを記録するときにグループが最初に折りたたまれる場合を除 **きます**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.groupCollapsed(label)
```  

---  

## <a name="groupend"></a>groupEnd  

このメソッドは、メッセージの視覚的なグループ化を停止します。  group メソッドに [移動](#group) します。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.groupEnd(label)
```  

---  

## <a name="info"></a>情報  

このメソッドは log メソッドと [同](#log) じです。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.info(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.info('info');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-info-button.msft.png" alt-text="console.info() の例の結果" lightbox="../media/console-demo-info-button.msft.png":::
         例の `console.info()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="log"></a>log  

このメソッドは、コンソールにメッセージを出力 **します**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.log(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.log('log');
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-log-button.msft.png" alt-text="console.log() の例の結果" lightbox="../media/console-demo-log-button.msft.png":::
         例の `console.log()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="table"></a>table  

このメソッドは、オブジェクトの配列をテーブルとしてログに記録します。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.table(array)
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-table-button.msft.png" alt-text="console.table() の例の結果" lightbox="../media/console-demo-table-button.msft.png":::
         例の `console.table()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="time"></a>time  

このメソッドは、新しいタイマーを開始します。  [timeEnd メソッドを使用](#timeend)してタイマーを停止し、経過時間をコンソールに出力**します**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.time([label])
```  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-time-button.msft.png" alt-text="console.time() の例の結果" lightbox="../media/console-demo-time-button.msft.png":::
         例の `console.time()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="timeend"></a>timeEnd  

このメソッドはタイマーを停止します。  詳細については、time メソッドに [移動](#time) します。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.timeEnd([label])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

---  

## <a name="trace"></a>trace  

このメソッドは、スタック トレースをコンソールに出力 **します**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.trace()
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Info`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
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
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-trace-button.msft.png" alt-text="console.trace() の例の結果" lightbox="../media/console-demo-trace-button.msft.png":::
         例の `console.trace()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="warn"></a>warn  

このメソッドは、コンソールに警告を出力 **します**。  

### <a name="javascript-syntax"></a>JavaScript 構文  

```javascript
console.warn(object [, object, ...])
```  

[ログ レベル][DevtoolsConsoleReferencePersist]: `Warning`  

### <a name="javascript-example"></a>JavaScript の例  

:::row:::
   :::column span="1":::
      入力  
   :::column-end:::
   :::column span="3":::
      ```javascript
      console.warn('warn');
      ```
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      出力
   :::column-end:::
   :::column span="3":::
      :::image type="complex" source="../media/console-demo-warn-button.msft.png" alt-text="console.warn() の例の結果" lightbox="../media/console-demo-warn-button.msft.png":::
         例の `console.warn()` 結果  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

---  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleConsoleLog]: ./console-log.md "コンソール ツール にログイン|Microsoft Docs"  
[DevtoolConsoleUtilities]: ./utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleReferenceClear]: ./reference.md#clear-the-console "[コンソール ] - [コンソール] リファレンス をクリア|Microsoft Docs"  
[DevtoolsConsoleReferenceFilter]: ./reference.md#filter-by-log-level "ログ レベルによるフィルター - コンソール リファレンス | Microsoft Docs"  
[DevtoolsConsoleReferencePersist]: ./reference.md#persist-messages-across-page-loads "ページの読み込み時にメッセージを保持する - コンソール参照|Microsoft Docs"  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツールの概要 |Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/api) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
