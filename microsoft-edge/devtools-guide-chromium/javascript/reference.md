---
title: JavaScript デバッグ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 26f7272534e0834e0fb302a40b7f0ebfc817c88e
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982176"
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







# JavaScript デバッグリファレンス   



Microsoft Edge DevTools デバッグ機能の包括的なリファレンスで、新しいデバッグワークフローを見つけます。  

デバッグの基礎については、「 [Microsoft Edge DevTools のデバッグ JavaScript の概要][DevToolsJavascriptGetStarted] 」を参照してください。  

## ブレークポイントを使用したコードの一時停止   

ランタイムの途中でコードを一時停止できるようにブレークポイントを設定します。  

ブレークポイントを設定する方法については [、「ブレークポイントを使用したコードの一時停止][DevToolsJavascriptBreakpoints] 」をご覧ください。  

[DevToolsJavascriptBreakpoints]: breakpoints.md "Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法"  

## ステップ実行コード   

コードが一時停止されたら、1行ずつステップ実行し、制御フローとプロパティの値を調べます。  

### コード行のステップ   

デバッグしている問題に関連しない関数を含むコード行で一時停止している場合は、ステップ **オーバー** \ ( ![ ステップオーバー ][ImageStepOverIcon] \) アイコンをクリックすると、この関数が実行されることはありません。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="[ステップオーバー] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   [**ステップオーバー** ] を選ぶ  
:::image-end:::  

たとえば、次のコードをデバッグするとします。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

はに一時停止 `A` しています。  [ **ステップオーバー**] を押すことで、実行している関数のすべてのコードが実行され `B` `C` ます。  次に、DevTools で一時停止 `D` します。  

### コード行のステップ   

デバッグしている問題に関連する関数呼び出しを含むコード行で一時停止している場合は **、その** ![ 機能を詳しく調査するために、[\ (ステップイン ][ImageStepIntoIcon] )] アイコンをクリックします。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="[ステップイン] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   [**ステップイン**] を選ぶ  
:::image-end:::  

たとえば、次のコードをデバッグするとします。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

はに一時停止 `A` しています。  **ステップイン**を押すと、devtools はこのコード行を実行し、で一時停止し `B` ます。  

### コード行のステップアウト   

デバッグ中の問題に関連していない関数の内部で一時停止している場合は、[ **step out** ![ ] (ステップアウト) アイコンをクリックして ][ImageStepOutIcon] 、関数の残りのコードを実行します。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="[ステップアウト] を選ぶ" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   [**ステップアウト**] を選ぶ  
:::image-end:::  

たとえば、次のコードスニペットをデバッグするとします。  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

はに一時停止 `A` しています。  [ **ステップアウト**] を押すと、devtools で残りのコードが実行 `getName()` され `B` ます。これは、この例では次のように `C` なります。  

### 特定の行までのすべてのコードを実行する   

Long 関数をデバッグする場合、デバッグしている問題に関連していないコードが多数存在する可能性があります。  

すべての行の手順を実行することもできますが、面倒なこともあります。  目的の行に行コードのブレークポイントを設定し、[ **スクリプト実行の再開** ] ([スクリプト実行の再開]) アイコンをクリックすることもできますが、 ![ ][ImageResumeScriptExecutionIcon] もっと簡単な方法があります。  

目的のコード行を右クリックし、[ **続行**] を選択します。  DevTools では、その時点までのすべてのコードが実行され、その行が一時停止されます。  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="[続行] を選択する" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   [**続行**] を選択する  
:::image-end:::  

### コールスタックの top 関数を再起動する   

一時停止しているコード行で、[ **通話スタック** ] ウィンドウ内の任意の場所を右クリックし、[ **フレームの再起動** ] を選択して、呼び出し履歴の一番上の関数の1行目にカーソルを置きます。  Top 関数は、最後に実行された関数です。  

たとえば、次のコードスニペットをステップ実行しているとします。  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

はに一時停止 `A` しています。  [ **フレームの再起動**] をクリックした後、 `B` ブレークポイントを設定したり、[ **再開] スクリプト実行**を押したりしなくても、を一時停止しておく必要があります。  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="[フレームの再起動] を選ぶ" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   [**フレームの再起動**] を選ぶ  
:::image-end:::  

