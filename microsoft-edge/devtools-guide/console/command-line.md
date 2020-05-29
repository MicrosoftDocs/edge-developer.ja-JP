---
description: コンソールコマンドラインを使って、実行中のページを操作する
title: DevTools-本体-コマンドライン
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、コンソールコマンドライン
ms.custom: seodec18
ms.openlocfilehash: c661736e5ea264f60279c89cfa0f9c55361d2288
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570523"
---
# コンソールコマンドライン

本体のコマンドラインを使って、ページ上の値を表示して変更し、その場でデバッグコードを実行します。 Visual Studio の[*IntelliSense*](/visualstudio/ide/javascript-intellisense)では、自動コード補完が利用されます。 

コマンドラインプロンプトで任意の有効な JavaScript を入力し、を押して `Enter` 実行します。 複数行入力の場合は、 `Shift+Enter` 改行を追加するために使用します。 現在の `Up` `Down` devtools セッション中に入力した前のコンソールコマンドの間を移動するには、および方向キーを使用します。 コンソールは、標準の JavaScript や[コンソール API](./console-api.md)に加えて、次のコマンドもサポートします。

 - [DOM オブジェクトの選択](#dom-selectors)
 - [オブジェクトのプロパティを検査する](#object-inspection)
 - [特定のオブジェクトのすべてのイベントリスナーを検索する](#event-listeners)

コマンドラインで入力したスクリプトは、ページがブレークポイントで一時停止されていない限り、現在選択されているウィンドウの[グローバルスコープ](/scripting/javascript/advanced/variable-scope-javascript)で実行されます。 ページが一時停止している間に入力されたコンソールコマンドは、呼び出し履歴内の現在の関数の[ローカルスコープ](/scripting/javascript/advanced/variable-scope-javascript)で実行されます。

本体には本体の出力領域のすぐ上に**ターゲット**の実行コンテキストのドロップダウンがあります。 既定では、[ **_top**] のトップレベルのドキュメントが選択されています。 ドキュメント内または実行可能な拡張機能もオプションとして表示され、それらのスコープ内でコマンドを実行することができます。

## DOM セレクター
以下のコンソールセレクターでは、DOM 内のオブジェクトにすばやくアクセスするためのシンプルな shorthands を提供しています。

### $ (*CSS セレクター文字列*)
指定された[CSS セレクター](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors) (または、複数のセレクターのグループ) 文字列に一致する、文書内の最初の要素を返します。 [Document selector ()](https://developer.mozilla.org/docs/Web/API/Document/querySelector)の短縮形。

例: 本体を開き、 `$('#main')` このページで div オブジェクトを返すために type を入力し `id='main'` ます。

![' $ ' セレクターの使用例](../media/console_cmd_$.png)

### $ $ (*CSS セレクター文字列*)
指定された[CSS セレクター](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors) (または、コンマ区切りのセレクター) 文字列に一致する、文書内の要素の配列を返します。 [QuerySelectorAll ()](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)の短縮形。

例: 本体を開いて、 `$$('.container')` このページにあるすべての div オブジェクトを返すように入力し `class='container'` ます。

![' $ $ ' セレクターの使用例](../media/console_cmd_$$.png)

### $0、$1、$2,...
[**要素**](../elements.md)パネルで選択されている最後の要素を返します。ここでは、現在選択されている項目を示し、その前に選択されている項目が含まれてい `$0` `$1` ます。

例: DevTools を開いて [**要素**] タブに移動し、を押して `CTRL + B` **[要素の選択**] ツールをアクティブ化し、マウスでこのページの一部の領域をクリックします。 次に、コンソールを開いて、 `$0` クリックしたばかりの要素を返すように入力します。

![' $0 ' セレクターの使用例](../media/console_cmd_$0.png)

### $x (*XPath 式*)
指定された[XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript)式に一致する要素の配列を返します。 

例: 本体を開き、 `$x('//script[@defer]')` `<script>` 属性を含むこのページのすべての要素を返すには、「...」と入力し `defer` ます。

!["$X" セレクターの使用例](../media/console_cmd_$x.png)

## オブジェクト検査

以下のコマンドを使うと、オブジェクトのプロパティを簡単に調べることができます。 指定したオブジェクトは、グローバル名前空間またはデバッガーの現在のスコープで定義されている必要があります。

### dir (*オブジェクト*)
指定されたオブジェクトのプロパティのツリービューのリストを返します。

例: 本体を開き、 `dir(document)` このページを表すドキュメントオブジェクトのオブジェクトプロパティを表示するには「」と入力します。

![' Dir ' メソッドの使用例](../media/console_cmd_dir.png)

### キー (*オブジェクト*)
指定されたオブジェクトに結び付けられているプロパティ名の配列を返します。

例: 本体と type を開き、 `keys(window)` グローバルウィンドウオブジェクトで定義されているすべてのプロパティを返します。

!["Keys" メソッドの使用例](../media/console_cmd_keys.png)

### 値 (*オブジェクト*)
指定されたオブジェクトに結び付けられているプロパティ値の配列を返します。

例: 本体を開き、 `values(window)` グローバルウィンドウオブジェクトで定義されているすべてのプロパティ (キー) の値を返すには、「type」と入力します。

!["Values" メソッドの使用例](../media/console_cmd_values.png)

## イベントリスナー

このコマンドを使うと、指定したオブジェクトに登録されているイベントリスナーを調べることができます。 指定したオブジェクトは、グローバル名前空間またはデバッガーの現在のスコープで定義されている必要があります。

### getEventListeners (*object*)
指定されたオブジェクトに登録されている各イベントの種類について、キーを含むオブジェクトを返します。 各キーの値は、イベントリスナーとそれに関連する情報の配列です。 

例: 本体と type を開き、 `getEventListeners(document)` このページのドキュメントオブジェクトに登録されているすべてのイベントリスナーを表示します。

![GetEventListeners メソッドの使用例](../media/console_cmd_getEventListeners.png)
