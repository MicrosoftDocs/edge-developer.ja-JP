---
description: コンソール コマンド ラインを使用して実行中のページを操作する
title: DevTools - コンソール - コマンド ライン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, コンソール コマンド ライン
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d7ea2bef9fa0014e4d61745636a06d508565df91
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234604"
---
# コンソール コマンド ライン

コンソール のコマンド ラインを使用して、ページ上の値を表示および変更し、デバッグ コードをオンザフライで実行します[**](/visualstudio/ide/javascript-intellisense)。同時に、自動コードVisual Studio IntelliSense利用できます。 

コマンド ライン プロンプトで有効な JavaScript を入力し、押して `Enter` 実行します。 複数行入力の場合は、 `Shift+Enter` 行間を追加するために使用します。 現在の DevTools セッション中に入力した以前のコンソール コマンドを移動するには、方向キーと `Up` `Down` 方向キーを使用します。 標準の JavaScript とコンソール [API](./console-api.md)に加えて、コンソールは次のコマンドもサポートしています。

 - [DOM オブジェクトの選択](#dom-selectors)
 - [オブジェクト プロパティの検査](#object-inspection)
 - [特定のオブジェクトのすべてのイベント リスナーを検索する](#event-listeners)

コマンド ラインに入力されたスクリプトは、ページが[](/scripting/javascript/advanced/variable-scope-javascript)ブレークポイントで一時停止されていない限り、現在選択されているウィンドウのグローバル スコープで実行されます。 ページが一時停止している間に入力されたコンソール コマンドは、[](/scripting/javascript/advanced/variable-scope-javascript)呼び出し履歴内の現在の関数のローカル スコープで実行されます。

コンソールには、コンソール **出力領域** の上にターゲット実行コンテキストドロップダウンがあります。 既定の選択範囲は、トップ レベルの文書 **_top。** ドキュメント内の iframe や実行中の拡張機能もオプションとして表示され、これらの範囲内でコマンドを別の方法で実行できます。

## DOM セレクター
次のコンソール セレクターは、DOM 内のオブジェクトにすばやくアクセスする簡単な短い方法を提供します。

### $(*CSS セレクター文字列*)
指定された [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  セレクター (またはセレクターのコンマ区切りグループ) 文字列に一致するドキュメント内の最初の要素を返します。 [document.querySelector() の簡単な説明です](https://developer.mozilla.org/docs/Web/API/Document/querySelector)。

例: コンソールを開き、このページ `$('#main')` で div オブジェクトを返 `id='main'` すコマンドを入力します。

!['$' セレクターの使用例](../media/console_cmd_$.png)

### $$(*CSS セレクター文字列*)
指定された [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  セレクター (またはセレクターのコンマ区切りグループ) 文字列に一致するドキュメント内の要素の配列を返します。 [document.querySelectorAll() の簡単な説明です](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)。

例: コンソールを開き、このページに含 `$$('.container')` まれるすべての div オブジェクトを返 `class='container'` す型を入力します。

!['$$' セレクターの使用例](../media/console_cmd_$$.png)

### $0、$1、$2,...
要素パネルで選択された最後の要素を[****](../elements.md)返します。現在選択されている項目を表し、その前に選択された項目だったなど `$0` `$1` です。

例: DevTools を **[要素**] タブで開き、Select 要素ツールを押してアクティブ化し、このページの一部の領域をマウス `CTRL + B` でクリックします。 **** コンソールを開き、クリック `$0` した要素を入力して返します。

!['$0' セレクターの使用例](../media/console_cmd_$0.png)

### $x(*XPath 式*)
指定した XPath 式と一致する要素の [配列を返](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) します。 

例: コンソールを開き、属性を含むこのページのすべての要素を返 `$x('//script[@defer]')` `<script>` す型を入力 `defer` します。

!['$x' セレクターの使用例](../media/console_cmd_$x.png)

## オブジェクト検査

これらのコマンドは、オブジェクトのプロパティを簡単に検査する方法を提供します。 指定したオブジェクトは、デバッガーのグローバル名前空間または現在のスコープで定義する必要があります。

### dir(*object*)
指定したオブジェクトのプロパティのツリー ビューリストを返します。

例: コンソールを開き、入力して、このページを表すドキュメント オブジェクトの `dir(document)` オブジェクト プロパティを表示します。

!['dir' メソッドの使用例](../media/console_cmd_dir.png)

### keys(*object*)
指定したオブジェクトに関連付けられたプロパティ名の配列を返します。

例: コンソールを開き、グローバル ウィンドウ オブジェクトで定義されているプロパティ `keys(window)` を返す型を入力します。

!['keys' メソッドの使用例](../media/console_cmd_keys.png)

### values(*object*)
指定したオブジェクトに関連付けられたプロパティ値の配列を返します。

例: コンソールを開いて入力し、グローバル ウィンドウ オブジェクトで定義されているプロパティ (キー) の値 `values(window)` を返します。

!['values' メソッドの使用例](../media/console_cmd_values.png)

## イベント リスナー

このコマンドを使用すると、特定のオブジェクトに登録されているイベント リスナーを検査できます。 指定したオブジェクトは、デバッガーのグローバル名前空間または現在のスコープで定義する必要があります。

### getEventListeners(*object*)
特定のオブジェクトに登録されている各イベントの種類のキーを含むオブジェクトを返します。 各キーの値は、イベント リスナーとその関連情報の配列です。 

例: コンソールを開き、入力して、このページのドキュメント オブジェクトに登録されているイベント リスナー `getEventListeners(document)` を表示します。

!['getEventListeners' メソッドの使用例](../media/console_cmd_getEventListeners.png)
