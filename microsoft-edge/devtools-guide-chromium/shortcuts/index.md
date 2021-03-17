---
description: Microsoft Edge DevTools キーボード ショートカットの標準ドキュメント。
title: Microsoft Edge DevTools キーボード ショートカット
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8197157c3024374e11db71f919cc937fed2e6b1b
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439592"
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

# <a name="microsoft-edge-devtools-keyboard-shortcuts"></a>Microsoft Edge DevTools キーボード ショートカット  

この記事は、Microsoft Edge DevTools のキーボード ショートカットのリファレンスです。

ヒントにショートカットが表示される場合があります。  DevTools の UI 要素にカーソルを合わせると、ツールヒントが表示されます。  要素にショートカットがある場合は、ツールヒントにショートカットが含まれます。

## <a name="keyboard-shortcuts-for-opening-devtools"></a>DevTools を開くキーボード ショートカット  

DevTools を開く場合は、カーソルがブラウザー ビューポートにフォーカスされている間に、次のキーボード ショートカットを選択します。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 最後に使用したパネルを開く | `F12` または `Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| コンソール ツール **を開** く | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 要素ツール **を開** く | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` または `Command`+`Option`+`C` |  

## <a name="global-keyboard-shortcuts"></a>グローバル キーボード ショートカット  

以下のキーボード ショートカットは、すべてではないにしろ、ほとんどの場合 DevTools パネルで使用できます。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 設定の **表示** | `?` or `F1` | `?` または `Function`+`F1` |  
| 次のパネルをフォーカスする | `Control`+`]` | `Command`+`]` |  
| 前のパネルをフォーカスする | `Control`+`[` | `Command`+`[` |  
| 最後に使用した [ドッキング位置に][DevtoolsCustomizeIndexPlacement] 戻ります。  DevTools がセッション全体の既定の位置にある場合、このショートカットは DevTools を別のウィンドウにドッキング解除します。 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| デバイス [エミュレーションの切り替え][DevtoolsDeviceModeIndex] | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 要素 **の検査モードの切り替え** | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| コマンド メニュー [を開く][DevtoolsCommandMenuIndex] | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| ドロワーを切り [替える][DevtoolsCustomizeIndexDrawer] | `Escape` | `Escape` |  
| 通常の更新 | `F5` または `Control`+`R` | `Command`+`R` |  
| ハード 更新 | `Control`+`F5` または `Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内のテキストを検索します。  監査、アプリケーション、**および**セキュリティ ツール******ではサポート**されていません | `Control`+`F` | `Command`+`F` |  
| ドロワー **で [検索** ] [タブを][DevtoolsCustomizeIndexDrawer]開き、読み込まれたすべてのリソースでテキストを検索できます。 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| [ソース] パネルで **ファイルを開** く | `Control`+`O` または `Control`+`P` | `Command`+`O` または `Command`+`P` |  
| 拡大する | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Control`+`-` | `Command`+`-` |  
| 既定のズーム レベルを復元する | `Control`+`0` | `Command`+`0` |  
| スニペットを実行する | [ `Control` + `O` コマンド] メニューを[開き、][DevtoolsCommandMenuIndex]次にスクリプトの名前を入力し、[次へ `!` ] を選択します。 `Enter` | [ `Command` + `O` コマンド] メニューを[開き、][DevtoolsCommandMenuIndex]次にスクリプトの名前を入力し、[次へ `!` ] を選択します。 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## <a name="elements-tool-keyboard-shortcuts"></a>要素ツールのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 変更の元に戻す | `Control`+`Z` | `Command`+`Z` |  
| やり直しの変更 | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 現在選択されている要素の上/下の要素を選択する | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 現在選択されているノードを展開します。  ノードが既に展開されている場合、このショートカットは、その下にある要素を選択します。 | `Right Arrow` | `Right Arrow` |  
| 現在選択されているノードを折りたたむ。  ノードが既に折りたたまれる場合、このショートカットは、その上にある要素を選択します。 | `Left Arrow` | `Left Arrow` |  
| 現在選択されているノードとすべての子を展開または折りたたむ | [ `Control` + `Alt` 保持] をクリックし、**要素**の名前の横にある矢印アイコンを選択します。 | [ `Option` 保持] をクリックし、 **要素** の名前の横にある矢印アイコンを選択します。 |  
| 現在選択 **されている要素の** [属性の編集] モードを切り替える | `Enter` | `Enter` |  
| 属性の編集モードに入った後で、次の/前 **の属性を選択** する | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 現在選択されている要素を非表示にする | `H` | `H` |  
| 現在選択 **されている要素の HTML** モードとして編集を切り替える | `Function`+`F2` | `F2` |  

