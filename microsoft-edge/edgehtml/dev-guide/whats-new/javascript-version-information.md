---
title: JavaScript のバージョン情報
description: Microsoft Edge、Microsoft Store アプリ、および Microsoft Store アプリ全体で JavaScript サポートを比較Internet Explorer
ms.prod: microsoft-edge
ms.topic: language-reference
author: MSEdgeTeam
ms.author: msedgedevrel
keywords: edge, ie, chakra, jscript, wwa, ストア アプリ
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5f420b0546f623b5b1c1d43a7b7237a888f97715
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234694"
---
# JavaScript のバージョン情報  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

JavaScript のサポートは、Microsoft Edge、Microsoft Store アプリ、および Internet Explorer \(IE\) のドキュメント モードによって異なります。 IE ドキュメント コードのバージョン管理の詳細については、「ドキュメントの互換性の [定義」を参照してください](/previous-versions/windows/internet-explorer/ie-developer/compatibility/cc288325(v=vs.85))。  

次の表は、アプリ、Microsoft Edge、Microsoft Store Internet Explorer JavaScript のサポートをまとめたものです。  
  
> [!IMPORTANT]
> 試験的な機能 `about:flags` \(\から有効) は、 `Exp` 場合によっては、ストア アプリのサポートは、示されている Windows 8 \(v8\) アプリと Windows 10 \(v10\) アプリ、Windows デスクトップ \(Win\) と Windows Phone \(Phone\) によって異なります。  
  
 | Language 要素 | Quirks、IE 6 Standards、IE 7 Standards | IE 8 の標準 | IE 9 標準 | IE 10 の標準 | IE 11 の標準 | Microsoft Edge | ストア アプリ |  
 |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |  
