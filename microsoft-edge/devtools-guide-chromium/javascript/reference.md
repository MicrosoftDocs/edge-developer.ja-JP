---
description: Microsoft Edge DevTools デバッグ機能の包括的なリファレンスで、新しいデバッグ ワークフローについて説明します。
title: JavaScript デバッグ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2944e054a08a901d2e1752fa7c4e48ae110f5787
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439459"
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

# <a name="javascript-debugging-reference"></a>JavaScript デバッグ リファレンス  

Microsoft Edge DevTools デバッグ機能の包括的な参照を使用して、新しいデバッグ ワークフローを確認します。  

デバッグの基本については [、「Microsoft Edge DevTools][DevToolsJavascriptGetStarted]での JavaScript のデバッグの開始」に移動します。  

## <a name="pause-code-with-breakpoints"></a>ブレークポイントを使用してコードを一時停止する  

ブレークポイントを設定して、ランタイムの途中でコードを一時停止できます。  

ブレークポイントを設定する方法については、「ブレークポイントを使用してコード [を一時停止する」に移動します][DevToolsJavascriptBreakpoints]。  

## <a name="step-through-code"></a>コードのステップスルー  

コードを一時停止したら、一度に 1 行に 1 行の手順を実行し、その途中で制御フローとプロパティ値を調査します。  

### <a name="step-over-line-of-code"></a>一行のコードをステップ オーバーする  

デバッグ中の問題に関係のない関数を含むコード行で一時停止した場合は、[Step **over** \( ![ Step over \) ] ボタンを選択して、ステップ インせずに関数を実行します。 ](../media/step-over-icon.msft.png)  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="[ステップ オーバー] を選択する" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   [ステップ **オーバー] を選択する**  
:::image-end:::  

たとえば、次のコード スニペットをデバッグするとします。  

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

一時停止中です `A` 。  [ステップ オーバー **] を選択した**後、DevTools は、ステップ オーバーする関数内のすべてのコードを実行します。つまり `B` 、 `C` です。  DevTools は次に一時停止します `D` 。  

### <a name="step-into-line-of-code"></a>コード行へのステップ  

デバッグ中の問題に関連する関数呼び出しを含むコード行で一時停止した場合は、[\( Step **to** ![ \) ] ボタンを選択して、その関数をさらに調査します ](../media/step-into-icon.msft.png) 。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="[ステップ の実行] を選択します。" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   [ステップ **の実行] を選択します。**  
:::image-end:::  

たとえば、次のコード スニペットをデバッグするとします。  

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

一時停止中です `A` 。  [ステップ イン **] を選択すると**、DevTools はコード行を実行し、次に一時停止します `B` 。  

### <a name="step-out-of-line-of-code"></a>コード行からステップアウトする  

デバッグ中の問題に関連しない関数の内部で一時停止した場合は、[ステップ アウト] \( Step **out** \) ボタンを選択して、関数の残りのコードを ![ ](../media/step-out-icon.msft.png) 実行します。  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="[ステップ アウト] を選択する" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   [ステップ **アウト] を選択する**  
:::image-end:::  

たとえば、次のコード スニペットをデバッグするとします。  

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

一時停止中です `A` 。  [ステップ アウト **] を選択**すると、DevTools はコードの残りの部分を実行します 。これは、この例に示すだけで、次に `getName()` `B` 一時停止します `C` 。  

### <a name="run-all-code-up-to-a-specific-line"></a>特定の行まですべてのコードを実行する  

長い関数をデバッグする場合、デバッグ中の問題とは関係ないコードが多い場合があります。  

すべての行をステップスルーすることを選択できますが、これは時間のかかっています。  必要な行にコード行ブレークポイントを設定し、[スクリプト実行の再開 **\(** スクリプト実行の再開 ![ \)] ボタンを選択することもできますが、より高速な方法 ](../media/resume-script-run-icon.msft.png) があります。  

目的のコード行にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[続行] **をクリックします**。  DevTools は、その時点まですべてのコードを実行し、その行で一時停止します。  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="[次へ] を選択します。" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   [次 **へ] を選択します。**  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a>呼び出し履歴のトップ関数を再起動する  

呼び出し履歴内のトップ関数の最初の行で一時停止し、コード行で一時停止している間は、[通話履歴****] ウィンドウの任意の場所にマウス ポインターを移動し、コンテキスト**** メニュー \(右クリック\) を開き、[フレームの再起動] を選択します。  トップ関数は、最後に実行された関数です。  

