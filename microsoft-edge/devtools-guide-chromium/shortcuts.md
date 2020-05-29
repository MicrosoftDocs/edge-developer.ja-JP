---
title: Microsoft Edge DevTools のショートカットキー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 031457d33bf3cf102380c01d9084619313612124
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601895"
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
   limitations under the License. -->





# Microsoft Edge DevTools のショートカットキー   





このページでは、Microsoft Edge DevTools のキーボードショートカットのリファレンスを示します。

また、ヒントにショートカットを表示することもできます。 DevTools の UI 要素の上にマウスポインターを置くと、そのツールチップが表示します。 要素にショートカットが含まれている場合は、ヒントに表示されます。

## DevTools を開くためのキーボードショートカット   

DevTools を開くには、次のキーボードショートカットをクリックします。これは、カーソルがブラウザーのビューポートでフォーカスされているときです。

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| 最後に使用した任意のパネルを開く | `F12` /`Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| **コンソール**パネルを開く | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| [**要素**] パネルを開く | `Control`+`Shift`+`C` | `Command`+`Shift`+`C`/`Command`+`Option`+`C` |  

## グローバルキーボードショートカット   

次のショートカットキーは、ほとんどの場合、[すべて] ではなく、[DevTools] パネルで使用できます。

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| **設定**を表示する | `?` または `F1` | `?` /`Function`+`F1` |  
| 次のパネルにフォーカスを移動する | `Control`+`]` | `Command`+`]` |  
| 前のパネルにフォーカスを移動する | `Control`+`[` | `Command`+`[` |  
| 最後に使用した任意の[ドッキング位置][DevtoolsCustomizeIndexPlacement]に切り替えます。  DevTools がセッション全体の既定の位置に配置されている場合は、このショートカットは、別のウィンドウに DevTools をドッキング解除します。 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| [Devicemode][DevtoolsDeviceModeIndex]の切り替え | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| **要素の検査モード**の切り替え | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| [コマンドメニュー][DevtoolsCommandMenuIndex]を開く | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| [ドロワー][DevtoolsCustomizeIndexDrawer]の切り替え | `Escape` | `Escape` |  
| 通常の再読み込み | `F5` /`Control`+`R` | `Command`+`R` |  
| ハードリロード | `Control`+`F5`/`Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内でテキストを検索します。  **監査**、**アプリケーション**、**セキュリティ**の各パネルではサポートされません。 | `Control`+`F` | `Command`+`F` |  
| [引き出し][DevtoolsCustomizeIndexDrawer]で [**検索**] タブを開き、読み込まれたすべてのリソースのテキストを検索できるようにします。 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| [**ソース**] パネルでファイルを開く | `Control`+`O`/`Control`+`P` | `Command`+`O`/`Command`+`P` |  
| 拡大 | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Control`+`-` | `Command`+`-` |  
| 既定のズームレベルに戻す | `Control`+`0` | `Command`+`0` |  
| スニペットの実行 | キーを押して `Control` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「」と入力し、 `!` 次にスクリプトの名前を入力して、 `Enter` | キーを押して `Command` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「」と入力し、 `!` 次にスクリプトの名前を入力して、 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## 要素パネルのショートカットキー   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| 変更を元に戻す | `Control`+`Z` | `Command`+`Z` |  
| 変更のやり直し | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 現在選択されている要素の上または下の要素を選択する | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 現在選択されているノードを展開します。 ノードが既に展開されている場合、このショートカットはその下の要素を選びます。 | `Right Arrow` | `Right Arrow` |  
| 現在選択されているノードを折りたたみます。 ノードが既に折りたたまれている場合、このショートカットは上にある要素を選択します。 | `Left Arrow` | `Left Arrow` |  
| 現在選択されているノードとそのすべての子の展開または折りたたみ | を押しながら `Control` + `Alt` 、要素の名前の横にある矢印アイコンをクリックします。 | を押しながら `Option` 、要素の名前の横にある矢印アイコンをクリックします。 |  
| 現在選択されている要素の [**属性の編集**] モードを切り替えます。 | `Enter` | `Enter` |  
| **属性の編集**モードを開始した後に、次の属性または前の属性を選ぶ | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 現在選択されている要素を非表示にする | `H` | `H` |  
| 現在選択されている要素で [ **HTML モードとして編集**] をオンにする | `Function`+`F2` | `F2` |  

### スタイルウィンドウのショートカットキー   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| プロパティ値が宣言されている行に移動する | を押しながら `Control` プロパティの値をクリックする | を押しながら `Command` プロパティの値をクリックする |  
| RBGA、HSLA、色の値の16進表現の切り替え | を押しながら、 `Shift` 値の横にある [**色のプレビュー** ] ボックスをクリックします。 | を押しながら、 `Shift` 値の横にある [**色のプレビュー** ] ボックスをクリックします。 |  
| 次/前のプロパティまたは値を選択する | プロパティ名または値をクリックして、`Tab` / `Shift`+`Tab` | プロパティ名または値をクリックして、`Tab` / `Shift`+`Tab` |  
| プロパティ値を0.1 でインクリメントまたはデクリメントする | 値をクリックし、Alt キーを押しながら↑キーを押します。`Alt`+`Down Arrow` | 値をクリックして、 `Option` + `Up Arrow` /Option + 下方向キーを押します。 |  
| プロパティ値を1つずつインクリメントまたはデクリメントする | 値をクリックして、`Up Arrow` / `Down Arrow` | 値をクリックして、`Up Arrow` / `Down Arrow` |  
| プロパティ値を10ずつ増減する | 値をクリックして、`Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 値をクリックして、`Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| プロパティ値を100でインクリメントまたはデクリメントする | 値をクリックして、`Control`+`Up Arrow` / `Control`+`Down Arrow` | 値をクリックして、`Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## ソースパネルのショートカットキー   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| スクリプトランタイムの一時停止 (現在 \ を実行している場合) または再開 \ (現在一時停止している場合) | `F8` /`Control`+`\` | `F8` /`Command`+`\` |  
| Next 関数呼び出しのステップオーバー | `F10` /`Control`+`'` | `F10` /`Command`+`'` |  
| 次の関数呼び出しに進む | `F11` /`Control`+`;` | `F11` /`Command`+`;` |  
| 現在の関数のステップアウト | `Shift`+`F11`/`Control`+`Shift`+`;` | `Shift`+`F11`/`Command`+`Shift`+`;` |  
| [一時停止中に特定のコード行][DevtoolsJavascriptBreakpointsLOC]に進む | 押しながら `Control` コードの行をクリックする | 押しながら `Command` コードの行をクリックする |  
| 現在選択されているフレームの下または上にある通話フレームを選択します。 | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| ローカル変更の変更を保存する | `Control`+`S` | `Command`+`S` |  
| すべての変更を保存する | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 行へ移動 | `Control`+`G` | `Control`+`G` |  
| 現在開かれているファイルの行番号にジャンプする | キーを押して `Control` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「次に行番号を入力」と入力 `:` して、 `Enter` | キーを押して `Command` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「次に行番号を入力」と入力 `:` して、 `Enter` |  
| 現在開いているファイルの列にジャンプする \ (行5、列 9 \ など) | キーを押して、 `Control` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「」と入力し、行番号を入力してから、 `:` 別 `:` の列番号を入力して、enter キーを押します。 `Enter` | キーを押して、 `Command` + `O` [コマンドメニュー][DevtoolsCommandMenuIndex]を開き、「」と入力し、行番号を入力してから、 `:` 別 `:` の列番号を入力して、enter キーを押します。 `Enter` |  
| 関数宣言 \ (現在開いているファイルが HTML またはスクリプト \ の場合)、またはルールセット \ (現在開いているファイルがスタイルシートの場合) に移動します。 | を押し `Control` + `Shift` + `O` 、宣言/ルールセットの名前を入力するか、オプションの一覧から選択します。 | を押し `Command` + `Shift` + `O` 、宣言/ルールセットの名前を入力するか、オプションの一覧から選択します。 |  
| アクティブなタブを閉じる | `Alt`+`W` | `Option`+`W` |  

### コードエディターのショートカットキー   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| カーソルまでの最後の単語のすべての文字を削除する | `Control`+`Delete` | `Option`+`Delete` |  
| [行コードのブレークポイント][DevtoolsJavascriptBreakpointsLOC]を追加または削除する | カーソルを線の上に置き、enter キーを押します。`Control`+`B` | カーソルを線の上に置き、enter キーを押します。`Command`+`B` |  
| 対応するかっこに移動する | `Control`+`M` | `Control`+`M` |  
| 単一行のコメントを切り替えます。 複数の行が選択されている場合、DevTools は各行の先頭にコメントを追加します。 | `Control`+`/` | `Command`+`/` |  
| カーソルがある単語を選択または選択解除します。 各オカレンスが同時に強調表示される | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## パフォーマンスパネルのショートカットキー   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| 記録を開始/停止する | `Control`+`E` | `Command`+`E` |  
| レコーディングを保存する | `Control`+`S` | `Command`+`S` |  
| 読み込みの記録 | `Control`+`O` | `Command`+`O` |  

## メモリパネルのショートカットキー 

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| 記録を開始/停止する | `Control`+`E` | `Command`+`E` |  

## コンソールパネルのキーボードショートカット   

| 操作 | Windows | macOS |  
|:--- |:--- |:--- |  
| オートコンプリートの候補を承諾する | `Right Arrow` または `Tab` | `Right Arrow` または `Tab` |  
| オートコンプリートの候補を拒否する | `Escape` | `Escape` |  
| 前のステートメントを取得する | `Up Arrow` | `Up Arrow` |  
| 次のステートメントを取得する | `Down Arrow` | `Down Arrow` |  
| **コンソール**にフォーカスを移動する | `Control`+ `` ` `` | `Control`+`` ` `` |  
| **本体**をクリアする | `Control`+`L` | `Command`+`K`/`Option`+`L` |  
| 複数行の入力を強制します。 DevTools では、既定で複数行のシナリオを検出する必要があることに注意してください。このショートカットは通常、不要になりました。 | `Shift`+`Enter` | `Command`+`Return` |  
| 以下のコマンドを実行します。 | `Enter` | `Return` |  
| コンソールに記録されているオブジェクトのすべてのサブプロパティを展開する | 長押しして `Alt` から、[展開] をクリック**し**ます。 ![][ImageExpandIcon] | 長押しして `Alt` から、[展開] をクリック**し**ます。 ![][ImageExpandIcon] |  

 



<!-- image links -->  

[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "引き出し-Microsoft Edge DevTools のカスタマイズ"  
[DevtoolsCustomizeIndexPlacement]: /microsoft-edge/devtools-guide-chromium/customize/index#change-devtools-placement "DevTools の配置を変更する-Microsoft Edge DevTools をカスタマイズする"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする"  
[DevtoolsJavascriptBreakpointsLOC]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "行コードのブレークポイント-Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法"  

<!--[201705ReleaseNotesContinue]: whats-new/2017/05/devtools-release-notes#continue  -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/shortcuts)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