| [__proto\_\_ プロパティ (オブジェクト)](/scripting/javascript/reference/proto-property-object-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Win): Y <br /> v8.1 (電話): Y |  
| [$1...$9 プロパティ (RegExp)](/scripting/javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [0n プロパティ](/scripting/javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [abs 関数](/scripting/javascript/reference/math-abs-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acos 関数](/scripting/javascript/reference/math-acos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [acosh 関数](/scripting/javascript/reference/math-acosh-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ActiveXObject オブジェクト](/scripting/javascript/reference/activexobject-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [加算代入演算子 (+=)](/scripting/javascript/reference/addition-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [加算演算子 (+)](/scripting/javascript/reference/addition-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [apply メソッド](/scripting/javascript/reference/apply-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [arguments オブジェクト](/scripting/javascript/reference/arguments-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [arguments プロパティ](/scripting/javascript/reference/arguments-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array オブジェクト](/scripting/javascript/reference/array-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Array.from 関数 (配列)](/scripting/javascript/reference/array-from-function-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [Array.isArray 関数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Array.of 関数 (Array)](/scripting/javascript/reference/array-of-function-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [ArrayBuffer オブジェクト](/scripting/javascript/reference/arraybuffer-object) | N | N | N | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [asin 関数](/scripting/javascript/reference/math-asin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Object.assign 関数 (オブジェクト)](/scripting/javascript/reference/object-assign-function-object-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [割り当て演算子 (=)](/scripting/javascript/reference/assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan 関数](/scripting/javascript/reference/math-atan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atan2 関数](/scripting/javascript/reference/math-atan2-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [atEnd メソッド](/scripting/javascript/reference/atend-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [bind メソッド](/scripting/javascript/reference/bind-method-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [ビット演算子 AND 代入演算子 (&=)](/scripting/javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 AND 演算子 (&)](/scripting/javascript/reference/bitwise-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット型左シフト演算子 (<\<)](/scripting/javascript/reference/bitwise-left-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 (~)](/scripting/javascript/reference/bitwise-not-operator-decrement-tilde-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 OR 代入演算子 (&#124;=)](/scripting/javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 (&#124;)](/scripting/javascript/reference/bitwise-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット型右シフト演算子 (>>)](/scripting/javascript/reference/bitwise-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 YOR 代入演算子 (^=)](/scripting/javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ビット演算子 (^)](/scripting/javascript/reference/bitwise-xor-operator-decrement-hat-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [blink メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [bold メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Boolean オブジェクト](/scripting/javascript/reference/boolean-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [break ステートメント](/scripting/javascript/reference/break-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [call メソッド](/scripting/javascript/reference/call-method-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [callee プロパティ](/scripting/javascript/reference/callee-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [caller プロパティ](/scripting/javascript/reference/caller-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [catch ステートメント](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ceil 関数](/scripting/javascript/reference/math-ceil-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charAt メソッド](/scripting/javascript/reference/charat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [charCodeAt メソッド](/scripting/javascript/reference/charcodeat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [class ステートメント](/scripting/javascript/reference/class-statement-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [codePointAt メソッド (文字列)](/scripting/javascript/reference/codepointat-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [コンマ演算子 (,)](/scripting/javascript/reference/comma-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [(1 行の Comment ステートメント)](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [/*..\*/ (Multiline Comment ステートメント)](/scripting/javascript/reference/comment-statements-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [比較演算子](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [compile メソッド](/scripting/javascript/reference/compile-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [concat メソッド (Array)](/scripting/javascript/reference/concat-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [concat メソッド (String)](/scripting/javascript/reference/concat-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [条件付きコンパイル](/scripting/javascript/advanced/conditional-compilation-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件付きコンパイル変数](/scripting/javascript/advanced/conditional-compilation-variables-javascript) | Y | Y | Y | Y | N | N | N |  
| [条件付き (3 項) 演算子 (?:)](/scripting/javascript/reference/conditional-ternary-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [constructor プロパティ](/scripting/javascript/reference/constructor-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [const ステートメント](/scripting/javascript/reference/const-statement-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Win): Y <br /> v8.1 (電話): Y |  
| [continue ステートメント](/scripting/javascript/reference/continue-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [cos 関数](/scripting/javascript/reference/math-cos-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [create 関数](/scripting/javascript/reference/object-create-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [DataView オブジェクト](/scripting/javascript/reference/dataview-object) | N | N | N | Y | Y | Y | Y |  
| [Date オブジェクト](/scripting/javascript/reference/date-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Debug オブジェクト](/scripting/javascript/reference/debug-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Debug.setNonUserCodeExceptions プロパティ](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [Debug.setNonUserCodeExceptions プロパティ](/scripting/javascript/reference/debug-setnonusercodeexceptions-property) | N | N | N | Y | Y | Y | Y |  
| [debugger ステートメント](/scripting/javascript/reference/debugger-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [decodeURI 関数](/scripting/javascript/reference/decodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [DecodeURIComponent 関数](/scripting/javascript/reference/decodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [デクメント演算子 (--)](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [defineProperties 関数](/scripting/javascript/reference/object-defineproperties-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [defineProperty 関数](/scripting/javascript/reference/object-defineproperty-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [delete 演算子](/scripting/javascript/reference/delete-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [description プロパティ](/scripting/javascript/reference/description-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [dimensions メソッド](/scripting/javascript/reference/dimensions-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [除算割り当て演算子 (/=)](/scripting/javascript/reference/division-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Division 演算子 (/)](/scripting/javascript/reference/division-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [do...while ステートメント](/scripting/javascript/reference/do-dot-dot-dot-while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [E 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI 関数](/scripting/javascript/reference/encodeuri-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [encodeURI コンポーネント関数](/scripting/javascript/reference/encodeuricomponent-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [entries メソッド (Array)](/scripting/javascript/reference/entries-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [Enumerator オブジェクト](/scripting/javascript/reference/enumerator-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [数値定数](/scripting/javascript/reference/number-constants-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [等号演算子 (===)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Error オブジェクト](/scripting/javascript/reference/error-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [stack プロパティ (Error)](/scripting/javascript/reference/stack-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [stackTraceLimit プロパティ (Error)](/scripting/javascript/reference/stacktracelimit-property-error-javascript) | N | N | N | Y | Y | Y | Y |  
| [escape 関数](/scripting/javascript/reference/escape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [eval 関数](/scripting/javascript/reference/eval-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [exec メソッド](/scripting/javascript/reference/exec-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [every メソッド](/scripting/javascript/reference/every-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [exp 関数](/scripting/javascript/reference/math-exp-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fill メソッド (Array)](/scripting/javascript/reference/fill-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [filter メソッド](/scripting/javascript/reference/filter-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [finally ステートメント](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [findIndex メソッド (Array)](/scripting/javascript/reference/findindex-method-array-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [fixed メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Float32Array オブジェクト](/scripting/javascript/reference/float32array-object) | N | N | N | Y | Y | Y | Y |  
| [Float64Array オブジェクト](/scripting/javascript/reference/float64array-object) | N | N | N | Y | Y | Y | Y |  
| [floor 関数](/scripting/javascript/reference/math-floor-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontcolor メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fontsize メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [for ステートメント](/scripting/javascript/reference/for-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [forEach メソッド](/scripting/javascript/reference/foreach-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [for...in ステートメント](/scripting/javascript/reference/for-dot-dot-dot-in-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [for...of ステートメント](/scripting/javascript/reference/for-dot-dot-dot-of-statement-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [freeze 関数](/scripting/javascript/reference/object-freeze-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [fromCharCode 関数](/scripting/javascript/reference/string-fromcharcode-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [fromCodePoint 関数](/scripting/javascript/reference/string-fromcodepoint-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Function オブジェクト](/scripting/javascript/reference/function-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [function ステートメント](/scripting/javascript/reference/function-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ジェネレーター](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [getDate メソッド](/scripting/javascript/reference/getdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getDay メソッド](/scripting/javascript/reference/getday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getFullYear メソッド](/scripting/javascript/reference/getfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getHours メソッド](/scripting/javascript/reference/gethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getItem メソッド](/scripting/javascript/reference/getitem-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMilliseconds メソッド](/scripting/javascript/reference/getmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMinutes メソッド](/scripting/javascript/reference/getminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getMonth メソッド](/scripting/javascript/reference/getmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [GetObject 関数](/scripting/javascript/reference/getobject-function-javascript) | Y | Y | N | N | N | N | N |  
| [getOwnPropertyDescriptor 関数](/scripting/javascript/reference/object-getownpropertydescriptor-function-javascript) | N | Y* | Y | Y | Y | Y | Y |  
| [getOwnPropertyNames 関数](/scripting/javascript/reference/object-getownpropertynames-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getPrototypeOf 関数](/scripting/javascript/reference/object-getprototypeof-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [getSeconds メソッド](/scripting/javascript/reference/getseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTime メソッド](/scripting/javascript/reference/gettime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getTimezoneOffset メソッド](/scripting/javascript/reference/gettimezoneoffset-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDate メソッド](/scripting/javascript/reference/getutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCDay メソッド](/scripting/javascript/reference/getutcday-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCFullYear メソッド](/scripting/javascript/reference/getutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCHours メソッド](/scripting/javascript/reference/getutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMilliseconds メソッド](/scripting/javascript/reference/getutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMinutes メソッド](/scripting/javascript/reference/getutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCMonth メソッド](/scripting/javascript/reference/getutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getUTCSeconds メソッド](/scripting/javascript/reference/getutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [getVarDate メソッド](/scripting/javascript/reference/getvardate-method-date-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [getYear メソッド](/scripting/javascript/reference/getyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Global オブジェクト](/scripting/javascript/reference/global-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [global プロパティ](/scripting/javascript/reference/global-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子より大きい (>)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子以上 (>=)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hasOwnProperty メソッド](/scripting/javascript/reference/hasownproperty-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [HTML Tag メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [hypot 関数](/scripting/javascript/reference/math-hypot-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Identity 演算子 (====)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [もし。。。else ステートメント](/scripting/javascript/reference/if-dot-dot-dot-else-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ignoreCase プロパティ](/scripting/javascript/reference/ignorecase-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [imul 関数](/scripting/javascript/reference/math-imul-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [In 演算子](/scripting/javascript/reference/in-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [includes メソッド (文字列)](/scripting/javascript/reference/includes-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Increment 演算子 (++)](/scripting/javascript/reference/increment-and-decrement-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [index プロパティ](/scripting/javascript/reference/index-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [indexOf メソッド (Array)](/scripting/javascript/reference/indexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [indexOf メソッド (文字列)](/scripting/javascript/reference/indexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [等しくない演算子 (!=)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [無限大定数](/scripting/javascript/reference/infinity-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [input プロパティ ($_)](/scripting/javascript/reference/input-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [instanceof 演算子](/scripting/javascript/reference/instanceof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Int8Array オブジェクト](/scripting/javascript/reference/int8array-object) | N | N | N | Y | Y | Y | Y |  
| [Int16Array オブジェクト](/scripting/javascript/reference/int16array-object) | N | N | N | Y | Y | Y | Y |  
| [Int32Array オブジェクト](/scripting/javascript/reference/int32array-object) | N | N | N | Y | Y | Y | Y |  
| [Intl.Collator オブジェクト](/scripting/javascript/reference/intl-collator-object-javascript) | N | N | N | N | Y | Y | v8 (Win): N <br /> v8.1 (Win): Y <br /> v8.1 (電話): Y |  
| [Intl.DateTimeFormat オブジェクト](/scripting/javascript/reference/intl-datetimeformat-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [Intl.NumberFormat オブジェクト](/scripting/javascript/reference/intl-numberformat-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [isFinite 関数](/scripting/javascript/reference/isfinite-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isArray 関数](/scripting/javascript/reference/array-isarray-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsExtensible 関数](/scripting/javascript/reference/object-isextensible-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isFrozen 関数](/scripting/javascript/reference/object-isfrozen-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [isInteger 関数](/scripting/javascript/reference/number-isinteger-function-number-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [isNaN 関数](/scripting/javascript/reference/isnan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isNaN 関数 (Number)](/scripting/javascript/reference/number-isnan-function-number-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [ISO 日付形式](/scripting/javascript/date-and-time-strings-javascript) | N | N | Y | Y | Y | Y | Y |  
| [IsPrototypeOf メソッド](/scripting/javascript/reference/isprototypeof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [isSealed 関数](/scripting/javascript/reference/object-issealed-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [italics メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [反復子](/scripting/javascript/advanced/iterators-and-generators-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [item メソッド](/scripting/javascript/reference/item-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [join メソッド](/scripting/javascript/reference/join-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON オブジェクト](/scripting/javascript/reference/json-object-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [keys 関数](/scripting/javascript/reference/object-keys-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [keys メソッド (Array)](/scripting/javascript/reference/keys-method-array-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [Labeled ステートメント](/scripting/javascript/reference/labeled-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndex プロパティ](/scripting/javascript/reference/lastindex-property-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastIndexOf メソッド (Array)](/scripting/javascript/reference/lastindexof-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [lastIndexOf メソッド (文字列)](/scripting/javascript/reference/lastindexof-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastMatch プロパティ ($&)](/scripting/javascript/reference/lastmatch-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lastParen プロパティ ($+)](/scripting/javascript/reference/lastparen-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [lbound メソッド](/scripting/javascript/reference/lbound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [leftContext プロパティ ($')](/scripting/javascript/reference/leftcontext-property-dollar-grave-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [左シフト割り当て演算子 (<<=)](/scripting/javascript/reference/left-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length プロパティ (引数)](/scripting/javascript/reference/length-property-arguments-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length プロパティ (Array)](/scripting/javascript/reference/length-property-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length プロパティ (Function)](/scripting/javascript/reference/length-property-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [length プロパティ (String)](/scripting/javascript/reference/length-property-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子より小さい (<)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子以下 (<=)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [let ステートメント](/scripting/javascript/reference/let-statement-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [link メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN2 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LN10 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [localeCompare メソッド](/scripting/javascript/reference/localecompare-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [log 関数](/scripting/javascript/reference/math-log-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG2E 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [LOG10E 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理 AND 演算子 (&&)](/scripting/javascript/reference/logical-and-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理 NOT 演算子 (!)](/scripting/javascript/reference/logical-not-operator-decrement-exclpt-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [論理 OR 演算子 (&#124;&#124;)](/scripting/javascript/reference/logical-or-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [map メソッド](/scripting/javascript/reference/map-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Map オブジェクト](/scripting/javascript/reference/map-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [match メソッド](/scripting/javascript/reference/match-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Math オブジェクト](/scripting/javascript/reference/math-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [max 関数](/scripting/javascript/reference/math-max-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MAX_VALUE定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [message プロパティ](/scripting/javascript/reference/message-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [min 関数](/scripting/javascript/reference/math-min-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [MIN_VALUE定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [残りの代入演算子 (%=)](/scripting/javascript/reference/modulus-assignment-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [残りの演算子 (%)](/scripting/javascript/reference/modulus-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveFirst メソッド](/scripting/javascript/reference/movefirst-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [moveNext メソッド](/scripting/javascript/reference/movenext-method-enumerator-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [multiline プロパティ](/scripting/javascript/reference/multiline-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乗算代入演算子 (*=)](/scripting/javascript/reference/multiplication-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [乗算演算子 (*)](/scripting/javascript/reference/multiplication-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [name プロパティ](/scripting/javascript/reference/name-property-error-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 定数 (グローバル)](/scripting/javascript/reference/nan-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NaN 定数 (数値)](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [NEGATIVE_INFINITY定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [新しい演算子](/scripting/javascript/reference/new-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Nonidentity 演算子 (!==)](/scripting/javascript/reference/comparison-operators-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [now 関数](/scripting/javascript/reference/date-now-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Number オブジェクト](/scripting/javascript/reference/number-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [number プロパティ](https://developer.mozilla.org/docs/Web/JavaScript/Microsoft_Extensions/Error.number) | Y | Y | Y | Y | Y | Y | Y |  
| [オブジェクト オブジェクト](/scripting/javascript/reference/object-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [演算子の優先順位](/scripting/javascript/operator-subtractprecedence-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Date.parse 関数](/scripting/javascript/reference/date-parse-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON.parse 関数](/scripting/javascript/reference/json-parse-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [parseFloat 関数](/scripting/javascript/reference/parsefloat-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [parseInt 関数](/scripting/javascript/reference/parseint-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [PI 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [pop メソッド](/scripting/javascript/reference/pop-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [POSITIVE_INFINITY定数](/scripting/javascript/reference/number-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [pow 関数](/scripting/javascript/reference/math-pow-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [preventExtensions 関数](/scripting/javascript/reference/object-preventextensions-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [Promise オブジェクト](/scripting/javascript/reference/promise-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [prototype プロパティ](/scripting/javascript/reference/prototype-property-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [propertyIsEnumerable メソッド](/scripting/javascript/reference/propertyisenumerable-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Proxy オブジェクト](/scripting/javascript/reference/proxy-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [push メソッド](/scripting/javascript/reference/push-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [random 関数](/scripting/javascript/reference/math-random-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [raw 関数](/scripting/javascript/reference/string-raw-function-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [reduce メソッド](/scripting/javascript/reference/reduce-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [reduceRight メソッド](/scripting/javascript/reference/reduceright-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [RegExp オブジェクト](/scripting/javascript/reference/regexp-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正規表現オブジェクト](/scripting/javascript/reference/regular-expression-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [正規表現構文](https://msdn.microsoft.com/ab0766e1-7037-45ed-aa23-706f58358c0e) | Y | Y | Y | Y | Y | Y | Y |  
| [正規表現 /y フラグ](/scripting/javascript/reference/regular-expression-object-javascript) | N | N | N | N | N | 有効期限 | v8.1: N <br /> v10: Exp. |  
| [repeat メソッド (String)](/scripting/javascript/reference/repeat-method-string-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [replace メソッド](/scripting/javascript/reference/replace-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | N | v8.1: N <br /> v10: Y |  
| [return ステートメント](/scripting/javascript/reference/return-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [reverse メソッド](/scripting/javascript/reference/reverse-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [rightContext プロパティ ($')](/scripting/javascript/reference/rightcontext-property-dollar-regexp-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Right Shift Assignment Operator (>>=)](/scripting/javascript/reference/right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [round 関数](/scripting/javascript/reference/math-round-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngine 関数](/scripting/javascript/reference/scriptengine-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineBuildVersion 関数](/scripting/javascript/reference/scriptenginebuildversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMajorVersion 関数](/scripting/javascript/reference/scriptenginemajorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ScriptEngineMinorVersion 関数](/scripting/javascript/reference/scriptengineminorversion-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [seal 関数](/scripting/javascript/reference/object-seal-function-javascript) | N | N | Y | Y | Y | Y | Y |  
| [search メソッド](/scripting/javascript/reference/search-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Set オブジェクト](/scripting/javascript/reference/set-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [setDate メソッド](/scripting/javascript/reference/setdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setFullYear メソッド](/scripting/javascript/reference/setfullyear-method-date-javascript) |  | Y | Y | Y | Y | Y | Y |  
| [setHours メソッド](/scripting/javascript/reference/sethours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMilliseconds メソッド](/scripting/javascript/reference/setmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMinutes メソッド](/scripting/javascript/reference/setminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setMonth メソッド](/scripting/javascript/reference/setmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setSeconds メソッド](/scripting/javascript/reference/setseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setTime メソッド](/scripting/javascript/reference/settime-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCDate メソッド](/scripting/javascript/reference/setutcdate-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCFullYear メソッド](/scripting/javascript/reference/setutcfullyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCHours メソッド](/scripting/javascript/reference/setutchours-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMilliseconds メソッド](/scripting/javascript/reference/setutcmilliseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMinutes メソッド](/scripting/javascript/reference/setutcminutes-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCMonth メソッド](/scripting/javascript/reference/setutcmonth-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setUTCSeconds メソッド](/scripting/javascript/reference/setutcseconds-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [setYear メソッド](/scripting/javascript/reference/setyear-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [shift メソッド](/scripting/javascript/reference/shift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sin 関数](/scripting/javascript/reference/math-sin-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [slice メソッド (Array)](/scripting/javascript/reference/slice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [slice メソッド (文字列)](/scripting/javascript/reference/slice-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [small メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [some メソッド](/scripting/javascript/reference/some-method-array-javascript) | N | N | Y | Y | Y | Y | Y |  
| [sort メソッド](/scripting/javascript/reference/sort-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [source プロパティ](/scripting/javascript/reference/source-property-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [method](/scripting/javascript/reference/splice-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [split メソッド](/scripting/javascript/reference/split-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [関数](/scripting/javascript/functions-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [sqrt 関数](/scripting/javascript/reference/math-sqrt-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT1_2定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [SQRT2 定数](/scripting/javascript/reference/math-constants-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [strict ディレクティブの使用](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [strike メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [String オブジェクト](/scripting/javascript/reference/string-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [JSON.stringify 関数](/scripting/javascript/reference/json-stringify-function-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [sub メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [substr メソッド](/scripting/javascript/reference/substr-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [substring メソッド](/scripting/javascript/reference/substring-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [減算割り当て演算子 (-=)](/scripting/javascript/reference/subtraction-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [減算演算子 (-)](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [sup メソッド](/scripting/javascript/reference/html-tag-methods-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [switch ステートメント](/scripting/javascript/reference/switch-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Symbol オブジェクト](/scripting/javascript/reference/symbol-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [tan 関数](/scripting/javascript/reference/math-tan-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [テンプレート文字列](/scripting/javascript/advanced/template-strings-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [test メソッド](/scripting/javascript/reference/test-method-regular-expression-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [このステートメント](/scripting/javascript/reference/this-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [throw ステートメント](/scripting/javascript/reference/throw-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toArray メソッド](/scripting/javascript/reference/toarray-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toDateString メソッド](/scripting/javascript/reference/todatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toExponential メソッド](/scripting/javascript/reference/toexponential-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toFixed メソッド](/scripting/javascript/reference/tofixed-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toGMTString メソッド](/scripting/javascript/reference/togmtstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toISOString メソッド](/scripting/javascript/reference/toisostring-method-date-javascript) | N | N | Y | Y | Y | Y | Y |  
| [toJSON メソッド](/scripting/javascript/reference/tojson-method-date-javascript) | N | Y | Y | Y | Y | Y | Y |  
| [toLocaleDateString メソッド](/scripting/javascript/reference/tolocaledatestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleLowercase メソッド](/scripting/javascript/reference/tolocalelowercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleString メソッド](/scripting/javascript/reference/tolocalestring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleTimeString メソッド](/scripting/javascript/reference/tolocaletimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLocaleUppercase メソッド](/scripting/javascript/reference/tolocaleuppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toLowerCase メソッド](/scripting/javascript/reference/tolowercase-method-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toPrecision メソッド](/scripting/javascript/reference/toprecision-method-number-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toString メソッド](/scripting/javascript/reference/tostring-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toTimeString メソッド](/scripting/javascript/reference/totimestring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUpperCase メソッド](/scripting/javascript/reference/touppercase-method-string-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [toUTCString メソッド](/scripting/javascript/reference/toutcstring-method-date-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [trim メソッド](/scripting/javascript/reference/trim-method-string-javascript) | N | N | Y | Y | Y | Y | Y |  
| [try ステートメント](/scripting/javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [typeof 演算子](/scripting/javascript/reference/typeof-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [ubound メソッド](/scripting/javascript/reference/ubound-method-vbarray-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Uint8Array オブジェクト](/scripting/javascript/reference/uint8array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint16Array オブジェクト](/scripting/javascript/reference/uint16array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint32Array オブジェクト](/scripting/javascript/reference/uint32array-object) | N | N | N | Y | Y | Y | Y |  
| [Uint8ClampedArray オブジェクト](/scripting/javascript/reference/uint8clampedarray-object-javascript) | N | N | N | N | Y | Y | v8: いいえ <br /> v8.1 (Win): はい <br /> v8.1 (電話): いいえ <br /> v10: Y |  
| [非項否定演算子 (-)](/scripting/javascript/reference/subtraction-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [undefined Constant](/scripting/javascript/reference/undefined-constant-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [unescape 関数](/scripting/javascript/reference/unescape-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [Unicode コード ポイントエスケープ文字](/scripting/javascript/advanced/special-characters-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [unshift メソッド](/scripting/javascript/reference/unshift-method-array-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [符号なし右シフト割り当て演算子 (>>>=)](/scripting/javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [符号なし右シフト演算子 (>>>)](/scripting/javascript/reference/unsigned-right-shift-operator-decrement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [strict ディレクティブの使用](/scripting/javascript/reference/use-strict-directive) | N | N | N | Y | Y | Y | Y |  
| [UTC 関数](/scripting/javascript/reference/date-utc-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [valueOf メソッド](/scripting/javascript/reference/valueof-method-object-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [values メソッド (Array)](/scripting/javascript/reference/values-method-array-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [var ステートメント](/scripting/javascript/reference/var-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [VBArray オブジェクト](/scripting/javascript/reference/vbarray-object-javascript) | Y | Y | Y | Y | Y | Y | N |  
| [void 演算子](/scripting/javascript/reference/void-operator-decrementjavascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WeakMap オブジェクト](/scripting/javascript/reference/weakmap-object-javascript) | N | N | N | N | Y | Y | v8: N <br /> v8.1: Y |  
| [WeakSet オブジェクト](/scripting/javascript/reference/weakset-object-javascript) | N | N | N | N | N | Y | v8.1: N <br /> v10: Y |  
| [while ステートメント](/scripting/javascript/reference/while-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [WinRTError オブジェクト](/scripting/javascript/reference/winrterror-object-javascript) | N | N | N | Y | Y | Y | Y |  
| [with ステートメント](/scripting/javascript/reference/with-statement-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [write 関数](/scripting/javascript/reference/debug-write-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
| [writeln 関数](/scripting/javascript/reference/debug-writeln-function-javascript) | Y | Y | Y | Y | Y | Y | Y |  
  
 \* DOM オブジェクトをサポートしますが、ユーザー定義オブジェクトはサポートしません。  属性 `enumerable` `configurable` と属性は指定できますが、使用されません。  
