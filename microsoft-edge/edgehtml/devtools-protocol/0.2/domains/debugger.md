---
description: デバッガー ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 デバッガー ドメインは、JavaScript のデバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
title: デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 00c410812edd4d11e9904a489955e7fd218a7e5d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398176"
---
# <a name="debugger-domain---devtools-protocol-version-02-edgehtml"></a>デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

デバッガー ドメインは、JavaScript のデバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。

| 分類 | Members |  
|:--- |:--- |  
| [**メソッド**](#methods) | [](#enable)enable [](#disable), disable , [getPossibleBreakpoints](#getpossiblebreakpoints) [](#pause), [setBreakpointByUrl , setBreakpointByUrl](#setbreakpointbyurl) [](#stepover), [setBreakpoint](#setbreakpoint) [](#setbreakpointsactive), [stepOver](#removebreakpoint), [stepInto](#stepout), stepOut , pause , [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [](#stepinto) [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue) |  
| [**イベント**](#events) | [scriptParsed](#scriptparsed), [ブレークポイントResolved](#breakpointresolved), [一時停止](#paused), [再開](#resumed) |  
| [**型**](#types) | [ブレークポイント Id](#breakpointid)、 [CallFrameId](#callframeid)、 [Location](#location)、 [BreakLocation](#breaklocation)、 [CallFrame](#callframe)、 [Scope](#scope) |  
| [**依存関係**](#dependencies) | [ランタイム](./runtime.md) |  

## <a name="methods"></a>メソッド  

### <a name="enable"></a>[有効]  

指定したページのデバッガーを有効にします。 クライアントは、このコマンドの結果を受信するまで、デバッグが有効になっていると見なす必要があります。  

&nbsp;  

---  

### <a name="disable"></a>[無効]  

特定のページのデバッガーを無効にします。  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a>getPossibleBreakpoints  

ブレークポイントの可能な場所を返します。 開始範囲と終了範囲の場所の scriptId は同じである必要があります。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| start | [Location](#location) | 範囲の開始位置からブレークポイントの場所を検索します。 |  
| 終了 | [Location](#location) | \(excluding\) でブレークポイントの場所を検索する範囲の末尾。  指定しない場合は、スクリプトの末尾が範囲の末尾として使用されます。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 場所 | [BreakLocation](#breaklocation) | 考えられるブレークポイントの場所の一覧。 |  

---  

### <a name="setbreakpointsactive"></a>setBreakpointsActive  

ページ上のすべてのブレークポイントをアクティブ化/非アクティブ化します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| active | `boolean` | ブレークポイントのアクティブな状態の新しい値。 | 

---  

### <a name="setbreakpointbyurl"></a>setBreakpointByUrl  

URL または URL 正規表現で指定された特定の場所に JavaScript ブレークポイントを設定します。  このコマンドを発行すると、解析済みのすべてのスクリプトにブレークポイントが解決され、プロパティに返 `locations` されます。  さらに一致するスクリプトの解析により、後続の `breakpointResolved` イベントが発行されます。  この論理ブレークポイントは、ページの再読み込みから存続します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| lineNumber | `integer` | ブレークポイントを設定する行番号。 | 
| url \(optional\) | `string` | ブレークポイントを設定するリソースの URL。 |  
| urlRegex \(optional\) | `string` | ブレークポイントを設定するリソースの URL の正規表現パターン。  指定 `url` するか `urlRegex` 、指定する必要があります。 |  
| columnNumber \(optional\) | `integer` | ブレークポイントを設定する行のオフセットです。 |  
| condition \(optional\) | `string` | ブレークポイント条件として使用する式。 指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| ブレークポイントId | [ブレークポイントId](#breakpointid) | 追加の参照用に作成されたブレークポイントの ID。 |  
| 場所 | [Location[]](#location) | 追加時にこのブレークポイントが解決された場所の一覧。 |  

---  

### <a name="setbreakpoint"></a>setBreakpoint  

特定の場所に JavaScript ブレークポイントを設定します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 場所 | [Location](#location) | ブレークポイントを設定する場所。 |  
| condition \(optional\) | `string` | ブレークポイント条件として使用する式。  指定すると、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| ブレークポイントId | [ブレークポイントId](#breakpointid) | 追加の参照用に作成されたブレークポイントの ID。 |  
| actualLocation | [Location](#location) | このブレークポイントが解決された場所。 |  

---  

### <a name="removebreakpoint"></a>removeBreakpoint  

JavaScript ブレークポイントを削除します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| ブレークポイントId | [ブレークポイントId](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a>stepOver  

ステートメントの手順を実行します。  

&nbsp;  

---  

### <a name="stepinto"></a>stepInto  

関数呼び出しを実行します。  

&nbsp;  

---  

### <a name="stepout"></a>stepOut  

関数呼び出しからステップアウトします。  

&nbsp;  

---  

### <a name="pause"></a>pause  

次の JavaScript ステートメントで停止します。  

&nbsp;  

---  

### <a name="resume"></a>resume  

JavaScript の実行を再開します。  

&nbsp;  

---  

### <a name="getscriptsource"></a>getScriptSource  

指定された ID を持つスクリプトのソースを返します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | ソースを取得するスクリプトの ID。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scriptSource | `string` | スクリプト ソース。 | 

---  

### <a name="setpauseonexceptions"></a>setPauseOnExceptions  

例外状態の一時停止を定義します。  すべての例外、キャッチされていない例外、または例外なしで停止する設定が可能です。  例外状態の最初の一時停止はです `none` 。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 状態 | `string` | 例外モードで一時停止します。  使用できる値:  `none` `uncaught` 、 、 `all` |  

---  

### <a name="evaluateoncallframe"></a>evaluateOnCallFrame  

指定された呼び出しフレームの式を評価します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| callFrameId | [CallFrameId](#callframeid) | フレーム識別子を呼び出して評価します。 |  
| 式 | `string` | 評価する式。 | 

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| result | [Runtime.RemoteObject](./runtime.md#remoteobject) | 評価結果のオブジェクト ラッパー。 |  

---  

### <a name="setvariablevalue"></a>setVariableValue  

呼び出しフレーム内の変数の値を変更します。  オブジェクト ベースのスコープはサポートされていないので、手動で変更する必要があります。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scopeNumber | `integer` | スコープ チェーンに記載されている範囲の 0 からベースの数。  のみ `local` 、 `closure` および `catch` スコープの種類を使用できます。  他のスコープは手動で操作できます。 | 
| variableName | `string` | 変数名。 | 
| newValue | [Runtime.CallArgument](./runtime.md#callargument) | 新しい変数値。 |  
| callFrameId | [CallFrameId](#callframeid) | 変数を保持する呼び出しフレームの ID。 |  

---  

### <a name="setblackboxpatterns"></a>setBlackboxPatterns  

**実験的な**.  以前のブラックボックス パターンを渡されたパターンに置き換える。  バックエンドは、パターンの 1 つに一致する URL を持つスクリプトのステップ/一時停止を強制的にスキップします。  デバッガーは、'step in' を何度も実行してブラックボックス化されたスクリプトを残し、失敗した場合は最後に "ステップアウト" に進みます。  


| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| パターン | `string[]` | スクリプトの URL でブラックボックスの状態を確認するために使用される正規表現の配列。 | 

---  

### <a name="mssetdebuggerpropertyvalue"></a>msSetDebuggerPropertyValue  

**実験的な**.  Microsoft: 指定したデバッガー プロパティを指定した値に設定します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| debuggerPropertyId | 文字列 | Microsoft: 設定するプロパティ ID \(すなわち `msDebuggerPropertyId` \) です。 | 
| newValue | `string` | &nbsp; |  

---  

## <a name="events"></a>イベント  

### <a name="scriptparsed"></a>scriptParsed  

スクリプトの解析時に発生します。 このイベントは、デバッガーを有効にした時点で、既知のスクリプトおよび未記録のスクリプトに対して発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | 解析されたスクリプトの識別子。 |  
| url | `string` | 解析されたスクリプトの URL または名前 \(if any\)。 | 
| startLine | `integer` | リソース内のスクリプトの行オフセットで、指定された URL \(スクリプト タグ\の場合)。 | 
| startColumn | `integer` | 指定された URL を持つリソース内のスクリプトの列オフセット。 | 
| endLine | `integer` | スクリプトの最後の行。 | 
| endColumn | `integer` | スクリプトの最後の行の長さ。 | 
| executionContextId | [Runtime.ExecutionContextId](./runtime.md#executioncontextid) | スクリプト作成コンテキストを指定します。 |  
| sourceMapURL \(optional\) | `string` | スクリプトに関連付けられたソース マップの URL (指定されている場合)。 |  
| length \(optional\) | `integer` | **実験的な**.  このスクリプトの長さ。 |  
| msParentId \(optional\) | `string` | **実験的な**.  これは親ドキュメント ID です。 |  
| msMimeType \(optional\) | `string` | **実験的な**.  これは MIME の種類です。 |  
| msIsDynamicCode \(optional\) | `boolean` | **実験的な**.  これは、動的コードであるかどうかを示します。 |  
| msLongDocumentId \(optional\) | `integer` | **実験的な**.  これは長いドキュメント ID です。 |  

---  

### <a name="breakpointresolved"></a>ブレークポイントResolved  

ブレークポイントが実際のスクリプトと場所に解決された場合に発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| ブレークポイントId | [ブレークポイントId](#breakpointid) | ブレークポイントの一意の識別子。 |  
| 場所 | [Location](#location) | 実際のブレークポイントの場所。 |  
| msLength \(optional\) | `integer` | **実験的な**.  Microsoft: ブレークポイントの場所にあるコードの長さ \(つまり、文字数\) です。 |  

---  

### <a name="paused"></a>paused (一時停止)  

ブレークポイントまたは例外のデバッガーが壊れた場合に発生します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| callFrames | [CallFrame[]](#callframe) | デバッガーが停止したスタックを呼び出します。 |  
| 理由 | `string` |  理由を一時停止します。  使用できる値:  `breakpoint` `step` `exception` `other` 、、、、、、 `EventListener` |  
| data \(optional\) | `object` | ブレーク固有の補助プロパティを含むオブジェクト。 |  
| hitBreakpoints \(optional\) | `string[]` | ブレークポイントのヒットの ID |  
| asyncStackTrace \(optional\) | `StackTrace` | JavaScript async スタック トレース。 |  

---  

### <a name="resumed"></a>再開  

デバッガーが実行を再開すると発生します。  

&nbsp;  

---  

## <a name="types"></a>型  

### <a name="breakpointid-string"></a>ブレークポイントId 文字列  

<a name="breakpointid"></a>  

ブレークポイント識別子。  

&nbsp;  

---  

### <a name="callframeid-string"></a>CallFrameId 文字列  

<a name="callframeid"></a>  

呼び出しフレーム識別子。  

&nbsp;  

---  

### <a name="location-object"></a>Location オブジェクト  

<a name="location"></a>  

ソース コード内の場所。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | で報告されるスクリプト識別子 `Debugger.scriptParsed` 。 |  
| lineNumber | `integer` | スクリプト \(0-based\) の行番号。 |  
| columnNumber \(optional\) | `integer` | スクリプト \(0-based\) の列番号。 |  
| msLength | `integer` | Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。 |  

---  

### <a name="breaklocation-object"></a>BreakLocation オブジェクト  

<a name="breaklocation"></a>  

ソース コード内の場所を壊します。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | で報告されるスクリプト識別子 `Debugger.scriptParsed` 。 |  
| lineNumber | `integer` | スクリプト \(0-based\) の行番号。 |  
| columnNumber \(optional\) | `integer` | スクリプト \(0-based\) の列番号。 |  
| msLength | `integer` | Microsoft: この呼び出しフレームでのコードの長さ \(つまり、文字数\) です。 |  
| 型 \(optional\) | `string` | 使用できる値: debuggerStatement、呼び出し、返します。 |  

---  

### <a name="callframe-object"></a>CallFrame オブジェクト  

<a name="callframe"></a>  

JavaScript 呼び出しフレーム。 呼び出しフレームの配列は、呼び出し履歴を形成します。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| callFrameId | [CallFrameId](#callframeid) | 呼び出しフレーム識別子。  この識別子は、デバッガーが一時停止している間のみ有効です。 |  
| functionName | `string` | この呼び出しフレームで呼び出される JavaScript 関数の名前。 |  
| functionLocation \(optional\) | [Location](#location) | **実験的な**.  ソース コード内の場所。 |  
| 場所 | [Location](#location) | ソース コード内の場所。 |  
| url | `string` | JavaScript スクリプト名または URL。 |  
| scopeChain | [Scope[]](#scope) | この呼び出しフレームのスコープ チェーン。 |  
| これ | [Runtime.RemoteObject](./runtime.md#remoteobject) | `this` この呼び出しフレームのオブジェクト。 |  
| returnValue \(optional\) | [Runtime.RemoteObject](./runtime.md#remoteobject) | 関数が戻り値である場合に返される値。 |  

---  

### <a name="scope-object"></a>Scope オブジェクト  

<a name="scope"></a>  

スコープの説明。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| 型 | `string` | スコープの種類。  使用できる値: `global` `local` `with` 、、、、、、、、、、 `closure` `catch` `block` `script` `eval` `module` `return` |  
| object | [Runtime.RemoteObject](./runtime.md#remoteobject) | スコープを表すオブジェクト。  For and scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as `global` `with` its properties. |  
| name \(optional\) | `string` | &nbsp; |  
| startLocation \(optional\) | [Location](#location) | スコープが開始するソース コード内の場所。 |  
| endLocation \(optional\) | [Location](#location) | スコープが終了するソース コード内の場所。 |  

---  

## <a name="dependencies"></a>依存関係  

[ランタイム](./runtime.md)  
