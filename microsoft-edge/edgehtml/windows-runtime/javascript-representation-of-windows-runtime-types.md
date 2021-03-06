---
description: Windows ランタイム型の JavaScript 表現
title: Windows ランタイム型の JavaScript 表現
ms.custom: ''
ms.date: 10/30/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- Windows Runtime types [JavaScript]
- JavaScript, Windows Runtime types
ms.assetid: f4851802-8b40-4afa-ba6c-8a162a9a43cc
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 18a288f95e7211794e3ceb88d700026dae359b06
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399331"
---
# <a name="javascript-representation-of-windows-runtime-types"></a>Windows ランタイム型の JavaScript 表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

次の表では、JavaScript が Windows ランタイム型を表す方法について説明します。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## <a name="windows-runtime-types-in-javascript"></a>JavaScript の Windows ランタイム型  

| Windows ランタイムの種類 | JavaScript 表記 | 説明 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows ランタイムは、JavaScript 番号として表される符号なしの `Uint8` 8 ビット整数です。  JavaScript の値は、最初に JavaScript 番号に変換され、次に `ToUint32` 処理が実行されます。  JavaScript 番号の値が Uint8 の範囲を外している場合、結果にはモジュロ 2^8 が適用されます。  |  
| `Int32` | `Number` | Windows ランタイムは `Int32` 、JavaScript 番号として表される符号付き 32 ビット整数です。  JavaScript の値は、最初に JavaScript 番号に変換され、次に `ToInt32` 処理が実行されます。  JavaScript 番号の値が a の範囲を外している場合、結果にはモジュロ `Int32` 2^16 が適用されます。  |  
| `Int64` | `Number` | Windows ランタイム `Int64` は符号付き 64 ビット整数で、\[-2^53, 2^53\] の範囲内にある場合は標準番号として表されます。  この範囲を外れた場合は、整数データの完全な 64 ビットを保持するカスタム バッキング ストアを持つ数値として表されます。  これらのカスタム Int64 数値に対するすべての数学的演算により、値は \[-2^53, 2^53\] の範囲の標準数値に変換されます。  値がこの範囲を外している場合は、型エラーが発生します。  この変換プロセスの例外は、2 つの 64 ビット値を渡した場合の `==` `===` `SameValue` `RelationalComparison` 引数を完全な 64 ビットに基づいて比較する 、および操作です。  いずれかの引数が標準の JavaScript 番号である場合、これらの操作は、比較前に引数を JavaScript 番号に変換します。  JavaScript 値が Int64 値自体の場合は、JavaScript 値が直接割り当てられます。それ以外の場合は、値に変換 `ToInteger` を適用した結果が Windows ランタイムに渡されます。  型の coercion が失敗した場合は、例外が返されます。  |  
| `Uint64` | `Number` | Windows ランタイム `Uint64` は符号なしの 64 ビット整数で、\[0, 2^53\] の範囲内にある場合は標準の数値として表されます。  この範囲を外れた場合は、符号なし整数データの完全な 64 ビットを保持するカスタム バッキング ストアを持つ数値として表されます。  これらのカスタム Uint64 値に対するすべての数学的演算により、値は \[0, 2^53\] の範囲の標準数値に変換されます。  値がこの範囲を外している場合は、型エラーが発生します。  この変換プロセスの例外は、2 つの 64 ビット値を渡した場合に `==` `===` `SameValue` 、64 ビット全体に基づいて引数を比較する 、および操作 `RelationalComparison` です。  いずれかの引数が標準の JavaScript 番号である場合、これらの操作は、比較前に引数を JavaScript 番号に変換します。  JavaScript 値が Uint64 値自体の場合は、JavaScript 値が直接割り当てられます。それ以外の場合は、値に変換を適用した結果に続いてモジュロ `ToInteger` 2^52 を取得すると、Windows ランタイムに渡されます。  型変換が失敗した場合は、例外が返されます。  |  
| `Single` | `Number` | Windows ランタイムは、32 ビット浮動小数点数で、最も近い倍精度値を単精度値に選択して `Single` JavaScript 番号として表されます。  JavaScript 値は JavaScript 番号に変換され、範囲がチェックされ、その値が単精度の 32 ビット IEEE 754 浮動小数点数で表される可能性があります。  変換または範囲のチェックに失敗すると、マーシャリング エラーが返されます。  |  
| `Double` | `Number` | Windows ランタイム `Double` は、64 ビット浮動小数点数です。  `ToNumber` は、Windows ランタイムを `Double` JavaScript 番号に変換するために使用されます。  変換に失敗すると、マーシャリング エラーが返されます。  |  
| `Boolean` | `Boolean` | Windows ランタイムは 8 ビットの値で、ゼロ以外の値は `Boolean` `false` JavaScript として `true` 表されます `Boolean` 。  JavaScript の値は、 によって最初に JavaScript に `Boolean` 変換されます `ToBoolean` 。  つまり、JavaScript で記述できるように宣言された `void func(BOOL);` Windows ランタイム関数は、 として記述されます `obj.func("test");` 。  Windows ランタイム関数は、 として渡されたパラメーター `BOOL` で呼び出されます `TRUE` 。  変換に失敗すると、マーシャリング エラーが返されます。  |  
| `Char16` | `String` | Windows ランタイムは 16 ビットの Unicode 文字で、1 文字を含む `Char16` JavaScript 文字列として表されます。  JavaScript の値は JavaScript 文字列に変換され、その文字列が 1 文字の長いだけである必要があります `ToString` 。  その後、1 文字が値として渡 `Char16` されます。  変換または長さのチェックに失敗すると、マーシャリング エラーが返されます。  |  
| `String` | `String` | Windows ランタイムは `String` 、オブジェクトの不変のシーケンス `Char16` です。  文字列は JavaScript オブジェクトとして表 `String` されます。  Windows ランタイム文字列には、\(""\) の異なる値と空の文字列 `null` が含まれています。  `null` 空の文字列値は JavaScript 空の文字列に変換されます。  **メモ**: JavaScript が文字列を期待する Windows ランタイム パラメーターに渡された場合、文字列値 "null" または空の文字列 `null` `null` \("\) が生成されます。  Windows ランタイムに渡される文字列は、常に空の文字列にインスタンス化する必要があります。  |  
| `Enumeration` | `Object` | Windows ランタイムは、名前付き定数のセットが関連付けられている 32 ビット整数 \(符号付きまたは符号なし `Enumeration` \) です。  JavaScript では、列挙は、名前付き値ごとに読み取り専用フィールドを含むオブジェクトとして表されます。  列挙値は、前に定義した JavaScript 番号に `Int32` 変換されます `UInt32` 。  JavaScript 値を Windows ランタイム列挙に変換すると、前述のように変換、切り捨て、範囲のチェックが行います。  ただし、結果の値は、列挙で指定された定義済みの名前付き値に対してチェックされません。  |  
| `Structure` | `Object` | Windows ランタイムは `Structure` 、名前付きデータ フィールドの異種コレクションです。  JavaScript では、構造体は、構造内の各フィールドの名前付きプロパティを含む JavaScript オブジェクトとして表されます。  構造体の値の変換に失敗すると、マーシャリング エラーが返されます。  Windows ランタイム構造に同等の値を持つ JavaScript オブジェクト内のフィールドは無視されます。  **注**: キーワードを使用して JavaScript で Windows ランタイム構造をインスタンス化 `new` することはできません。  |  
| `Array` | `Array` | Windows ランタイム `Array` は JavaScript 配列に変換されます。  ただし、Windows ランタイム配列はサイズ変更できないので、一部の JavaScript 配列操作は使用できません。  変換された `[[Class]]` 配列の内部プロパティは、ECMAScript 5 仕様では許可されないので、"Array" に設定されません。  これは、 を `Array.isArray(v)` 返します `false` 。  JavaScript の値は、次のように Windows ランタイム配列に `null` `undefined` 変換されます。 `null`  内部プロパティが "Array" の場合は、ネイティブ配列にコピーされ、この配列への `[[Class]]` 参照が渡されます。  前に説明したように、変換された配列の場合は、基になるネイティブ配列が渡されます。  **メモ**: JavaScript 配列の値を Windows ランタイム メソッドに渡す場合、配列の完全なコピーが発生します。  |  
| Delegate \(function callback\) | `Function` | Windows ランタイム デリゲートは、1 つのメソッドへの参照です。  Windows ランタイム デリゲートは JavaScript で JavaScript として表され、適切なスレッドで呼び出 `Function` される保証があります。  呼び `Function` 出されると、引数は同等の Windows ランタイム パラメーター型に変換されます。  デリゲート パラメーターよりも JavaScript 引数が少ない場合、デリゲート `in` 呼び出しは失敗します。  デリゲート内のパラメーターよりも多くの JavaScript 引数がある場合、余分な `in` JavaScript 引数は無視されます。  デリゲートが呼び出されると、 `out` パラメーターは JavaScript 型に変換され、返されます。  ネイティブ JavaScript 関数オブジェクトを Windows ランタイム デリゲートに変換すると、対応する型の Windows ランタイム デリゲートにラップされます。  デリゲートが呼び出されると、 `in` パラメーターは JavaScript 型に変換されます。  デリゲートが呼び出されると、戻り値はデリゲートの `out` パラメーターに変換されます。  |  
| インターフェイス | `Object` | インターフェイスとインターフェイス グループは、JavaScript ではオブジェクトとして直接表現されません。  ただし、インターフェイスは、Windows ランタイム メソッドのパラメーターおよび戻り値の型として表されます。  Windows ランタイム インターフェイス インスタンスは、次のように変換されます。<br /> <br /> 1. 有効なランタイム クラスがある場合は、そのクラスのインスタンスとしてオブジェクトを表します。<br /> 2. 有効なランタイム クラスがない場合は、インスタンスが実装する既知のインターフェイスと必要なインターフェイスを正確に実装する、名前のないランタイム クラスのインスタンスとしてオブジェクトを表します。<br /> <br /> JavaScript 値がテストされ、それがランタイム クラスまたはインターフェイスのインスタンスであるかどうかを判断します。  その場合、元の Windows ランタイム値がインターフェイスを実装している場合、オブジェクトは Windows ランタイムに渡されます。  |  
| ランタイム クラス | `Object` | Windows ランタイム内のオブジェクトには、1 つ以上のインターフェイスを実装するランタイム クラスのインスタンスを指定できます。  Windows ランタイム オブジェクトは JavaScript でオブジェクトとして表されます。  クラスのすべての実装インターフェイスで定義されたメソッド、プロパティ、およびイベントのユニオンは、JavaScript オブジェクトのプロトタイプの名前付きプロパティを表します。  JavaScript コンシューマーは、クラスの任意のメンバーに直接アクセスできます。  Windows ランタイム オブジェクトには、ランタイム クラスのすべての実装インターフェイスのすべてのメンバーを含むプロトタイプがあります。  |  
  
## <a name="see-also"></a>関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用|Microsoft Docs"  
