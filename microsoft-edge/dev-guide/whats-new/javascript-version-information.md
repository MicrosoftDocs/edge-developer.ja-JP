---
title: JavaScript のバージョン情報
description: JavaScript のサポートは Microsoft Edge、Microsoft Store アプリ、およびトラブルシューティInternet Explorer
ms.date: 07/28/2020
ms.prod: microsoft-edge
ms.topic: language-reference
author: MSEdgeTeam
ms.author: msedgedevrel
keywords: edge、ie、chakra、jscript、wwa、Store アプリ
ms.custom: seodec18
ms.openlocfilehash: 6041cd538c55303e68cadf3f740716b3c3637898
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941885"
---
# JavaScript のバージョン情報  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

JavaScript サポートは、Microsoft Edge、Microsoft Store アプリ、およびさまざまなドキュメント モードによって、Internet Explorer \(IE\) によって異なります。 IE ドキュメント コードのバージョン管理の詳細については、「 [ドキュメントの互換性の定義」を参照してください](/previous-versions/windows/internet-explorer/ie-developer/compatibility/cc288325(v=vs.85))。  

次の表は、Internet Explorer、Microsoft Edge、Microsoft ストア アプリ間での JavaScript サポートをまとめたものです。  
  
> [!IMPORTANT]
> 明示的な機能 \(/)) は `about:flags` `Exp.` 、Windows 8 \(v8\) および Windows 10 \(v10\) アプリと Windows デスクトップ \(Win\) アプリと Windows デスクトップ \(Win\) と Windows Phone \(Phone\) との間で異なります。  
  
 | 言語要素 | クイロー、IE 6 Standard、IE 7 Standard | IE 8 Standards | IE 9 標準 | IE 10 標準 | IE 11 標準 | Microsoft Edge | アプリを保存する |  
 |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |  
