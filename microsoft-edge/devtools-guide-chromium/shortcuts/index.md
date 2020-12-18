---
description: Microsoft Edge DevTools キーボード ショートカットの標準ドキュメント。
title: Microsoft Edge DevTools のキーボード ショートカット
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 417e2235e4ea63d0258c158035ea201cd5657099
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234372"
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

# Microsoft Edge DevTools のキーボード ショートカット  

この記事は、Microsoft Edge DevTools のキーボード ショートカットのリファレンスです。

また、ヒントにショートカットを表示できます。  DevTools の UI 要素にカーソルを合わせると、ヒントが表示されます。  要素にショートカットがある場合は、ヒントにショートカットが含まれます。

## DevTools を開くキーボード ショートカット  

DevTools を開く場合は、カーソルがブラウザーのビューポートにフォーカスされている間に、次のキーボード ショートカットを選択します。

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 最後に使用したパネルを開く | `F12` または `Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| コンソール パネル **を開** く | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 要素パネル **を開** く | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` または `Command`+`Option`+`C` |  

## グローバル キーボード ショートカット  

次のキーボード ショートカットは、すべてではないにしろ、ほとんどの DevTools パネルで利用できます。

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 設定の **表示** | `?` または `F1` | `?` または `Function`+`F1` |  
| 次のパネルにフォーカスを移動する | `Control`+`]` | `Command`+`]` |  
| 前のパネルにフォーカスを移動する | `Control`+`[` | `Command`+`[` |  
| 最後に使用した [ドッキング位置に][DevtoolsCustomizeIndexPlacement] 戻ります。  DevTools がセッション全体の既定の位置にある場合、このショートカットは DevTools を別のウィンドウにドッキング解除します。 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| デバイス エミュレーション [の切り替え][DevtoolsDeviceModeIndex] | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 要素モード **の検査の切り替え** | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| コマンド メニュー [を開く][DevtoolsCommandMenuIndex] | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| ドロワーを切り [替える][DevtoolsCustomizeIndexDrawer] | `Escape` | `Escape` |  
| 通常の再読み込み | `F5` または `Control`+`R` | `Command`+`R` |  
| ハード 再読み込み | `Control`+`F5` または `Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 現在のパネル内のテキストを検索します。  監査パネル、アプリケーション パネル **、およびセキュリティ**パネル**ではサポート**されていません**** | `Control`+`F` | `Command`+`F` |  
| ドロワー **の [検索** ] [タブを開][DevtoolsCustomizeIndexDrawer]きます。これにより、読み込まれたすべてのリソースのテキストを検索できます。 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| [ソース] パネルで **ファイルを開** く | `Control`+`O` または `Control`+`P` | `Command`+`O` または `Command`+`P` |  
| 拡大する | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 縮小 | `Control`+`-` | `Command`+`-` |  
| 既定のズーム レベルを復元する | `Control`+`0` | `Command`+`0` |  
| スニペットを実行する | Select `Control` + `O` キーを押して[コマンド メニューを][DevtoolsCommandMenuIndex]開き、その後にスクリプトの `!` 名前を入力して、 `Enter` | Select `Command` + `O` キーを押して[コマンド メニューを][DevtoolsCommandMenuIndex]開き、その後にスクリプト `!` の名前を入力して、 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## 要素パネルのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 変更を元に戻す | `Control`+`Z` | `Command`+`Z` |  
| 変更をやり直す | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 現在選択されている要素の上/下の要素を選択する | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 現在選択されているノードを展開します。  ノードが既に展開されている場合、このショートカットはノードの下の要素を選択します。 | `Right Arrow` | `Right Arrow` |  
| 現在選択されているノードを折りたたむ。  ノードが既に折りたたまれる場合、このショートカットは上の要素を選択します。 | `Left Arrow` | `Left Arrow` |  
| 現在選択されているノードとすべての子ノードを展開または折りたたむ | [保持 `Control` + `Alt` ] をクリックし、要素**の**名前の横にある矢印アイコンを選択します。 | [保持 `Option` ] をクリックし、要素 **の** 名前の横にある矢印アイコンを選択します。 |  
| 現在 **選択されている要素で** 属性の編集モードを切り替える | `Enter` | `Enter` |  
| 属性の編集モードに入った後、次 **の属性または前の属性を選択** する | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 現在選択されている要素を非表示にする | `H` | `H` |  
| 現在 **選択されている要素で [編集] を HTML** モードに切り替える | `Function`+`F2` | `F2` |  

### スタイル ウィンドウのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| プロパティ値が宣言されている行に移動します。 | [保持 `Control` ] をクリックし、プロパティ値を選択します。 | [保持 `Command` ] をクリックし、プロパティ値を選択します。 |  
| 色の値の RBGA、HSLA、および 16 進表現を繰り返す | [保留 `Shift` ] をクリックし、値 **の** 横にある [色のプレビュー] ボックスを選択します。 | [保留 `Shift` ] をクリックし、値 **の** 横にある [色のプレビュー] ボックスを選択します。 |  
| 次または前のプロパティまたは値を選択する | プロパティの名前または値を選択し、 `Tab` / `Shift`+`Tab` | プロパティの名前または値を選択し、 `Tab` / `Shift`+`Tab` |  
| プロパティ値を 0.1 ずつインクリメントまたはデクリメントする | 値を選択し、 `Alt`+`Up Arrow` / `Alt`+`Down Arrow` | 値を選択し、/ `Option` + `Up Arrow` オプション + 下矢印を選択します。 |  
| プロパティ値を 1 ずつインクリメント/デクリメントする | 値を選択し、 `Up Arrow` / `Down Arrow` | 値を選択し、 `Up Arrow` / `Down Arrow` |  
| プロパティ値を 10 ずつインクリメントまたはデクリメントする | 値を選択し、 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 値を選択し、 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| プロパティ値を 100 ずつインクリメントまたはデクリメントする | 値を選択し、 `Control`+`Up Arrow` / `Control`+`Down Arrow` | 値を選択し、 `Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## ソース パネルのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| スクリプト ランタイム \(現在実行中の場合\) または再開 \(現在一時停止している場合\) を一時停止します。 | `F8` または `Control`+`\` | `F8` または `Command`+`\` |  
| 次の関数呼び出しのステップ オーバー | `F10` または `Control`+`'` | `F10` または `Command`+`'` |  
| 次の関数呼び出しにステップ する | `F11` または `Control`+`;` | `F11` または `Command`+`;` |  
| 現在の関数からステップ アウトする | `Shift`+`F11` または `Control`+`Shift`+`;` | `Shift`+`F11` または `Command`+`Shift`+`;` |  
| 一時停止中 [に特定のコード行に進む][DevtoolsJavascriptBreakpointsLOC] | [保留 `Control` ] をクリックし、コード行を選択します。 | [保留 `Command` ] をクリックし、コード行を選択します。 |  
| 現在選択されているフレームの下/上の通話フレームを選択する | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| ローカルの変更に対する変更を保存する | `Control`+`S` | `Command`+`S` |  
| すべての変更を保存する | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 行に移動する | `Control`+`G` | `Control`+`G` |  
| 現在開いているファイルの行番号にジャンプする | Select `Control` + `O` キーを押して[コマンド メニューを][DevtoolsCommandMenuIndex]開き、その `:` 後に行番号を入力して、 `Enter` | Select `Command` + `O` キーを押して[コマンド メニューを][DevtoolsCommandMenuIndex]開き、その `:` 後に行番号を入力して、 `Enter` |  
| 現在開いているファイルの列にジャンプします (例: 行 5、列 9\) | Select `Control` + `O` to open the [Command Menu,][DevtoolsCommandMenuIndex] `:` type, then the line number, then `:` another, then the column number, then select `Enter` | Select `Command` + `O` to open the [Command Menu,][DevtoolsCommandMenuIndex] `:` type, then the line number, then `:` another, then the column number, then select `Enter` |  
| 現在のファイルが HTML またはスクリプトの場合は、関数宣言に移動します。  <br />  現在のファイルがスタイルシートの場合は、ルール セットに移動します。  | `Control` + `Shift` + `O` Select、then type in the name of the declaration / rule set, or select it from the list of options | `Command` + `Shift` + `O` Select、then type in the name of the declaration / rule set, or select it from the list of options |  
| アクティブなタブを閉じる | `Alt`+`W` | `Option`+`W` |  

