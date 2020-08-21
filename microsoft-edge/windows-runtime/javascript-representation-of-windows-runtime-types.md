---
title: Windows ランタイム型の JavaScript 表現
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 0ee55b5dd5071b0f0b31656ae164e9801e98d6ac
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942044"
---
# Windows ランタイムの種類の JavaScript 表現  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

次の表では、JavaScript が Windows ランタイムの種類を表す方法について説明します。  

> [!IMPORTANT]
> Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。  

## JavaScript の Windows ランタイムの種類  

| Windows ランタイムの種類 | JavaScript 表現 | 説明 |  
|:--- |:--- |:--- |  
| `UInt8` | `Number` | Windows ランタイム `Uint8` は、JavaScript 番号として表される符号なし 8 ビット整数です。  最初に JavaScript 値が JavaScript 番号に変換され、その後、 `ToUint32` プロセスの次に進みます。  JavaScript 番号の値が Uint8 の範囲外の場合、結果はモジュール 2^8 が適用されます。  |  
| `Int32` | `Number` | Windows ランタイムは、JavaScript 番号として表される符号付き `Int32` 32 ビット整数です。  最初に JavaScript 値が JavaScript 番号に変換され、その後、 `ToInt32` プロセスの次に進みます。  JavaScript 番号の値が範囲外の場合、 `Int32` 結果はモジュール 2^16 が適用されます。  |  
| `Int64` | `Number` | Windows ランタイム `Int64` は、標準の 64 ビット整数で、標準の数値が \[-2^53, 2^53\] の範囲内に含まれています。  この範囲外にある場合、その値は、64 ビットの整数データを格納するカスタム バックアップ ストアを持つ数値として表されます。  これらのカスタム Int64 数値の値に対するすべての算処理により、値は \[-2^53, 2^53\] の範囲内の標準の数値に変換されます。  値がこの範囲外の場合、型エラーが発生します。  この変換処理の例外は `==` `===` `SameValue` `RelationalComparison` 、2 つのビット値を表す 64 ビットを超える引数を比較する、および操作です。  いずれかの引数が標準 JavaScript 番号の場合、比較する前に、これらの引数を JavaScript 番号に変換することもできます。  JavaScript 値が Int64 値自体の場合は直接割り当てられます。それ以外の場合は、値に対する `ToInteger` 変換を適用した結果が Windows ランタイムに転送されます。  型の補正に失敗した場合は、例外が返されます。  |  
| `Uint64` | `Number` | Windows ランタイム `Uint64` は、標準の数値として表されます (標準の数値が \[0, 2^53\]])。  この範囲外にある場合、それはサインインされていない整数データのうえ 64 ビットを保持するカスタム バックアップ ストアを持つ番号と表されます。  これらのカスタム Uint64 値に対するすべての算処理により、値は \[0, 2^53\] の範囲内の標準の数値に変換されます。  値がこの範囲外の場合、型エラーが発生します。  この変換処理の例外は、2 つの 64 ビット値に基づいて引数を比較する `==` `===` `SameValue` `RelationalComparison` 、および操作です。  いずれかの引数が標準 JavaScript 番号の場合、比較する前に、これらの引数を JavaScript 番号に変換することもできます。  Uint64 値自体の場合は、JavaScript 値が直接割り当てられます。それ以外の場合、値に対して変換を適用した後にモジュール `ToInteger` 2^52 を押した後に modulo 2^52 を押すと、Windows ランタイムに換えられます。  型の変換に失敗すると、例外が返されます。  |  
| `Single` | `Number` | Windows ランタイムは、単精度値に最も多くの精度値を選択することで、JavaScript 番号として表される 32 ビットのフローティ `Single` ング ポイント番号です。  JavaScript 値は JavaScript 番号に変換され、範囲がオンになり、単精度の 32 ビット IEEE 754 フローティング ポイント番号で値を表すことができます。  変換または範囲のチェックが失敗した場合は、マーシュアリング エラーが返されます。  |  
| `Double` | `Number` | Windows ランタイム `Double` は 64 ビットのフローティング ポイント番号です。  `ToNumber` は、Windows ランタイムを `Double` JavaScript 番号に変換するために使用されます。  変換が失敗した場合は、マーシュアリング エラーが返されます。  |  
| `Boolean` | `Boolean` | Windows ランタイム `Boolean` は 8 ビット値であり、0 以外 `false` の値は `true` JavaScript として表されます `Boolean` 。  最初に JavaScript 値が JavaScript に変換 `Boolean` されます `ToBoolean` 。  つまり、JavaScript で記述されると認めた Windows ラン `void func(BOOL);` タイム関数が示されます `obj.func("test");` 。  Windows ランタイム関数は、パラメータ `BOOL` ーとしてパラメーターされたパラメーターを使用して呼び出されます `TRUE` 。  変換が失敗した場合は、マーシュアリング エラーが返されます。  |  
| `Char16` | `String` | Windows ランタイムは 16 ビット Unicode 文字で、1 文字を含む `Char16` JavaScript 文字列と表されます。  JavaScript 値は JavaScript 文字列に変換され、その文字列が 1 文字の長さのみである `ToString` ことを確認します。  その後、1 文字が値として入力 `Char16` されます。  変換または長さがチェックに失敗した場合は、マーシュアリング エラーが返されます。  |  
| `String` | `String` | Windows ランタイムは、オブジェクトがよく使用される一覧 `String` `Char16` です。  文字列は JavaScript オブジェクトとして `String` 表されます。  Windows ランタイム文字列には、"\("\) には異なる値が `null` 含られていません。  `null` また、文字列値は JavaScript の文字列に変換されます。  **注**: JavaScript が文字列を予想する Windows ランタイム パラメーターにパスされると `null` 、文字列値 "null" を返します。または `null` 、""\) が返されます。  Windows ランタイムにパスされる文字列は、常に、常に、白一の文字列にインスタンス化する必要があります。  |  
| `Enumeration` | `Object` | Windows ランタイムは 32 ビット整数 \(署名または署名されていない\) で、名前付き定数が関連付けられて `Enumeration` います。  JavaScript では、列挙型は、名前付きの各名前付き値の読み取り専用フィールドを含むオブジェクトとして表されます。  列挙値は、前に定義されたとおり、JavaScript 番号に変換 `Int32` されます `UInt32` 。  JavaScript 値が Windows ランタイム列挙型に変換されると、前述したとおり、変換、切り捨て、および範囲がオンになっています。  ただし、生じる値は、列挙型で指定されている定義された名前付き値に対してチェックされません。  |  
| `Structure` | `Object` | Windows ランタイムは、名前付きデータ フィールドの大き `Structure` なコレクションです。  JavaScript では、構造体内の各フィールドの名前付きプロパティを含む JavaScript オブジェクトとして構造体が表示されます。  構造値の変換に失敗した場合は、マーシュアリング エラーが返されます。  Windows ランタイム構造体に同等のものがない JavaScript オブジェクトのフィールドは無視されます。  **注**: JavaScript では、キーワードを使用して Windows ランタイム構造体をインスタンス化 `new` することはできません。  |  
| `Array` | `Array` | Windows ランタイム `Array` は JavaScript 配列に変換されます。  ただし、Windows ランタイム配列はサイズ変更できないため、一部の JavaScript 配列操作を実行することはできません。  変換された配列の内部プロパティは `[[Class]]` ECMAScript 5 指定で許可されないため、"Array" に設定されていません。  つまり、返 `Array.isArray(v)` される値を指定します `false` 。  JavaScript 値は次のように Windows ランタイム配列に変換されます。値が含まれます。または、ネイティブに `null` `undefined` 変換されます `null` 。  内部プロパティが "Array" の場合、それがネイティブ配列にコピーされ、この配 `[[Class]]` 列への参照が合算されます。  前述のように変換された配列の場合、基になるネイティブ配列が実行されます。  **注**: JavaScript 配列値を Windows ランタイム メソッドに指定すると、配列の完全コピーが作成されます。  |  
| 代理人 \(関数コールバック\) | `Function` | Windows ランタイム代理人は、単一の方法への参照です。  Windows ランタイム代理人は、JavaScript で、適切なスレッドで呼び出されることを保保します `Function` 。  引数が `Function` インブランクに入ると、同等の Windows ランタイム パラメーターの種類に変換されます。  代理パラメーターよりも JavaScript 引数の数が少ない場合、代理呼 `in` び出しは失敗します。  代理人にパラメーターが含めている JavaScript 引数が複数ある場合、 `in` 超 EvaScript 引数は無視されます。  代理人が非読み上げになると、パラメーターは `out` JavaScript の種類に変換され、返されます。  ネイティブ JavaScript 関数オブジェクトが Windows ランタイム代理人に変換されると、対応する型の Windows ランタイム代理人でそのオブジェクトがラップされます。  代理人が実行されると、パラメーターは `in` JavaScript の種類に変換されます。  代理人が無効になりましたが、戻り値は代理人のパ `out` ラメーターに変換されます。  |  
| インターフェイス | `Object` | インターフェイスとインターフェイス グループは、オブジェクトとして JavaScript では直接表されません。  ただし、インターフェイスはパラメーターとして表され、Windows ランタイムメソッドの型を返します。  Windows ランタイム インスタンスは次のように変換されます。<br /> <br /> 1. 有効なランタイム クラスがある場合は、そのクラスのインスタンスとしてオブジェクトを表します。<br /> 2. 有効なランタイム クラスがない場合は、インスタンスを実装し、必要なインターフェイスを実装するインターフェイスを実装するインターフェイスを実装する、名前なしランタイム クラスのインスタンスとしてオブジェクトを示します。<br /> <br /> JavaScript 値は、ランタイム クラスのインスタンスであるかインターフェイスのインスタンスであるかを判別するテストを行っています。  その場合、元の Windows ランタイム値でインターフェイスが実装されている場合、そのオブジェクトは Windows ランタイムに合うようになります。  |  
| ランタイム クラス | `Object` | Windows ランタイムのオブジェクトは、1 つ以上のインターフェイスを実装するランタイム クラスのインスタンスです。  Windows ランタイム オブジェクトは、オブジェクトとして JavaScript で表されます。  クラスで実装されたすべてのインターフェイスで定義されたメソッド、プロパティ、およびイベントのユニオンは、JavaScript オブジェクトのプロトタイプの名前付きプロパティを表します。  JavaScript のコンシューマーは、クラスの任意のメンバーに直接アクセスできます。  Windows ランタイム オブジェクトには、ランタイム クラスの実装されたすべてのインターフェイスからのすべてのメンバーを含むプロトタイプがあります。  |  
  
## 関連項目  

[JavaScript での Windows ランタイムの使用][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "JavaScript で Windows ランタイムを使用する |Microsoft ドキュメント"  