### <a name="styles-panel-keyboard-shortcuts"></a>スタイル パネルのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| プロパティ値が宣言されている行に移動する | [保持 `Control` ] をクリックし、プロパティの値を選択します。 | [保持 `Command` ] をクリックし、プロパティの値を選択します。 |  
| 色の値の RBGA、HSLA、および 16 進表記を循環する | [ `Shift` 保持] をクリックし、値 **の横** にある [色のプレビュー] ボックスを選択します。 | [ `Shift` 保持] をクリックし、値 **の横** にある [色のプレビュー] ボックスを選択します。 |  
| 次の/前のプロパティまたは値を選択する | プロパティ名または値を選択してから、 `Tab` / `Shift`+`Tab` | プロパティ名または値を選択してから、 `Tab` / `Shift`+`Tab` |  
| プロパティ値を 0.1 ずつ増分/デクリメントする | 値を選択してから、 `Alt`+`Up Arrow` / `Alt`+`Down Arrow` | 値を選択し、[オプション] `Option` + `Up Arrow` + [下方向] の順に選択します。 |  
| プロパティ値を 1 ずつインクリメント/デクリメントする | 値を選択してから、 `Up Arrow` / `Down Arrow` | 値を選択してから、 `Up Arrow` / `Down Arrow` |  
| プロパティ値を 10 ずつインクリメント/デクリメントする | 値を選択してから、 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 値を選択してから、 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| プロパティ値を 100 ずつ増分/デクリメントする | 値を選択してから、 `Control`+`Up Arrow` / `Control`+`Down Arrow` | 値を選択してから、 `Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## <a name="sources-tool-keyboard-shortcuts"></a>ソース ツールのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| スクリプト ランタイムを一時停止する \(現在実行中の場合\) または resume \(現在一時停止している場合\) | `F8` または `Control`+`\` | `F8` または `Command`+`\` |  
| 次の関数呼び出しのステップ オーバー | `F10` または `Control`+`'` | `F10` または `Command`+`'` |  
| 次の関数呼び出しへのステップ | `F11` または `Control`+`;` | `F11` または `Command`+`;` |  
| 現在の関数からステップ アウトする | `Shift`+`F11` または `Control`+`Shift`+`;` | `Shift`+`F11` または `Command`+`Shift`+`;` |  
| 一時停止中 [に特定のコード行に進む][DevtoolsJavascriptBreakpointsLOC] | [保持 `Control` ] をクリックし、コード行を選択します。 | [保持 `Command` ] をクリックし、コード行を選択します。 |  
| 現在選択されているフレームの下/上の通話フレームを選択する | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| ローカル変更への変更を保存する | `Control`+`S` | `Command`+`S` |  
| すべての変更を保存する | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 行に移動する | `Control`+`G` | `Control`+`G` |  
| 現在開いているファイルの行番号にジャンプする | [ `Control` + `O` 選択] をクリックして[コマンド メニュー][DevtoolsCommandMenuIndex]を開き、次に行番号 `:` を入力してから、 `Enter` | [ `Command` + `O` 選択] をクリックして[コマンド メニュー][DevtoolsCommandMenuIndex]を開き、次に行番号 `:` を入力してから、 `Enter` |  
| 現在開いているファイル \(たとえば、行 5、列 9\) の列にジャンプします。 | [コマンド] メニューを開き、次に行番号を開き、次に別の行番号を選択し、次に列 `Control` + `O` [][DevtoolsCommandMenuIndex] `:` `:` 番号を選択します。 `Enter` | [コマンド] メニューを開き、次に行番号を開き、次に別の行番号を選択し、次に列 `Command` + `O` [][DevtoolsCommandMenuIndex] `:` `:` 番号を選択します。 `Enter` |  
| 現在のファイルが HTML またはスクリプトの場合は、関数宣言に移動します。  <br />  現在のファイルがスタイルシートの場合は、ルール セットに移動します。  | を `Control` + `Shift` + 選択し、宣言/ルール セットの名前を入力するか、オプションの一覧 `O` から選択します。 | を `Command` + `Shift` + 選択し、宣言/ルール セットの名前を入力するか、オプションの一覧 `O` から選択します。 |  
| アクティブなタブを閉じる | `Alt`+`W` | `Option`+`W` |  

### <a name="code-editor-keyboard-shortcuts"></a>コード エディターのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| カーソルまで、最後の単語のすべての文字を削除する | `Control`+`Delete` | `Option`+`Delete` |  
| コード行ブレークポイント [を追加または削除する][DevtoolsJavascriptBreakpointsLOC] | カーソルを行にフォーカスしてから、 `Control`+`B` | カーソルを行にフォーカスしてから、 `Command`+`B` |  
| 一致するかっこに移動する | `Control`+`M` | `Control`+`M` |  
| 1 行のコメントを切り替える。  複数行が選択されている場合、DevTools は各行の開始にコメントを追加します。 | `Control`+`/` | `Command`+`/` |  
| カーソルがオンの単語の次の出現をオンまたはオフにします。  各オカレンスが同時に強調表示されます | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## <a name="performance-tool-keyboard-shortcuts"></a>パフォーマンス ツールのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 録音の開始/停止 | `Control`+`E` | `Command`+`E` |  
| 記録の保存 | `Control`+`S` | `Command`+`S` |  
| 記録の読み込み | `Control`+`O` | `Command`+`O` |  

## <a name="memory-tool-keyboard-shortcuts"></a>メモリ ツールのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 録音の開始/停止 | `Control`+`E` | `Command`+`E` |  

## <a name="console-tool-keyboard-shortcuts"></a>コンソール ツールのキーボード ショートカット  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| オートコンプリートの提案を受け入れる | `Right Arrow` or `Tab` | `Right Arrow` or `Tab` |  
| オートコンプリートの提案を拒否する | `Escape` | `Escape` |  
| 前のステートメントを取得する | `Up Arrow` | `Up Arrow` |  
| Get next ステートメント | `Down Arrow` | `Down Arrow` |  
| コンソールの **フォーカス** | `Control`+ `` ` `` | `Control`+`` ` `` |  
| コンソールをクリア **する** | `Control`+`L` | `Command`+`K` または `Option`+`L` |  
| 複数行のエントリを強制的に指定します。  DevTools は既定で複数行のシナリオを検出する必要があるため、このショートカットはほとんどの場合不要です。 | `Shift`+`Enter` | `Command`+`Return` |  
| 以下のコマンドを実行します。 | `Enter` | `Return` |  
| コンソールにログに記録されるオブジェクトのすべてのサブプロパティを展開する | [保持 `Alt` ]**** をクリックし、[展開\( ![ Expand ](../media/expand-icon.msft.png) \) | [保持 `Alt` ]**** をクリックし、[展開\( ![ Expand ](../media/expand-icon.msft.png) \) |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexPlacement]: ../customize/index.md#change-devtools-placement "DevTools の配置を変更する - Microsoft Edge DevTools の配置を|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLOC]: ../javascript/breakpoints.md#line-of-code-breakpoints "コード行ブレークポイント - Microsoft Edge DevTools アプリケーションでブレークポイントを使用してコードを一時停止する|Microsoft Docs"  

<!--[201705ReleaseNotesContinue]: whats-new/2017/05/devtools-release-notes#continue  -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/shortcuts) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  