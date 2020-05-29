---
title: Windows ランタイム型の JavaScript 表現
ms.custom: ''
ms.date: 04/01/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Runtime types [JavaScript]
- JavaScript, Windows Runtime types
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b76c28d3448b8be6fbef1fd7e23b07b2eff8d087
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570789"
---
# Windows ランタイム型の JavaScript 表現  

次の表では、JavaScript が Windows ランタイム型を表す方法について説明します。  

> [!IMPORTANT]
> Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。  

## JavaScript での Windows ランタイム型  

| Windows ランタイム型 | JavaScript 表現 | 説明 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows ランタイム `Uint8` は、JavaScript 番号として表される符号なし8ビット整数です。  JavaScript の値は、最初に JavaScript の数値に変換され、その後、 `ToUint32` プロセスが実行されます。  JavaScript 番号の値が Uint8 の範囲外の場合、結果はモジュロ 2 ^ 8 が適用されます。 |  
| `Int32` | `Number` | Windows ランタイム `Int32` は、JavaScript 番号として表される符号付きの32ビット整数です。  JavaScript の値は、最初に JavaScript の数値に変換され、その後、 `ToInt32` プロセスが実行されます。  JavaScript 番号の値が a の範囲外の場合、 `Int32` 結果はモジュロ 2 ^ 16 が適用されます。 |  
| `Int64` | `Number` | Windows ランタイム `Int64` は、64ビットの符号付き整数であり、値が \ [-2 ^ 53, 2 ^ 53 \] の範囲内にある場合は標準の数値として表されます。  この範囲外の場合は、整数データの完全な64ビットが保持されているカスタムバッキングストアを含む数値として表されます。  これらのユーザー設定の Int64 数値値に対するすべての算術演算では、値が \ [-2 ^ 53, 2 ^ 53 \] の標準の数値に変換されます。  値がこの範囲外の場合は、型エラーが発生します。  この変換プロセスの例外は、、、、ということです。この処理は、 `==` `===` `SameValue` `RelationalComparison` 完全な64ビットに基づいて、2つの64ビット値が渡された場合に、引数を比較します。  いずれかの引数が標準の JavaScript 番号である場合、これらの操作により、比較前に引数を JavaScript の数値に変換することもできます。  JavaScript 値は、Int64 値自体の場合、直接割り当てられます。それ以外の場合は、 `ToInteger` 値に対する変換を適用した結果が Windows ランタイムに渡されます。  型の強制変換が失敗すると、例外が返されます。 |  
| `Uint64` | `Number` | Windows ランタイム `Uint64` は符号なしの64ビット整数であり、\ [0, 2 ^ 53 \] の範囲内にある場合は標準の数値として表されます。  この範囲外の場合は、符号なし整数データの完全な64ビットを保持するカスタムバッキングストアを含む数値として表されます。  これらのカスタムの Uint64 値に対するすべての算術演算では、値が、範囲 \ [0, 2 ^ 53 \] の標準の数値に変換されます。  値がこの範囲外の場合は、型エラーが発生します。  この変換処理の例外は、、、、ということです。これは、 `==` `===` `SameValue` `RelationalComparison` 2 64 ビット値が渡されたときに、完全な64ビットに基づいて引数を比較する、、、という操作です。  いずれかの引数が標準の JavaScript 番号である場合、これらの操作により、比較前に引数を JavaScript の数値に変換することもできます。  JavaScript 値は、Uint64 値自体である場合、直接割り当てられます。それ以外の場合は、値に変換を適用した `ToInteger` 後、モジュロ 2 ^ 52 を受け取ると、Windows ランタイムに渡されます。  型変換が失敗すると、例外が返されます。 |  
| `Single` | `Number` | Windows ランタイム `Single` は、32ビット浮動小数点数であり、最も近い倍精度の値を単精度の値に指定することによって JavaScript の数値として表されます。  JavaScript の値が JavaScript の数値に変換され、[範囲] がオンになって、値が単一 precision の32ビット IEEE 754 浮動小数点数で表されることを確認します。  変換または範囲のチェックが失敗すると、マーシャリングエラーが返されます。 |  
| `Double` | `Number` | Windows ランタイム `Double` は、64ビット浮動小数点値です。  `ToNumber` Windows ランタイムを JavaScript の数値に変換するために使用され `Double` ます。  変換が失敗すると、マーシャリングエラーが返されます。 |  
| `Boolean` | `Boolean` | Windows ランタイム `Boolean` は、 `false` `true` JavaScript として表される8ビット値であり、0は0以外の値になり `Boolean` ます。  JavaScript の値は、最初に JavaScript に変換され `Boolean` `ToBoolean` ます。  つまり、として宣言された Windows ランタイム関数は、 `void func(BOOL);` JavaScript でとして記述することができ `obj.func("test");` ます。  Windows ランタイム関数が呼び出されたときに、 `BOOL` というパラメーターが渡され `TRUE` ます。  変換が失敗すると、マーシャリングエラーが返されます。 |  
| `Char16` | `String` | Windows ランタイム `Char16` は16ビットの Unicode 文字であり、1つの文字を含む JavaScript 文字列として表されます。  JavaScript の値が JavaScript の文字列に変換され、その `ToString` 文字列が1文字の長さのみであることが確認されます。  1つの文字が値として渡され `Char16` ます。  変換または長さのチェックに失敗した場合は、マーシャリングエラーが返されます。 |  
| `String` | `String` | Windows ランタイム `String` は、オブジェクトの順序を `Char16` 変更できません。  文字列は JavaScript オブジェクトとして表され `String` ます。  Windows ランタイム文字列の値は `null` 、および空の文字列 \ ("" \) には異なります。  `null` 空の文字列値は、JavaScript の空の文字列に変換されます。  注: JavaScript `null` が文字列を想定する Windows ランタイムパラメーターに渡されると、文字列値 "null"、 `null` 空の文字列 \ ("" \) が生成されます。  Windows ランタイムに渡される文字列は、常に空の文字列にインスタンス化する必要があります。 |  
| `Enumeration` | `Object` | Windows ランタイム `Enumeration` は、関連付けられた名前付き定数のセットを持つ32ビット整数 \ (符号付きまたは符号なし \) です。  JavaScript では、列挙型は、名前付きの各値の読み取り専用フィールドを含むオブジェクトとして表されます。  列挙値は、およびの前に定義された JavaScript の数値に変換され `Int32` `UInt32` ます。  JavaScript の値が Windows ランタイムの列挙型に変換されると、変換され、切り捨てられて、前に説明した範囲が選択されています。  ただし、結果の値は、列挙で指定された定義された名前付きの値に対してチェックされません。 |  
| `Structure` | `Object` | Windows ランタイム `Structure` は、名前付きデータフィールドの異種コレクションです。  JavaScript では、構造体は、構造体の各フィールドの名前付きプロパティを含む JavaScript オブジェクトとして表されます。  構造体の値の変換に失敗した場合、マーシャリングエラーが返されます。  Windows ランタイム構造体に対応していない JavaScript オブジェクトのフィールドは無視されます。  注: Windows ランタイムの構造体は、JavaScript でキーワードを使ってインスタンス化することはできません。 `new` |  
| `Array` | `Array` | Windows ランタイム `Array` は JavaScript 配列に変換されます。  ただし、Windows ランタイムの配列はサイズを変更できないため、一部の JavaScript 配列操作はできません。  変換された `[[Class]]` 配列の internal プロパティは、ECMAScript 5 仕様で許可されていないため、"array" に設定されません。  これは、 `Array.isArray(v)` 戻り値 `false` です。  JavaScript の値は、次のように Windows ランタイム配列に変換されます。値がの場合 `null` は `undefined` 、ネイティブに変換されます `null` 。  内部 `[[Class]]` プロパティが "配列" の場合は、ネイティブ配列にコピーされ、この配列への参照が渡されます。  前に説明したように変換された配列の場合は、基になるネイティブ配列が渡されます。  注: JavaScript 配列値を Windows ランタイムメソッドに渡すと、配列の完全なコピーが発生します。 |  
| Delegate \ (関数のコールバック \) | `Function` | Windows ランタイムデリゲートは、1つのメソッドへの参照です。  Windows ランタイムデリゲートは javascript として javascript として表され `Function` 、適切なスレッドで呼び出されることが保証されます。  が呼び出されると、 `Function` 引数は同等の Windows ランタイムパラメーター型に変換されます。  デリゲートパラメーター数よりも JavaScript 引数が少ない場合は `in` 、デリゲート呼び出しは失敗します。  デリゲートのパラメーター数よりも多くの JavaScript 引数がある場合は `in` 、追加の javascript 引数は無視されます。  デリゲートが呼び出される `out` と、パラメーターが JavaScript の型に変換され、返されます。  ネイティブ JavaScript 関数オブジェクトが Windows ランタイムデリゲートに変換される場合は、対応する型の Windows ランタイムデリゲートでラップされます。  デリゲートが呼び出されると、 `in` パラメーターが JavaScript 型に変換されます。  デリゲートが呼び出されると、戻り値はデリゲートのパラメーターに変換され `out` ます。 |  
| インターフェイス | `Object` | インターフェイスとインターフェイスグループは、JavaScript でオブジェクトとして直接表現されるわけではありません。  ただし、インターフェイスは、Windows ランタイムメソッドのパラメーターと戻り値の型として表されます。  Windows ランタイムインターフェイスインスタンスは、次のように変換されます。<br /> <br /> 1. 有効なランタイムクラスがある場合は、そのクラスのインスタンスとしてオブジェクトを表します。<br /> 2. 有効なランタイムクラスがない場合は、インスタンスに実装されていることがわかっているインターフェイスとその必須インターフェイスを実装する無名のランタイムクラスのインスタンスとしてオブジェクトを表します。<br /> <br /> JavaScript 値がテストされ、ランタイムクラスまたはインターフェイスのインスタンスであるかどうかが判定されます。  その場合は、元の Windows ランタイムの値によってインターフェイスが実装され、そのオブジェクトが Windows ランタイムに渡されます。 |  
| ランタイムクラス | `Object` | Windows ランタイムのオブジェクトは、1つ以上のインターフェイスを実装するランタイムクラスのインスタンスにすることができます。  Windows ランタイムオブジェクトは、JavaScript でオブジェクトとして表されます。  クラスのすべての実装済みインターフェイスで定義されているメソッド、プロパティ、イベントのユニオンは、JavaScript オブジェクトのプロトタイプで名前付きプロパティを表します。  JavaScript コンシューマーは、クラスの任意のメンバーに直接アクセスできます。  Windows ランタイムオブジェクトには、ランタイムクラスの実装されたすべてのインターフェイスからすべてのメンバーを含むプロトタイプが含まれています。 |  
  
## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "JavaScript での Windows ランタイムの使用"  
