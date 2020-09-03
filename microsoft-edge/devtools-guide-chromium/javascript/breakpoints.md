---
description: Microsoft Edge DevTools でコードを一時停止できるすべての方法について説明します。
title: Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 95aba99c2cfe87f26704faa20964ace5d2abdf51
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992810"
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







# Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法   



ブレークポイントを使用して JavaScript コードを一時停止します。  このガイドでは、DevTools で利用できる各種類のブレークポイントと、それぞれの種類の設定方法について説明します。  デバッグプロセスの実践的なチュートリアルについては、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevtoolsJavascriptIndex]」を参照してください。  

## 各ブレークポイントの種類を使用する状況の概要   

最もよく知られているブレークポイントの種類は、コード行です。  ただし、行コードのブレークポイントを設定するのは効率的ではありません。特に、正確な場所がわからない場合や、大規模なコードベースを使用している場合などが考えられます。  他の種類のブレークポイントを使用する方法とタイミングを理解することで、デバッグ時に時間を節約できます。  

| ブレークポイントの種類 | 一時停止するときに使用する...  |  
|:--- |:--- |  
| [行コード](#line-of-code-breakpoints) | コードの正確な領域。  |  
| [条件行コード](#conditional-line-of-code-breakpoints) | コードの正確な領域で、他の条件が true の場合にのみ表示されます。  |  
| [DOM](#dom-change-breakpoints) | 特定の DOM ノードまたは子を変更または削除するコード。  |  
| [XHR](#xhrfetch-breakpoints) | XHR URL に文字列パターンが含まれている場合。  |  
| [イベントリスナー](#event-listener-breakpoints) | イベント (、など) の後で実行されるコードの `click` 場合。  |  
| [エラー](#exception-breakpoints) | キャッチされた、またはキャッチされない例外をスローするコード行。  |  
| [機能](#function-breakpoints) | 特定のコマンド、関数、またはメソッドを実行するたび。  |  

## 行コードのブレークポイント   

調査が必要なコードの正確な領域がわかっている場合は、コード行のブレークポイントを使います。  このコード行が実行される前に、DevTools は常に一時停止します。  

DevTools で行コードのブレークポイントを設定するには、次の操作を行います。  

1.  [ **ソース** ] タブをクリックします。  
1.  改ページするコードの行が含まれているファイルを開きます。  
1.  コードの行に移動します。  
1.  コード行の左側には、[行番号列を入力します。  それをクリックします。  [行番号] 列の横に赤いアイコンが表示されます。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       行コードのブレークポイント  
    :::image-end:::  
    
### コードの行コードのブレークポイント   

コードからメソッドを実行して、 `debugger` その行にカーソルを置きます。  これは、コード内にブレーク [ポイント](#line-of-code-breakpoints)が設定されている点を除いて、コード内にブレークポイントが設定されていることを意味します。  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### 条件行コードのブレークポイント   

調査が必要なコードの正確な領域がわかっているが、その他の条件が true の場合にのみ一時停止する必要がある場合は、条件付きコードのブレークポイントを使用します。  

条件行コードのブレークポイントを設定するには、次の操作を行います。  

1.  [ **ソース** ] タブをクリックします。  
1.  改ページするコードの行が含まれているファイルを開きます。  
1.  コードの行に移動します。  
1.  コード行の左側には、[行番号列を入力します。  行番号を右クリックします。  
1.  [ **条件付きブレークポイントの追加**] を選択します。  ダイアログがコード行の下に表示されます。  
1.  ダイアログに条件を入力します。  
1.  を押して `Enter` 、ブレークポイントを有効にします。  [行番号] 列の横にあるアイコン。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件行コードのブレークポイント" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       条件行コードのブレークポイント  
    :::image-end:::  
    
### 行コードのブレークポイントを管理する   

[ **ブレークポイント** ] ウィンドウを使用して、1つの場所から行コードのブレークポイントを無効化または削除します。  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="[ブレークポイント] パネル" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   [ **ブレークポイント** ] パネル  
:::image-end:::  

*   エントリの横にあるチェックボックスをオンにして、そのブレークポイントを無効にします。  
*   エントリを右クリックして、そのブレークポイントを削除します。  
*   [ **ブレークポイント** ] ウィンドウ内の任意の場所を右クリックして、すべてのブレークポイントを非アクティブ化、すべてのブレークポイントの無効化、すべてのブレークポイントの削除を行います。  すべてのブレークポイントを無効にすることは、それぞれのチェックをオフにすることと同じです。  すべてのブレークポイントを非アクティブ化するには、すべてのコードのブレークポイントを無視するように DevTools を使用しますが、それぞれのブレークポイントを再アクティブ化するときと同じ状態になるように、有効な状態を維持する必要があります。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="[ブレークポイント] ウィンドウのブレークダウンの無効化" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       [ **ブレークポイント** ] ウィンドウのブレークダウンの無効化  
    :::image-end:::  
    
## DOM 変更のブレークポイント   

Dom ノードまたは子を変更するコードを一時停止する場合は、DOM 変更ブレークポイントを使用します。  

DOM 変更のブレークポイントを設定するには、次の操作を行います。  

1.  [ **要素** ] タブをクリックします。  
1.  ブレークポイントを設定する要素に移動します。  
1.  要素を右クリックします。  
1.  [ **中断] の上に**カーソルを合わせ、[ **サブツリーの変更**]、[属性の **変更**]、または [ **ノードの削除**] を選択します。  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="DOM 変更ブレークポイントを作成するためのコンテキストメニュー" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       DOM 変更ブレークポイントを作成するためのコンテキストメニュー  
    :::image-end:::  
    
### DOM の種類の変更ブレークポイント   

*   **サブツリーの変更**。  現在選択されているノードの子が削除または追加された場合、または子の内容が変更された場合にトリガーされます。  子ノードの属性の変更、または現在選択されているノードへの変更に対してトリガーされません。  
*   **属性の変更**: 現在選択されているノードの属性が追加または削除されたとき、または属性値が変更されたときにトリガーされます。  
*   **ノードの削除**: 現在選択されているノードが削除されたときに発生します。  
    
## XHR/Fetch のブレークポイント   

XHR の要求 URL に指定された文字列が含まれている場合に中断する場合は、XHR ブレークポイントを使います。  DevTools は、XHR がメソッドを実行しているコード行で一時停止し `send()` ます。  

> [!NOTE]
> この機能は、 [FETCH API][MDNFetchApi] 要求でも動作します。  

これが役に立つ場合の1つの例として、ページで正しくない URL が要求されていることがわかっていて、誤った要求を引き起こしている AJAX またはフェッチソースコードをすばやく見つける必要がある場合があります。  

XHR のブレークポイントを設定するには:  

1.  [ **ソース** ] タブをクリックします。  
1.  [ **Xhr のブレークポイント** ] ウィンドウを展開します。  
1.  [ **ブレークポイントの追加**] をクリックします。  
1.  改ページする文字列を入力します。  DevTools は、この文字列が XHR 要求 URL の任意の場所にある場合に一時停止します。  
1.  を押して `Enter` 確認します。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="XHR ブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       XHR ブレークポイントを作成する  
    :::image-end:::  
    
## イベントリスナーのブレークポイント 

イベントが発生した後に実行されるイベントリスナーコードで一時停止する場合は、イベントリスナーのブレークポイントを使用します。  [ `click` すべてのマウスイベント] などのイベントのカテゴリやカテゴリなどの特定のイベントを選ぶことができます。  

1.  [ **ソース** ] タブをクリックします。  
1.  [ **イベントリスナーのブレークポイント** ] ウィンドウを展開します。  [DevTools] は、 **アニメーション**などのイベントカテゴリの一覧を表示します。  
1.  いずれかのカテゴリをチェックして、そのカテゴリのイベントが発生したときに一時停止するか、カテゴリを展開して特定のイベントを確認します。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="イベントリスナーのブレークポイントを作成する" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       イベントリスナーのブレークポイントを作成する  
    :::image-end:::  
    
## 例外のブレークポイント   

キャッチまたはキャッチされない例外をスローするコード行で一時停止する場合は、例外のブレークポイントを使用します。  

1.  [ **ソース** ] タブをクリックします。  
1.  [ **例外時に一時停止] を** クリックします (例外がある場合は ![ 一時停止し ][ImagePauseOnExceptionsIcon] ます)。  有効にすると、アイコンが青色に変わります。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="[例外時に一時停止] ボタン" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       **[例外時に一時停止**] ボタン  
    :::image-end:::  
    
1.  **省略可能**。  キャッチされていない例外にも一時停止したい場合は、 **[キャッチした例外を一時停止** ] チェックボックスをオンにします。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="キャッチされていない例外で一時停止" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       キャッチされていない例外で一時停止  
    :::image-end:::  
    
## 関数のブレークポイント   

特定の `debug(method)` `method` 関数が実行されているときに一時停止する必要がある場合は、デバッグするコマンド、関数、またはメソッドを実行します。  `debug()`コード (ステートメントなど) に挿入し `console.log()` たり、Devtools コンソールからメソッドを実行したりすることができます。  `debug()` 関数の最初の行に [行コードのブレークポイント](#line-of-code-breakpoints) を設定することと同じです。  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### ターゲット関数が範囲内にあることを確認する   

DevTools は、 `ReferenceError` デバッグする関数がスコープ外であるかどうかをスローします。  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

DevTools コンソールからメソッドを実行している場合は、ターゲット関数がスコープ内にあることを確認するのが複雑になり `debug()` ます。  1つの戦略を次に示します。  

1.  関数がスコープ内のどこかにある [行コードのブレークポイント](#line-of-code-breakpoints) を設定します。
1.  ブレークポイントをトリガーします。  
1.  コード `debug()` が行のブレークポイントで一時停止されている状態で、DevTools コンソールでこのメソッドを実行します。  
    
<!---  
 


-->  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要 |Microsoft ドキュメント"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
