---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。  ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。  評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。  元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9aa87c1c289452844ef3442811f84881fc752b4
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397693"
---
# <a name="runtime-domain---devtools-protocol-version-01-edgehtml"></a>ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。  評価結果は、オブジェクトの種類、文字列表現、さらにオブジェクト参照に使用できる一意の識別子を公開するミラー オブジェクトとして返されます。  元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。  

| 分類 | Members |  
|:--- |:--- |  
| [メソッド](#methods) | [enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties) |  
| [イベント](#events) | [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown) |  
| [型](#types) | [ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace) |  

## <a name="methods"></a>メソッド  

### <a name="enable"></a>[有効]  

イベントのレポートを有効 `executionContextsCleared` にする。  

&nbsp;  

---  

### <a name="disable"></a>[無効]  

イベントのレポートを無効 `executionContextsCleared` にします。  

&nbsp;  

---  

### <a name="evaluate"></a>評価する  

グローバル オブジェクトの式を評価します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 式 | `string` | 評価する式。 |  
| silent \(optional\) | `boolean` | 評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。  状態を上書 `setPauseOnException` きします。 |  
| contextId \(optional\) | [ExecutionContextId](#executioncontextid) | 評価を実行する実行コンテキストを指定します。  パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。 |  
| returnByValue \(optional\) | `boolean` | 結果が値によって送信される JSON オブジェクトと予想されるかどうか。 |  
| awaitPromise \(optional\) | `boolean` | 結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | 評価結果。 |  

---  

### <a name="callfunctionon"></a>callFunctionOn  

指定されたオブジェクトに対して指定された宣言を持つ関数を呼び出します。  結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| functionDeclaration | `string` | 呼び出す関数の宣言。 |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid) | 関数を呼び出すオブジェクトの識別子。  または `objectId` 指定 `executionContextId` する必要があります。  objectId は Runtime.evaluate() 関数の値である必要があります。 |  
| arguments \(optional\) | [CallArgument[]](#callargument) | 引数を呼び出します。  すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。 |  
| silent \(optional\) | `boolean` | 評価中にスローされるサイレント モードの例外は報告され、実行を一時停止しません。  状態を上書 `setPauseOnException` きします。 |  
| returnByValue \(optional\) | `boolean` | 結果が値によって送信される JSON オブジェクトと予想されるかどうか。 |  
| awaitPromise \(optional\) | `boolean` | 結果の値に対 `await` して実行を行い、待ち受ける約束が解決された後に戻る必要があるかどうか。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | 結果を呼び出します。 |  

---  

### <a name="getproperties"></a>getProperties  

指定したオブジェクトのプロパティを返します。  結果のオブジェクト グループは、ターゲット オブジェクトから継承されます。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| objectId | [RemoteObjectId](#remoteobjectid) | プロパティを返すオブジェクトの識別子。  `objectId` 関数からである必要 `Debugger.evaluateOnCallFrame()` があります。 |  
| ownProperties \(optional\) | `boolean` | If `true` は、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。 |  
| accessorPropertiesOnly \(optional\) | `boolean` | **実験的な**.  場合 `true` は、アクセサー プロパティ \(getter/setter\) のみを返します。内部プロパティも返されません。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| result | [PropertyDescriptor[]](#propertydescriptor) | オブジェクトのプロパティ。 |  

---  

## <a name="events"></a>イベント  

### <a name="executioncontextscleared"></a>executionContextsCleared  

ブラウザーですべての executionContexts がクリアされた場合に発行されます。  

&nbsp;  

---  

### <a name="exceptionthrown"></a>exceptionThrown  

例外がスローされ、処理されない場合に発行されます。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| タイムスタンプ | [タイムスタンプ](#timestamp) | 例外のタイムスタンプ。 |  
| exceptionDetails | [ExceptionDetails](#exceptiondetails) | &nbsp; |  

---  

## <a name="types"></a>型  

### <a name="scriptid-string"></a>ScriptId 文字列  

<a name="scriptid"></a>  

一意のスクリプト識別子。  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a>RemoteObjectId 文字列  

<a name="remoteobjectid"></a>  

一意のオブジェクト識別子。  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a>UnserializableValue 文字列  

<a name="unserializablevalue"></a>  

JSON 文字列化できないプリミティブ値。  

##### <a name="allowed-values"></a>許可される値  

`Infinity`, `NaN`, `-Infinity`, `-0`  

---  

### <a name="remoteobject-object"></a>RemoteObject オブジェクト  

<a name="remoteobject"></a>  

元の JavaScript オブジェクトを参照するミラー オブジェクト。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 型 | `string` | オブジェクトの種類。  使用できる値: `object` `function` `undefined` 、、、、、、、、 `string` `number` `boolean` `symbol` |  
| サブタイプ \(optional\) | `string` | オブジェクトのサブタイプ ヒント。  型の値 `object` にのみ指定します。  使用できる値:  `null` `error` 、、および `promise` |  
| className \(optional\) | `string` | オブジェクト クラス \(constructor\) 名。  型の値 `object` にのみ指定します。 |  
| value \(optional\) | `any` | プリミティブ値または JSON 値の場合のリモート オブジェクト値 \(要求された場合\)。 |  
| unserializableValue \(optional\) | [UnserializableValue](#unserializablevalue) | JSON 文字列化できないプリミティブ値は持たれていますが `value` 、このプロパティを取得します。 |  
| description \(optional\) | `string` | オブジェクトの文字列表現。 |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid) | 一意のオブジェクト識別子 \(非プリミティブ値\)。 |  
| msDebuggerPropertyId \(optional\) | `string` | **実験的な**.  Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。 |  

---  

### <a name="propertydescriptor-object"></a>PropertyDescriptor オブジェクト  

<a name="propertydescriptor"></a>  

オブジェクト プロパティ記述子。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| name | `string` | プロパティ名またはシンボルの説明。 |  
| value \(optional\) | [RemoteObject](#remoteobject) | プロパティに関連付けられている値。 |  
| 書き込み可能 \(optional\) | `boolean` | `True` プロパティに関連付けられている値が変更される場合 \(データ記述子のみ\)。 |  
| get \(optional\) | [RemoteObject](#remoteobject) | プロパティの getter として機能する関数、または `undefined` getter \(アクセサー記述子のみ\) がない場合。 |  
| set \(optional\) | [RemoteObject](#remoteobject) | プロパティのセッターとして機能する関数、または `undefined` setter \(アクセサー記述子のみ\) がない場合。 |  
| 構成可能 | `boolean` | `True` このプロパティ記述子の種類が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合。 |  
| 列挙可能 | `boolean` | `True` このプロパティが対応するオブジェクトのプロパティの列挙中に表示される場合。 |  
| wasThrown \(optional\) | `boolean` | `True` 評価中に結果がスローされた場合。 |  
| isOwn \(optional\) | `boolean` | `True` プロパティがオブジェクトに対して所有されている場合。 |  
| msReturnValue \(optional\) | `boolean` | **実験的な**.  Microsoft:  `True` プロパティが戻り値の場合。 |  
| symbol \(optional\) | [RemoteObject](#remoteobject) | プロパティが型の場合は、プロパティ シンボル `symbol` オブジェクト。 |  

---  

### <a name="callargument-object"></a>CallArgument オブジェクト  

<a name="callargument"></a>  

関数呼び出しの引数を表します。  リモート オブジェクト `value` ID、非erializable プリミティブ値、または \(for undefined\) のいずれかを指定する必要があります。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| value \(optional\) | `any` | プリミティブ値またはシリアル化可能な javascript オブジェクト。 |  
| unserializableValue \(optional\) | [UnserializableValue](#unserializablevalue) | JSON 文字列化できないプリミティブ値。 |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid) | リモート オブジェクト ハンドル。 |  

---  

### <a name="executioncontextid-integer"></a>ExecutionContextId 整数  

<a name="executioncontextid"></a>  

実行コンテキストの ID。  

&nbsp;  

---  

### <a name="exceptiondetails-object"></a>ExceptionDetails オブジェクト  

<a name="exceptiondetails"></a>  

スクリプトのコンパイルまたは実行中にスローされた例外 \(または error\) に関する詳細情報。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| exceptionId | `integer` | 例外 ID。 |  
| テキスト | `string` | 使用可能な場合は例外オブジェクトと共に使用する必要がある例外テキスト。 |  
| lineNumber | `integer` | 例外の場所 \(0 ベース\) の行番号。 |  
| columnNumber | `integer` | 例外の場所 \(0 ベース\) の列番号。 |  
| scriptId \(optional\) | [ScriptId](#scriptid) | 例外の場所のスクリプト ID。 |  
| url \(optional\) | `string` | スクリプトが報告されていないときに使用する例外の場所の URL。 |  
| stackTrace \(optional\) | [StackTrace](#stacktrace) | JavaScript スタック トレース (使用可能な場合)。 |  
| 例外 \(optional\) | [RemoteObject](#remoteobject) | 例外オブジェクト (使用可能な場合)。 |  
| executionContextId \(optional\) | [ExecutionContextId](#executioncontextid) | 例外が発生したコンテキストの識別子。 |  

---  

### <a name="timestamp-integer"></a>タイムスタンプの整数  

<a name="timestamp"></a>  

エポックからのミリ秒単位。  

&nbsp;  

---  

### <a name="callframe-object"></a>CallFrame オブジェクト  

<a name="callframe"></a>  

ランタイム エラーとアサーションのスタック エントリ。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| functionName | `string` | JavaScript 関数名。 |  
| scriptId | [ScriptId](#scriptid) | JavaScript スクリプト ID。 |  
| url | `string` | JavaScript スクリプト名または URL。 |  
| lineNumber | `integer` | JavaScript スクリプト行番号 \(0-based\)。 |  
| columnNumber | `integer` | JavaScript スクリプト列番号 \(0-based\)。 |  

---  

### <a name="stacktrace-object"></a>StackTrace オブジェクト  

<a name="stacktrace"></a>  

アサーションまたはエラー メッセージの呼び出しフレーム。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| description \(optional\) | `string` | このスタック トレースの文字列ラベル。  非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。 |  
| callFrames | [CallFrame[]](#callframe) | JavaScript 関数名。 |  
| parent \(optional\) | [StackTrace](#stacktrace) | このスタックの前に含まれる非同期 JavaScript スタック トレース (使用可能な場合)。 |  

---  