### スクリプトランタイムを再開する   

スクリプトを一時停止した後で実行を継続するには、[ **スクリプト実行の再開** ] ([ ![ スクリプト実行の再開 ][ImageResumeScriptExecutionIcon] ]) アイコンをクリックします。  DevTools は、次のブレークポイント (存在する場合) までスクリプトを実行します。  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="[スクリプト実行の再開] を選択する" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   [**スクリプト実行の再開**] を選択する  
:::image-end:::  

#### スクリプトの強制実行   

すべてのブレークポイントを無視してスクリプトを強制的に実行し続けるには、[**スクリプト実行の再開**] をクリックして、[スクリプト実行の強制実行] (スクリプト実行の強制) を ![ ][ImageResumeScriptExecutionIcon] 選び**Force script execution** ![ ][ImageForceScriptExecutionIcon] ます。  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="[スクリプト実行の強制] を選ぶ" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   [**スクリプト実行の強制**] を選ぶ  
:::image-end:::  

### スレッドコンテキストの変更   

Web ワーカーまたはサービスワーカーを操作するときに、[ **スレッド** ] ウィンドウに表示されているコンテキストをクリックして、そのコンテキストに切り替えます。  青い矢印のアイコンは、現在選択されているコンテキストを示します。  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="[スレッド] ウィンドウ" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   [ **スレッド** ] ウィンドウ  
:::image-end:::  

たとえば、メインスクリプトとサービスワーカースクリプトの両方のブレークポイントで一時停止しているとします。  サービスワーカーコンテキストのローカルプロパティとグローバルプロパティを表示する必要があるが、[ **ソース** ] パネルにはメインスクリプトコンテキストが表示されています。  [ **スレッド** ] ウィンドウで service worker エントリをクリックすると、そのコンテキストに切り替えることができるようになります。  

## ローカル、クロージャ、グローバルプロパティの表示と編集   

コード行で一時停止している間に、 **スコープ** ウィンドウを使って、ローカル、クロージャ、グローバルスコープのプロパティと変数の値を表示および編集します。  

*   プロパティ値をダブルクリックして変更します。  
*   列挙可能でないプロパティは灰色で表示されます。  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="スコープウィンドウ" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   **スコープ**ウィンドウ  
:::image-end:::  

## 現在の通話履歴を表示する   

一時停止しているコード行では、[ **通話スタック** ] ウィンドウを使って、この時点までの呼び出し履歴を表示できます。  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

エントリをクリックすると、その関数が呼び出されたコード行にジャンプします。  青色の矢印アイコンは、現在の DevTools が現在強調表示されている関数を示しています。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="[通話スタック] ウィンドウ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   [ **通話スタック** ] ウィンドウ  
:::image-end:::  

> [!NOTE]
> コード行で一時停止していない場合、[ **呼び出し履歴** ] ウィンドウは空です。  

### スタックトレースのコピー   

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

[ **通話スタック** ] ウィンドウ内の任意の場所を右クリックし、[ **スタックトレースのコピー** ] を選択して、現在の呼び出し履歴をクリップボードにコピーします。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="[スタックトレースのコピー] を選ぶ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   [**スタックトレースのコピー** ] を選ぶ  
:::image-end:::  

出力の例を次に示します。  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## スクリプトまたはスクリプトのパターンを無視する  

デバッグ中にそのスクリプトを無視する場合は、スクリプトをライブラリコードとしてマークします。  ライブラリコードとしてマークされている場合、スクリプトは [ **呼び出し履歴** ] ウィンドウで隠されており、コードのステップ実行時にスクリプトの関数にはステップインしません。  