### コード エディターのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| カーソルまでの最後の単語のすべての文字を削除する | `Control`+`Delete` | `Option`+`Delete` |  
| コード行のブレークポイント [を追加または削除する][DevtoolsJavascriptBreakpointsLOC] | 行にカーソルを合った後、 `Control`+`B` | 行にカーソルを合った後、 `Command`+`B` |  
| 一致する角かっこに移動する | `Control`+`M` | `Control`+`M` |  
| 1 行のコメントを切り替える。  複数行が選択されている場合、DevTools は各行の開始にコメントを追加します。 | `Control`+`/` | `Command`+`/` |  
| カーソルが置く単語の次の出現箇所を選択または選択から削除します。  各オカレンスが同時に強調表示される | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## パフォーマンス パネルのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| レコーディングの開始/停止 | `Control`+`E` | `Command`+`E` |  
| レコーディングを保存する | `Control`+`S` | `Command`+`S` |  
| レコーディングの読み込み | `Control`+`O` | `Command`+`O` |  

## メモリ パネルのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| レコーディングの開始/停止 | `Control`+`E` | `Command`+`E` |  

## コンソール パネルのキーボード ショートカット  

| Action | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| オートコンプリート候補を受け入れる | `Right Arrow` または `Tab` | `Right Arrow` または `Tab` |  
| オートコンプリート候補を拒否する | `Escape` | `Escape` |  
| 前のステートメントを取得する | `Up Arrow` | `Up Arrow` |  
| Get next ステートメント | `Down Arrow` | `Down Arrow` |  
| 本体の **フォーカス** | `Control`+ `` ` `` | `Control`+`` ` `` |  
| 本体をクリア **する** | `Control`+`L` | `Command`+`K` または `Option`+`L` |  
| 複数行の入力を強制します。  DevTools は既定で複数行のシナリオを検出する必要があるため、このショートカットはほとんどの場合不要です。 | `Shift`+`Enter` | `Command`+`Return` |  
| 以下のコマンドを実行します。 | `Enter` | `Return` |  
| コンソールに記録されるオブジェクトのすべてのサブプロパティを展開する | Hold `Alt` , then choose **Expand** \( ![ Expand ][ImageExpandIcon] \) | Hold `Alt` , then choose **Expand** \( ![ Expand ][ImageExpandIcon] \) |  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexPlacement]: ../customize/index.md#change-devtools-placement "DevTools の配置を変更する - Microsoft Edge DevTools をカスタマイズする |Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLOC]: ../javascript/breakpoints.md#line-of-code-breakpoints "コード行のブレークポイント - Microsoft Edge DevTools でブレークポイントでコードを一時停止する方法 |Microsoft Docs"  

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