| [__proto\\\ プロパティ (オブジェクト)](/scripting/javascript/reference/proto-property-object-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Windows): Y <br /> v8.1 (電話): Y |  
| [$1...$9 のプロパティ (RegExp)](/scripting/javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [0n プロパティ](/scripting/javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [abs 関数](/scripting/javascript/reference/math-abs-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acos 関数](/scripting/javascript/reference/math-acos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acosh 関数](/scripting/javascript/reference/math-acosh-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ActiveXObject オブジェクト](/scripting/javascript/reference/activexobject-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [割り当ての割り当て演算子 (+=](/scripting/javascript/reference/addition-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [追加演算子 (+)](/scripting/javascript/reference/addition-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [適用方法](/scripting/javascript/reference/apply-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [引数オブジェクト](/scripting/javascript/reference/arguments-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [引数プロパティ](/scripting/javascript/reference/arguments-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array オブジェクト](/scripting/javascript/reference/array-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array.from 関数 (配列)](/scripting/javascript/reference/array-from-function-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [Array.isArray 関数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [配列.of 関数 (配列)](/scripting/javascript/reference/array-of-function-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [ArrayBuffer オブジェクト](/scripting/javascript/reference/arraybuffer-object) | N | N | N | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [asin 関数](/scripting/javascript/reference/math-asin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Object.assign 関数 (Object)](/scripting/javascript/reference/object-assign-function-object-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [割り当て演算子 (=)](/scripting/javascript/reference/assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan 関数](/scripting/javascript/reference/math-atan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan2 関数](/scripting/javascript/reference/math-atan2-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atend メソッド](/scripting/javascript/reference/atend-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [バインド方法](/scripting/javascript/reference/bind-method-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [ビット単位で割り当て演算子 (&=)](/scripting/javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の AND 演算子 (&)](/scripting/javascript/reference/bitwise-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の左シフト演算子 (<\<)](/scripting/javascript/reference/bitwise-left-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の NOT 演算子 (~)](/scripting/javascript/reference/bitwise-not-operator-decrement-tilde-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位または割り当て演算子 (&#124;=)](/scripting/javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の OR 演算子 (&#124;)](/scripting/javascript/reference/bitwise-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の右シフト演算子 (>>)](/scripting/javascript/reference/bitwise-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の YOR 割り当て演算子 (^=)](/scripting/javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット単位の YOR 演算子 (^)](/scripting/javascript/reference/bitwise-xor-operator-decrement-hat-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [blink Method](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [太字の方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Boolean Object](/scripting/javascript/reference/boolean-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ブレーステートメント](/scripting/javascript/reference/break-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Call Method](/scripting/javascript/reference/call-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| ["callee/呼び出し" プロパティ](/scripting/javascript/reference/callee-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [呼び出し先のプロパティ](/scripting/javascript/reference/caller-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [catch Statement](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ceil 関数](/scripting/javascript/reference/math-ceil-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charAt メソッド](/scripting/javascript/reference/charat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charCodeAt メソッド](/scripting/javascript/reference/charcodeat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [クラス ステートメント](/scripting/javascript/reference/class-statement-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [codePointAt メソッド (文字列)](/scripting/javascript/reference/codepointat-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [コンマ演算子 (,)](/scripting/javascript/reference/comma-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [(単一行コメント ステートメント)](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [/*..\*/ (マルチライン コメント ステートメント)](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [比較演算子](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [コンパイル方法](/scripting/javascript/reference/compile-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [定数メソッド (配列)](/scripting/javascript/reference/concat-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [コンテキスト方法 (文字列)](/scripting/javascript/reference/concat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [条件付きコンパイル](/scripting/javascript/advanced/conditional-compilation-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件付きコンパイル変数](/scripting/javascript/advanced/conditional-compilation-variables-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件付き (Ternary) 演算子 (?:)](/scripting/javascript/reference/conditional-ternary-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [コンストラクター プロパティ](/scripting/javascript/reference/constructor-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [const ステートメント](/scripting/javascript/reference/const-statement-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Windows): Y <br /> v8.1 (電話): Y |  
| [continue ステートメント](/scripting/javascript/reference/continue-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [cos 関数](/scripting/javascript/reference/math-cos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数の作成](/scripting/javascript/reference/object-create-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [DataView オブジェクト](/scripting/javascript/reference/dataview-object) | N | N | N | Y | Y | Y | Y |  
| [Date Object](/scripting/javascript/reference/date-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [デバッグ オブジェクト](/scripting/javascript/reference/debug-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Debug.setNonUserCodeExceptions プロパティ](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [Debug.setNonUserCodeExceptions プロパティ](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [デバッガー ステートメント](/scripting/javascript/reference/debugger-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [decodeURI 関数](/scripting/javascript/reference/decodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [DecodeURIComponent 関数](/scripting/javascript/reference/decodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Decrement Operator (----](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [defineProperties 関数](/scripting/javascript/reference/object-defineproperties-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [defineProperty 関数](/scripting/javascript/reference/object-defineproperty-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [[演算子]](/scripting/javascript/reference/delete-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [説明プロパティ](/scripting/javascript/reference/description-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ディメンション方法](/scripting/javascript/reference/dimensions-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [割り当て演算子 (/=)](/scripting/javascript/reference/division-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [部演算子 (/)](/scripting/javascript/reference/division-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [do...while Statement](/scripting/javascript/reference/do-dot-dot-dot-while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [E Constant](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI 関数](/scripting/javascript/reference/encodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI Component 関数](/scripting/javascript/reference/encodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [エントリ メソッド (配列)](/scripting/javascript/reference/entries-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [列挙オブジェクト](/scripting/javascript/reference/enumerator-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [数値定数](/scripting/javascript/reference/number-constants-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [等値演算子 (== )](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [エラー オブジェクト](/scripting/javascript/reference/error-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [stack プロパティ (エラー)](/scripting/javascript/reference/stack-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [stackTraceLimit プロパティ (Error)](/scripting/javascript/reference/stacktracelimit-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [エスケープ関数](/scripting/javascript/reference/escape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [eval 関数](/scripting/javascript/reference/eval-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [実行方法](/scripting/javascript/reference/exec-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [すべての方法](/scripting/javascript/reference/every-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [exp 関数](/scripting/javascript/reference/math-exp-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fill Method (配列)](/scripting/javascript/reference/fill-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [フィルター方法](/scripting/javascript/reference/filter-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [最後のステートメント](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [findIndex メソッド (配列)](/scripting/javascript/reference/findindex-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [固定方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Float32Array オブジェクト](/scripting/javascript/reference/float32array-object) | N | N | N | Y | Y | Y | Y |  
| [Float64Array オブジェクト](/scripting/javascript/reference/float64array-object) | N | N | N | Y | Y | Y | Y |  
| [floor 関数](/scripting/javascript/reference/math-floor-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontcolor Method](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontsize Method](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [for Statement](/scripting/javascript/reference/for-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [forEach Method](/scripting/javascript/reference/foreach-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [などin ステートメント](/scripting/javascript/reference/for-dot-dot-dot-in-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [などof Statement](/scripting/javascript/reference/for-dot-dot-dot-of-statement-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Freeze 関数](/scripting/javascript/reference/object-freeze-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [fromCharCode 関数](/scripting/javascript/reference/string-fromcharcode-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fromCodePoint 関数](/scripting/javascript/reference/string-fromcodepoint-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [関数オブジェクト](/scripting/javascript/reference/function-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数ステートメント](/scripting/javascript/reference/function-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ジェナレーター](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [getDate メソッド](/scripting/javascript/reference/getdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getDay メソッド](/scripting/javascript/reference/getday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getFullYear メソッド](/scripting/javascript/reference/getfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getHours Method](/scripting/javascript/reference/gethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getItem メソッド](/scripting/javascript/reference/getitem-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMilliseconds Method](/scripting/javascript/reference/getmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMinutes Method](/scripting/javascript/reference/getminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMonth メソッド](/scripting/javascript/reference/getmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [GetObject 関数](/scripting/javascript/reference/getobject-function-javascript) | Y | Y | N | N | N | N | N |  
| [getOwnPropertyDescriptor 関数](/scripting/javascript/reference/object-getownpropertydescriptor-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [getOwnPropertyNames 関数](/scripting/javascript/reference/object-getownpropertynames-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getPrototypeOf 関数](/scripting/javascript/reference/object-getprototypeof-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getSeconds Method](/scripting/javascript/reference/getseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTime メソッド](/scripting/javascript/reference/gettime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTimezoneOffset メソッド](/scripting/javascript/reference/gettimezoneoffset-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDate メソッド](/scripting/javascript/reference/getutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDay メソッドを取得する](/scripting/javascript/reference/getutcday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCFullYear メソッド](/scripting/javascript/reference/getutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCHours Method](/scripting/javascript/reference/getutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [GETUTCMilliseconds Method](/scripting/javascript/reference/getutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMinutes Method](/scripting/javascript/reference/getutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMonth メソッドを取得する](/scripting/javascript/reference/getutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCSeconds Method](/scripting/javascript/reference/getutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getVarDate メソッド](/scripting/javascript/reference/getvardate-method-date-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [getYear メソッド](/scripting/javascript/reference/getyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [グローバル オブジェクト](/scripting/javascript/reference/global-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [グローバル プロパティ](/scripting/javascript/reference/global-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子より大きい (>)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子以上 (>=)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hasOwnProperty メソッド](/scripting/javascript/reference/hasownproperty-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [HTML タグメソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hypot 関数](/scripting/javascript/reference/math-hypot-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ID 演算子 (==)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [もし。。。else ステートメント](/scripting/javascript/reference/if-dot-dot-dot-else-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ignoreCase プロパティ](/scripting/javascript/reference/ignorecase-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [imul 関数](/scripting/javascript/reference/math-imul-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [In 演算子](/scripting/javascript/reference/in-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [includes Method (文字列)](/scripting/javascript/reference/includes-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Increment Operator (++)](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [インデックス プロパティ](/scripting/javascript/reference/index-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [indexOf メソッド (配列)](/scripting/javascript/reference/indexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [indexOf メソッド (文字列)](/scripting/javascript/reference/indexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Inequality Operator (!)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Infinity Constant](/scripting/javascript/reference/infinity-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [入力プロパティ ($_)](/scripting/javascript/reference/input-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [instanceof Operator](/scripting/javascript/reference/instanceof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Int8Array オブジェクト](/scripting/javascript/reference/int8array-object) | N | N | N | Y | Y | Y | Y |  
| [Int16Array オブジェクト](/scripting/javascript/reference/int16array-object) | N | N | N | Y | Y | Y | Y |  
| [Int32Array オブジェクト](/scripting/javascript/reference/int32array-object) | N | N | N | Y | Y | Y | Y |  
| [Intl.Collator オブジェクト](/scripting/javascript/reference/intl-collator-object-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Windows): Y <br /> v8.1 (電話): Y |  
| [Intl.DateTimeFormat オブジェクト](/scripting/javascript/reference/intl-datetimeformat-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [Intl.NumberFormat オブジェクト](/scripting/javascript/reference/intl-numberformat-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [isFinite 関数](/scripting/javascript/reference/isfinite-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isArray 関数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsExtensible 関数](/scripting/javascript/reference/object-isextensible-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isFrozen 関数](/scripting/javascript/reference/object-isfrozen-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isInteger 関数](/scripting/javascript/reference/number-isinteger-function-number-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [isNaN 関数](/scripting/javascript/reference/isnan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isNaN 関数 (数値)](/scripting/javascript/reference/number-isnan-function-number-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ISO 日付形式](/scripting/javascript/date-and-time-strings-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsPrototypeOf メソッド](/scripting/javascript/reference/isprototypeof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isSealed 関数](/scripting/javascript/reference/object-issealed-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [italics Method](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [イタリア](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [アイテムの方法](/scripting/javascript/reference/item-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [参加方法](/scripting/javascript/reference/join-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON オブジェクト](/scripting/javascript/reference/json-object-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [Keys 関数](/scripting/javascript/reference/object-keys-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [キーを押しながらメソッド (配列)](/scripting/javascript/reference/keys-method-array-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ラベル付きステートメント](/scripting/javascript/reference/labeled-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndex プロパティ](/scripting/javascript/reference/lastindex-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndexOf メソッド (配列)](/scripting/javascript/reference/lastindexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [lastIndexOf メソッド (文字列)](/scripting/javascript/reference/lastindexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastMatch プロパティ ($&)](/scripting/javascript/reference/lastmatch-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastParen プロパティ ($+)](/scripting/javascript/reference/lastparen-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lbound Method](/scripting/javascript/reference/lbound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [leftContext プロパティ ($')](/scripting/javascript/reference/leftcontext-property-dollar-grave-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [左 Shift 割り当て演算子 (<<=)](/scripting/javascript/reference/left-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length プロパティ (引数)](/scripting/javascript/reference/length-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length Property (配列)](/scripting/javascript/reference/length-property-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length Property (関数)](/scripting/javascript/reference/length-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length Property (String)](/scripting/javascript/reference/length-property-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [オペレーターより小さい (<)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演 <算子以下](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [let ステートメント](/scripting/javascript/reference/let-statement-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [リンク方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN2 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN10 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [localeCompare メソッド](/scripting/javascript/reference/localecompare-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [log 関数](/scripting/javascript/reference/math-log-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG2E 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG10E 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理算演算子 (&&)](/scripting/javascript/reference/logical-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理 NOT 演算子 (!)](/scripting/javascript/reference/logical-not-operator-decrement-exclpt-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理演算子 (&#124;&#124;)](/scripting/javascript/reference/logical-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [マップ方法](/scripting/javascript/reference/map-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Map オブジェクト](/scripting/javascript/reference/map-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [一致方法](/scripting/javascript/reference/match-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [数式オブジェクト](/scripting/javascript/reference/math-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [max 関数](/scripting/javascript/reference/math-max-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MAX_VALUE定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [message Property](/scripting/javascript/reference/message-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [min 関数](/scripting/javascript/reference/math-min-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MIN_VALUE定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [残りの割り当て演算子 (%)](/scripting/javascript/reference/modulus-assignment-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [残りの演算子 (%)](/scripting/javascript/reference/modulus-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveFirst Method](/scripting/javascript/reference/movefirst-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveNext メソッド](/scripting/javascript/reference/movenext-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [マルチライン プロパティ](/scripting/javascript/reference/multiline-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乗算の割り当て演算子 (*=)](/scripting/javascript/reference/multiplication-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乗算演算子 (*)](/scripting/javascript/reference/multiplication-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| ["Name/名前" プロパティ](/scripting/javascript/reference/name-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 定数 (グローバル)](/scripting/javascript/reference/nan-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 定数 (数値)](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NEGATIVE_INFINITY定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [新しい演算子](/scripting/javascript/reference/new-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Nonidentity 演算子 (!=)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Now 関数](/scripting/javascript/reference/date-now-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Number Object](/scripting/javascript/reference/number-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [数値プロパティ](https://developer.mozilla.org/docs/Web/JavaScript/Microsoft_Extensions/Error.number) | Y | Y | Y | Y | Y | Y | Y |  
| [オブジェクト](/scripting/javascript/reference/object-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子のプレゼンス](/scripting/javascript/operator-subtractprecedence-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Date.parse 関数](/scripting/javascript/reference/date-parse-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON.parse 関数](/scripting/javascript/reference/json-parse-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [parseFloat 関数](/scripting/javascript/reference/parsefloat-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [parseInt 関数](/scripting/javascript/reference/parseint-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [PI 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ポップアップ方法](/scripting/javascript/reference/pop-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [POSITIVE_INFINITY定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [pow 関数](/scripting/javascript/reference/math-pow-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [preventExtensions 関数](/scripting/javascript/reference/object-preventextensions-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Promise オブジェクト](/scripting/javascript/reference/promise-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [プロトタイプ プロパティ](/scripting/javascript/reference/prototype-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [propertyIsEnumerable Method](/scripting/javascript/reference/propertyisenumerable-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [プロキシ オブジェクト](/scripting/javascript/reference/proxy-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [プッシュメソッド](/scripting/javascript/reference/push-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ランダマ関数](/scripting/javascript/reference/math-random-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [raw 関数](/scripting/javascript/reference/string-raw-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [方法の再開](/scripting/javascript/reference/reduce-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [reduceRight メソッドを再度下げる](/scripting/javascript/reference/reduceright-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [RegExp オブジェクト](/scripting/javascript/reference/regexp-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正式表現オブジェクト](/scripting/javascript/reference/regular-expression-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正表現の構文](https://msdn.microsoft.com/ab0766e1-7037-45ed-aa23-706f58358c0e) | Y | Y | Y | Y | Y | Y | Y |  
| [正正表現 /y フラグ](/scripting/javascript/reference/regular-expression-object-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [繰り返し方法 (文字列)](/scripting/javascript/reference/repeat-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [置き換える方法](/scripting/javascript/reference/replace-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [return ステートメント](/scripting/javascript/reference/return-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [逆方向の方法](/scripting/javascript/reference/reverse-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [rightContext プロパティ ($')](/scripting/javascript/reference/rightcontext-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [右シフトの割り当て演算子 (>>=)](/scripting/javascript/reference/right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Round 関数](/scripting/javascript/reference/math-round-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngine 関数](/scripting/javascript/reference/scriptengine-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineBuildVersion 関数](/scripting/javascript/reference/scriptenginebuildversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMajorVersion 関数](/scripting/javascript/reference/scriptenginemajorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMinorVersion 関数](/scripting/javascript/reference/scriptengineminorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [seal 関数](/scripting/javascript/reference/object-seal-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [検索方法](/scripting/javascript/reference/search-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [オブジェクトの設定](/scripting/javascript/reference/set-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [setDate メソッド](/scripting/javascript/reference/setdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setFullYear メソッド](/scripting/javascript/reference/setfullyear-method-date-javascript) |  | Y | Y | Y | Y | Y | Y |  
| [setHours Method](/scripting/javascript/reference/sethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMilliseconds Method](/scripting/javascript/reference/setmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMinutes Method](/scripting/javascript/reference/setminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMonth メソッド](/scripting/javascript/reference/setmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setSeconds Method](/scripting/javascript/reference/setseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setTime メソッド](/scripting/javascript/reference/settime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCDate メソッドを設定する](/scripting/javascript/reference/setutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCFullYear メソッドを設定する](/scripting/javascript/reference/setutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCHours Method](/scripting/javascript/reference/setutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMilliseconds Method](/scripting/javascript/reference/setutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMinutes Method](/scripting/javascript/reference/setutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMonth Method](/scripting/javascript/reference/setutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCSeconds Method](/scripting/javascript/reference/setutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setYear メソッド](/scripting/javascript/reference/setyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [shift Method](/scripting/javascript/reference/shift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sin 関数](/scripting/javascript/reference/math-sin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [スライス メソッド (配列)](/scripting/javascript/reference/slice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [スライス メソッド (文字列)](/scripting/javascript/reference/slice-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [小規模な方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [一部の方法](/scripting/javascript/reference/some-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [並べ替え方法](/scripting/javascript/reference/sort-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ソース プロパティ](/scripting/javascript/reference/source-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [splice メソッド](/scripting/javascript/reference/splice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [分割メソッド](/scripting/javascript/reference/split-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [sqrt 関数](/scripting/javascript/reference/math-sqrt-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT1_2定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT2 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [制限付きダイレクトを使用する](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [付リク方法](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [String オブジェクト](/scripting/javascript/reference/string-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON.stringify 関数](/scripting/javascript/reference/json-stringify-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [サブメソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [サブストラッシーの方法](/scripting/javascript/reference/substr-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [サブ文字列のメソッド](/scripting/javascript/reference/substring-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [減算割り当て演算子 (-=)](/scripting/javascript/reference/subtraction-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [減算演算子 (-)](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sup Method](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [スイッチメント](/scripting/javascript/reference/switch-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Symbol オブジェクト](/scripting/javascript/reference/symbol-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [tan 関数](/scripting/javascript/reference/math-tan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [テンプレート文字列](/scripting/javascript/advanced/template-strings-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [テスト方法](/scripting/javascript/reference/test-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [この声明](/scripting/javascript/reference/this-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [スロー ステートメント](/scripting/javascript/reference/throw-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toArray メソッド](/scripting/javascript/reference/toarray-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toDateString Method](/scripting/javascript/reference/todatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toExponential Method](/scripting/javascript/reference/toexponential-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toFixed Method](/scripting/javascript/reference/tofixed-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toGMTString メソッド](/scripting/javascript/reference/togmtstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toISOString Method](/scripting/javascript/reference/toisostring-method-date-javascript) | N | N | Y | Y | Y | Y | Y |  
| [toJSON メソッド](/scripting/javascript/reference/tojson-method-date-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [toLocaleDateString Method](/scripting/javascript/reference/tolocaledatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleLowercase Method](/scripting/javascript/reference/tolocalelowercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleString メソッド](/scripting/javascript/reference/tolocalestring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleTimeString Method](/scripting/javascript/reference/tolocaletimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleUppercase Method](/scripting/javascript/reference/tolocaleuppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLowerCase Method](/scripting/javascript/reference/tolowercase-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toPrecision Method](/scripting/javascript/reference/toprecision-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toString メソッド](/scripting/javascript/reference/tostring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toTimeString メソッド](/scripting/javascript/reference/totimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUpperCase Method](/scripting/javascript/reference/touppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUTCString メソッド](/scripting/javascript/reference/toutcstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [トリミング方法](/scripting/javascript/reference/trim-method-string-javascript) | N | N | Y | Y | Y | Y | Y |  
| [try Statement](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [種類の演算子](/scripting/javascript/reference/typeof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ubound Method](/scripting/javascript/reference/ubound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Uint8Array オブジェクト](/scripting/javascript/reference/uint8array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint16Array オブジェクト](/scripting/javascript/reference/uint16array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint32Array オブジェクト](/scripting/javascript/reference/uint32array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint8ClampedArray オブジェクト](/scripting/javascript/reference/uint8clampedarray-object-javascript) | N | N | N | N | Y | Y | v8: No <br /> v8.1 (Win): はい <br /> v8.1 (電話):いいえ <br /> v10: Y |  
| [Unary Negation Operator (-)](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [未定義定数](/scripting/javascript/reference/undefined-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [unescape 関数](/scripting/javascript/reference/unescape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Unicode Code ポイント エスケープ文字](/scripting/javascript/advanced/special-characters-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [unshift Method](/scripting/javascript/reference/unshift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Unsigned Right Shift assignment operator (>>>=)](/scripting/javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [符号なしシフト演算子 (>>>)](/scripting/javascript/reference/unsigned-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [制限付きダイレクトを使用する](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [UTC 関数](/scripting/javascript/reference/date-utc-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [valueOf メソッド](/scripting/javascript/reference/valueof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [値のメソッド (配列)](/scripting/javascript/reference/values-method-array-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [var Statement](/scripting/javascript/reference/var-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [VBArray オブジェクト](/scripting/javascript/reference/vbarray-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [void 演算子](/scripting/javascript/reference/void-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WeakMap オブジェクト](/scripting/javascript/reference/weakmap-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [WeakSet オブジェクト](/scripting/javascript/reference/weakset-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [while Statement](/scripting/javascript/reference/while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WinRTError オブジェクト](/scripting/javascript/reference/winrterror-object-javascript) | N | N | N | Y | Y | Y | Y |  
| [with Statement](/scripting/javascript/reference/with-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [write 関数](/scripting/javascript/reference/debug-write-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [writeln 関数](/scripting/javascript/reference/debug-writeln-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
  
 \* DOM オブジェクトはサポートしていますが、ユーザー定義オブジェクトはサポートしていません。  属 `enumerable` `configurable` 性と属性を指定できますが、使用されません。  