次のコード スニペットは、手順を実行する例です。  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

一時停止中です `A` 。  [フレームの **再起動]** を選択した後は、ブレークポイントを設定したり、[スクリプトの実行の再開] を選択したりせずに、一 `B` **時停止する必要があります**。  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="[フレームの再起動] を選択する" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   [フレーム **の再起動] を選択する**  
:::image-end:::  

### <a name="resume-script-runtime"></a>スクリプト ランタイムの再開  

スクリプトの一時停止後にランタイムを続行するには、[スクリプトの実行の再開 \( Resume Script **Execution** ![ ](../media/resume-script-run-icon.msft.png) \) ] ボタンを選択します。  DevTools は、次のブレークポイントがある場合は、スクリプトを実行します。  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="[スクリプトの実行の再開] を選択します。" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   [スクリプト **の実行の再開] を選択します。**  
:::image-end:::  

#### <a name="force-script-runtime"></a>強制スクリプト ランタイム  

すべてのブレークポイントを無視してスクリプトの実行を強制的に再開するには、[スクリプトの実行を**再開する**]\( スクリプト実行の再開 \) ボタンを選択し、スクリプトの実行を強制する \( 強制スクリプト実行 ![ ](../media/resume-script-run-icon.msft.png) **** ![ ](../media/force-script-run-icon.msft.png) \) ボタンを選択します。  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="[スクリプトの実行を強制する] を選択する" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   [スクリプト **の実行を強制する] を選択する**  
:::image-end:::  

### <a name="change-thread-context"></a>スレッド コンテキストの変更  

Web ワーカーまたはサービス ワーカーを操作する場合は、[スレッド] ウィンドウに表示**** されているコンテキストを選択して、そのコンテキストに切り替えます。  青い矢印アイコンは、現在選択されているコンテキストを表します。  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="[スレッド] ウィンドウ" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   [ **スレッド]** ウィンドウ  
:::image-end:::  

たとえば、メイン スクリプトとサービス ワーカー スクリプトの両方のブレークポイントで一時停止したとします。  サービス ワーカー コンテキストのローカル プロパティとグローバル プロパティを表示する場合**** は、[ソース] パネルにメイン スクリプト コンテキストが表示されます。  [スレッド] ウィンドウでサービス ワーカー**** エントリを選択すると、そのコンテキストに切り替える必要があります。  

## <a name="view-and-edit-local-closure-and-global-properties"></a>ローカル、クロージャ、およびグローバル プロパティの表示と編集  

コード行で一時停止中に、[スコープ]**** ウィンドウを使用して、ローカル スコープ、クロージャ スコープ、およびグローバル スコープ内のプロパティと変数の値を表示および編集します。  

*   プロパティ値をダブルクリックして変更します。  
*   列挙できないプロパティは灰色で表示されます。  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   [ **スコープ]** ウィンドウ  
:::image-end:::  

## <a name="view-the-current-call-stack"></a>現在の呼び出し履歴を表示する  

コード行で一時停止中に、[呼び出**** し履歴] ウィンドウを使用して、この時点に移動した通話履歴を表示します。  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

その関数が呼び出されたコード行にジャンプするエントリを選択します。  青い矢印アイコンは、DevTools が現在強調表示している関数を表します。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="[通話履歴] ウィンドウ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   [ **通話履歴]** ウィンドウ  
:::image-end:::  

> [!NOTE]
> コード行で一時停止しない場合、[呼び出 **し履歴]** ウィンドウは空です。  

### <a name="copy-stack-trace"></a>スタック トレースのコピー  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

現在の呼び出し履歴をクリップボードにコピーするには、[通話履歴****] ウィンドウの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[スタック トレースのコピー] を**選択します**。  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="[スタック トレースのコピー] を選択する" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   [スタック **トレースのコピー] を選択する**  
:::image-end:::  

次のコード スニペットは、出力の例です。  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a>スクリプトまたはスクリプトのパターンを無視する  

デバッグ中にスクリプトを無視する場合は、スクリプトをライブラリ コードとしてマークします。  ライブラリ コードとしてマークされている場合、スクリプトは [呼び**** 出し履歴] ウィンドウで見えなされ、コードをステップ実行するときにスクリプトの機能にステップ インする必要はありません。  

