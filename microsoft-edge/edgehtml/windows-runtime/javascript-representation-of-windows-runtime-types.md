---
description: Windows ランタイム型の JavaScript 表現。
title: Windows ランタイム型の JavaScript 表現
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
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1fd6c8831b2c98cea5794866a0f8830d8f557723
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235071"
---
# Windows ランタイム型の JavaScript 表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

次の表では、JavaScript が Windows ランタイム型を表す方法について説明します。  

> [!IMPORTANT]
> Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。  

## JavaScript での Windows ランタイム型  

| Windows ランタイムの種類 | JavaScript 表現 | 説明 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows ランタイムは、JavaScript 番号として表される符号なし `Uint8` 8 ビットの整数です。  JavaScript 値は最初に JavaScript 番号に変換され、次にプロセス `ToUint32` が実行されます。  JavaScript 番号の値が Uint8 の範囲を外している場合、結果にはモジュール 2^8 が適用されます。  |  
| `Int32` | `Number` | Windows ランタイムは、JavaScript 番号として表される符号付き `Int32` 32 ビットの整数です。  JavaScript 値は最初に JavaScript 番号に変換され、次にプロセス `ToInt32` が実行されます。  JavaScript 番号の値が an の範囲を外している場合、結果には `Int32` モジュール 2^16 が適用されます。  |  
| `Int64` | `Number` | Windows ランタイムは符号付き `Int64` 64 ビットの整数で、\[-2^53, 2^53\] の範囲内にある場合は標準の数値として表されます。  この範囲を外れた場合は、整数データの完全な 64 ビットを保持するカスタム バッキング ストアを持つ数値として表されます。  これらのカスタム Int64 数値に対する算術演算はすべて、\[-2^53, 2^53\] の範囲の標準の数値に変換されます。  値がこの範囲を外している場合は、型エラーが発生します。  この変換プロセスの例外は、2 つ渡された場合に 64 ビット全体に基づいて引数を比較する `==` 、64 ビットの値です `===` `SameValue` `RelationalComparison` 。  どちらかの引数が標準の JavaScript 番号である場合、これらの操作は比較の前に引数を JavaScript 番号に変換します。  JavaScript 値は、Int64 値自体である場合に直接割り当てられます。それ以外の場合は、値に変換 `ToInteger` を適用した結果が Windows ランタイムに渡されます。  型の型の型の型が失敗した場合は、例外が返されます。  |  
| `Uint64` | `Number` | Windows ランタイムは符号なし 64 ビットの整数で `Uint64` 、\[0, 2^53\] の範囲内にある場合は標準の数値として表されます。  この範囲を外れた場合、完全な 64 ビットの符号なし整数データを保持するカスタム バッキング ストアを持つ数値として表されます。  これらのカスタム Uint64 値に対する算術演算はすべて、値を \[0, 2^53\] の範囲の標準数値に変換します。  値がこの範囲を外している場合は、型エラーが発生します。  この変換プロセスの例外は、2 つの 64 ビット値を渡した場合に `==` `===` `SameValue` `RelationalComparison` 、完全な 64 ビットに基づいて引数を比較する 、操作です。  どちらかの引数が標準の JavaScript 番号である場合、これらの操作は比較の前に引数を JavaScript 番号に変換します。  JavaScript 値が Uint64 値自体の場合は直接割り当てられます。それ以外の場合は、値に変換を適用し、その後にモジュール 2^52 を取った結果が Windows ランタイム `ToInteger` に渡されます。  型変換が失敗した場合は、例外が返されます。  |  
| `Single` | `Number` | Windows ランタイムは 32 ビット浮動小数点数で、単精度値に最も近い倍精度値を選択することで `Single` JavaScript 数値として表されます。  JavaScript 値は JavaScript 番号に変換され、範囲がチェックされ、その値が単精度 32 ビット IEEE 754 浮動小数点数で表される可能性があります。  変換または範囲のチェックが失敗した場合は、マーシャリング エラーが返されます。  |  
| `Double` | `Number` | Windows ランタイムは `Double` 64 ビット浮動小数点数です。  `ToNumber` は、Windows ランタイムを `Double` JavaScript 番号に変換するために使用されます。  変換が失敗した場合は、マーシャリング エラーが返されます。  |  
| `Boolean` | `Boolean` | Windows ランタイムは 8 ビット値で、ゼロは 0 で、0 以外の値は `Boolean` `false` `true` JavaScript として表されます `Boolean` 。  JavaScript の値は、最初に JavaScript に変換 `Boolean` されます `ToBoolean` 。  つまり、JavaScript で記述できる方法で宣言された Windows ランタイム `void func(BOOL);` 関数を次のように指定します `obj.func("test");` 。  Windows ランタイム関数は、渡されたパラメーターを `BOOL` 使用して呼び出されます `TRUE` 。  変換が失敗した場合は、マーシャリング エラーが返されます。  |  
| `Char16` | `String` | Windows ランタイムは、1 つの文字を含む JavaScript 文字列として表される `Char16` 16 ビットの Unicode 文字です。  JavaScript の値は、JavaScript 文字列に変換され、その文字列が 1 文字長のみである必要があります `ToString` 。  その後、1 文字が値として渡 `Char16` されます。  変換または長さのチェックが失敗した場合は、マーシャリング エラーが返されます。  |  
| `String` | `String` | Windows ランタイムは `String` 、オブジェクトの不変シーケンス `Char16` です。  文字列は JavaScript オブジェクトとして表 `String` されます。  Windows ランタイム文字列の値は異なって、 `null` 空の文字列 \(""\) です。  `null` 空の文字列値は JavaScript の空の文字列に変換されます。  **注**: JavaScript が文字列を必要とする Windows ランタイム パラメーターに渡される場合、文字列値 "null" が生成されます。空の文字列 `null` `null` \(""\) は生成されません。  Windows ランタイムに渡される文字列は、常に空の文字列にインスタンス化する必要があります。  |  
| `Enumeration` | `Object` | Windows ランタイムは、名前付き定数のセットが関連付けられた 32 ビット整数 \(符号付きまたは符号なし `Enumeration` \) です。  JavaScript では、列挙型は、名前付き値ごとに読み取り専用フィールドを含むオブジェクトとして表されます。  列挙値は、前に定義した JavaScript 番号に `Int32` 変換されます `UInt32` 。  JavaScript の値を Windows ランタイム列挙に変換すると、前に説明したように、変換、切り詰め、範囲のチェックが行されます。  ただし、結果の値は、列挙で指定された定義済みの名前付き値に対してチェックされません。  |  
| `Structure` | `Object` | Windows ランタイムは `Structure` 、名前付きデータ フィールドの異種コレクションです。  JavaScript では、構造体は、構造内の各フィールドの名前付きプロパティを含む JavaScript オブジェクトとして表されます。  構造体の値の変換に失敗すると、マーシャリング エラーが返されます。  Windows ランタイム構造で同等の値を持たない JavaScript オブジェクトのフィールドは無視されます。  **メモ**: キーワードを使用して JavaScript で Windows ランタイム構造をインスタンス化 `new` することはできません。  |  
| `Array` | `Array` | Windows ランタイムは `Array` JavaScript 配列に変換されます。  ただし、Windows ランタイム配列はサイズ変更できないので、一部の JavaScript 配列操作は実行できません。  変換された配列の内部プロパティは、ECMAScript 5 の仕様では許可されていないので `[[Class]]` 、"Array" に設定されません。  これは、戻 `Array.isArray(v)` り値を意味します `false` 。  JavaScript の値は、次のように Windows ランタイム配列に変換されます。値がネイティブの場合、またはネイティブ `null` `undefined` に変換されます `null` 。  内部プロパティが "Array" の場合は、ネイティブ配列にコピーされ、この配列への参照 `[[Class]]` が渡されます。  前に説明したように、変換された配列である場合は、基になるネイティブ配列が渡されます。  **注**: JavaScript 配列値を Windows ランタイム メソッドに渡す場合、配列の完全コピーが発生します。  |  
| Delegate \(function callback\) | `Function` | Windows ランタイム デリゲートは、1 つのメソッドへの参照です。  Windows ランタイム デリゲートは JavaScript で JavaScript として表され、適切なスレッドで呼び出 `Function` される必要があります。  呼び `Function` 出されると、引数は同等の Windows ランタイム パラメーター型に変換されます。  デリゲート パラメーターよりも少ない JavaScript 引数がある場合、デリゲート呼び `in` 出しは失敗します。  デリゲート内のパラメーターよりも多くの JavaScript 引数がある場合、余分な `in` JavaScript 引数は無視されます。  デリゲートが呼び出されると、 `out` パラメーターは JavaScript 型に変換され、返されます。  ネイティブの JavaScript 関数オブジェクトが Windows ランタイム デリゲートに変換された場合、対応する型の Windows ランタイム デリゲートにラップされます。  デリゲートが呼び出されると、 `in` パラメーターは JavaScript 型に変換されます。  デリゲートが呼び出されると、戻り値はデリゲートの `out` パラメーターに変換されます。  |  
| インターフェイス | `Object` | インターフェイスとインターフェイス グループは、JavaScript ではオブジェクトとして直接表現されません。  ただし、インターフェイスは、Windows ランタイム メソッドのパラメーターおよび戻り値の型として表されます。  Windows ランタイム インターフェイス インスタンスは、次のように変換されます。<br /> <br /> 1. 有効なランタイム クラスがある場合は、そのオブジェクトをそのクラスのインスタンスとして表します。<br /> 2. 有効なランタイム クラスがない場合は、インスタンスが実装する既知のインターフェイスと必要なインターフェイスを正確に実装する、名前のないランタイム クラスのインスタンスとしてオブジェクトを表します。<br /> <br /> JavaScript 値がテストされ、それがランタイム クラスのインスタンスかインターフェイスかを判断します。  インターフェイスが実装されている場合、元の Windows ランタイム値がインターフェイスを実装すると、オブジェクトは Windows ランタイムに渡されます。  |  
| ランタイム クラス | `Object` | Windows ランタイムのオブジェクトは、1 つ以上のインターフェイスを実装するランタイム クラスのインスタンスです。  Windows ランタイム オブジェクトは、JavaScript でオブジェクトとして表されます。  クラスの実装されているインターフェイスすべてで定義されているメソッド、プロパティ、およびイベントのユニオンは、JavaScript オブジェクトのプロトタイプの名前付きプロパティを表します。  JavaScript コンシューマーは、クラスの任意のメンバーに直接アクセスできます。  Windows ランタイム オブジェクトには、ランタイム クラスのすべての実装インターフェイスのすべてのメンバーを含むプロトタイプがあります。  |  
  
## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  