たとえば、次のコードスニペットをステップ実行しているとします。  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` は、信頼できるサードパーティのライブラリです。  デバッグ中の問題がサードパーティのライブラリに関連していないことがわかっている場合は、スクリプトを **ライブラリコード**としてマークすることをお勧めします。  

### [エディター] ウィンドウからスクリプトをライブラリコードとしてマークする  

スクリプトを**エディター**ウィンドウから**ライブラリコード**としてマークするには、次の操作を行います。  

1.  ファイルを開きます。  
1.  任意の場所を右クリックします。  
1.  [ **Library code としてマーク**] を選択します。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="エディターウィンドウからスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       **エディター**ウィンドウからスクリプトを**ライブラリコード**としてマークする  
    :::image-end:::  
    
### [呼び出し履歴] ウィンドウからスクリプトをライブラリコードとしてマークする  

**呼び出し履歴**ウィンドウからスクリプトを**ライブラリコード**としてマークするには、次の操作を行います。  

1.  スクリプトから関数を右クリックします。  
1.  [ **Library code としてマーク**] を選択します。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="呼び出し履歴ウィンドウからスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       **呼び出し履歴**ウィンドウからスクリプトを**ライブラリコード**としてマークする  
    :::image-end:::  
    
### 設定からスクリプトをライブラリコードとしてマークする  

1つのスクリプトまたはスクリプトのパターンを設定からマークするには、次の操作を行います。  

1.  [ [設定][DevToolsCustomize]] を開きます。  
1.  [ **ライブラリコード** ] タブに移動します。  
1.  [ **パターンの追加**] をクリックします。  
1.  **ライブラリコード**としてマークするスクリプト名またはスクリプト名の regex パターンを入力します。  
1.  **[追加]** をクリックします。  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="設定からスクリプトをライブラリコードとしてマークする" lightbox="../media/javascript-framework-library-code.msft.png":::
       **設定**からスクリプトを**ライブラリコード**としてマークする  
    :::image-end:::  
    
## 任意のページからデバッグコードのスニペットを実行します。   

本体で同じデバッグコードを繰り返し実行していることがわかった場合は、スニペットを検討してください。  スニペットは、DevTools 内で作成、保存、実行するランタイムスクリプトです。  

詳細については [、「任意のページからコードのスニペットを実行][DevToolsJavascriptSnippets] する」を参照してください。  

## カスタム JavaScript 式の値を見る   

**ウォッチ**ウィンドウを使用して、カスタム式の値を確認します。  有効な JavaScript 式を見ることができます。  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="ウォッチウィンドウ" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   **ウォッチ**ウィンドウ  
:::image-end:::  

*   新しいウォッチ式を作成するには、 **式** \ ( ![ 式の追加) アイコンをクリックし ][ImageAddExpressionIcon] ます。  
*   **Refresh** ![ ][ImageRefreshIcon] すべての既存の式の値を更新するには、更新 \ (更新) アイコンをクリックします。  値は、コードをステップ実行して自動的に更新されます。  
*   式の上にマウスポインターを移動し、[ **式の削除** \ ( ![ 式の削除)] アイコンをクリックし ][ImageDeleteExpressionIcon] て削除します。  
    
## ファイルを読みやすくする   

[\] (書式 \) アイコンをクリックして、 **表示** している ![ ][ImageFormatIcon] ファイルを人間が読めるようにします。  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="[書式] ボタン" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   [ **書式** ] ボタン  
:::image-end:::  

## スクリプトを編集する   

バグを修正する場合、多くの場合、JavaScript コードに加えられた変更をいくつかテストする必要があります。  外部のエディターまたは IDE で変更を行ってから、ページを再読み込みする必要はありません。  作成したスクリプトは、DevTools で編集できます。  

スクリプトを編集するには:  

1.  [**ソース**] パネルの [**エディター** ] ウィンドウでファイルを開きます。  
1.  [ **エディター** ] ウィンドウで変更します。  
1.  `Ctrl` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。  DevTools は、JS ファイル全体を Microsoft Edge の JavaScript エンジンに更新します。  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="[エディター] ウィンドウ" lightbox="../media/javascript-sources-html-minified.msft.png":::
       [ **エディター** ] ウィンドウ  
    :::image-end:::  
     
## JavaScript を無効にする   

「 [Microsoft Edge DevTools で JavaScript を無効にする」を][DevToolsJavascriptDisable]参照してください。  

<!--## Feedback   -->  



<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptDisable]: ./disable.md "Microsoft Edge DevTools で JavaScript を無効にする |Microsoft ドキュメント"  
[DevToolsJavascriptGetStarted]: ./index.md "Microsoft Edge DevTools のデバッグ JavaScript の概要 |Microsoft ドキュメント"  
[DevToolsJavascriptSnippets]: ./snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。Microsoft ドキュメント"  
[DevToolsCustomize]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