次のコード スニペットは、手順を実行する例です。  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` は、信頼できるサード パーティ製のライブラリです。  デバッグ中の問題がサード パーティ製ライブラリに関連していないと確信している場合は、スクリプトをライブラリ コードとしてマークする方 **が理にかなっています**。  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a>エディター ウィンドウからスクリプトをライブラリ コードとしてマークする  

次のアクションを実行して、[エディター] ウィンドウから **スクリプトをライブラリ コード** として **マーク** します。  

1.  ファイルを開きます。  
1.  任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開きます。  
1.  [ **ライブラリ コードとしてマーク] を選択します**。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="エディター ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       エディター ウィンドウからスクリプト **をライブラリ コード** として **マーク** する  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a>[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする  

次のアクションを実行して、[呼び出し履歴] ウィンドウから **スクリプトをライブラリ** コード **としてマーク** します。  

1.  スクリプトから関数にカーソルを移動し、コンテキスト メニュー \(右クリック\) を開きます。  
1.  [ **ライブラリ コードとしてマーク] を選択します**。  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       [呼び出し履歴] **ウィンドウからスクリプトを** ライブラリ **コードとしてマーク** する  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a>設定からスクリプトをライブラリ コードとしてマークする  

設定からスクリプトの 1 つのスクリプトまたはパターンをマークするには、次のアクションを **実行します**。  

1.  [設定 [] を開きます][DevToolsCustomize]。  
1.  [ライブラリ コード **] 設定に移動** します。  
1.  [パターン **の追加] を選択します**。  
1.  ライブラリ コードとしてマークするスクリプト名またはスクリプト名の正規表現パターンを **入力します**。  
1.  **追加** を選びます。  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="設定からスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-framework-library-code.msft.png":::
       設定からスクリプトを **ライブラリ コードとして** マーク **する**  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a>任意のページからデバッグ コードのスニペットを実行する  

コンソールで同じデバッグ コードを実行している場合は、スニペットを検討してください。  スニペットは、DevTools 内で作成、保存、および実行するランタイム スクリプトです。  

詳細については、「任意のページから [コードのスニペットを実行する」に移動します][DevToolsJavascriptSnippets]。  

## <a name="watch-the-values-of-custom-javascript-expressions"></a>カスタム JavaScript 式の値を確認する  

[ウォッチ **] ウィンドウを** 使用して、カスタム式の値を確認します。  有効な JavaScript 式を確認できます。  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="[ウォッチ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   [ **ウォッチ]** ウィンドウ  
:::image-end:::  

*   [式 **の追加** \( Add Expression \) ] ボタンを ![ ](../media/add-expression-icon.msft.png) 選択して、新しいウォッチ式を作成します。  
*   [\( **Refresh** ![ ](../media/refresh-icon.msft.png) \) ] ボタンを選択して、既存のすべての式の値を更新します。  コードをステップ実行すると、値が自動的に更新されます。  
*   式にカーソルを合わせると、式の **削除** \( ![ 式 ](../media/delete-expression-icon.msft.png) の削除 \) ボタンを選択して削除します。  

## <a name="make-a-minified-file-readable"></a>ファイルを読み取り可能にする  

[Format **** \( Format \) ] ボタンを選択して、ファイルを人間が読み取り可能 ![ ](../media/format-icon.msft.png) にします。  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="[書式] ボタン" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   [ **書式]** ボタン  
:::image-end:::  

## <a name="edit-a-script"></a>スクリプトの編集  

バグを修正する場合は、JavaScript コードに対する変更をテストする必要が生じがちです。  外部エディターまたは IDE で変更を加え、ページを更新する必要はない。  DevTools でスクリプトを編集できます。  

スクリプトを編集するには、次のアクションを実行します。  

1.  [ソース] パネルの **[エディター** ] ウィンドウで **ファイルを開** きます。  
1.  [エディター] ウィンドウで変更 **を行** います。  
1.  `Ctrl` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して保存します。  DevTools は、JS ファイル全体を Microsoft Edge の JavaScript エンジンにパッチを適用します。  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="[エディター] ウィンドウ" lightbox="../media/javascript-sources-html-minified.msft.png":::
       [ **エディター]** ウィンドウ  
    :::image-end:::  
     
## <a name="disable-javascript"></a>JavaScript を無効にする  

[Microsoft Edge [DevTools を使用して JavaScript を無効にする] に移動します][DevToolsJavascriptDisable]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "Microsoft Edge DevTools を使用して JavaScript を無効|Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "Microsoft Edge DevTools の JavaScript のデバッグの|Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "Microsoft Edge DevTools を使用して任意のページで JavaScript のスニペットを実行|Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
