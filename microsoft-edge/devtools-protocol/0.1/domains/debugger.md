---
description: デバッガードメインの参照。 デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
title: デバッガドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1e76d17e5dfbe39ba61c7cb45a4e88b9fd223068
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882955"
---
# デバッガドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)  
  
デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。

| | |
|-|-|
| [**メソッド**](#methods) | [有効化](#enable)、[無効化](#disable)、 [getstepOut ブレークポイント](#getpossiblebreakpoints)、 [setbreakpointsactive](#setbreakpointsactive)、 [setbreakpointsactive](#setbreakpointbyurl)、 [setブレークポイント](#setbreakpoint)、 [removebreakpoint](#pause) [、curve、](#stepover) [stepinto](#stepinto)、 [removebreakpoint ポイント](#removebreakpoint)、[履歴書](#resume)、 [getpossiblebreakpoints](#getscriptsource)、 [setPauseOnExceptions](#setpauseonexceptions)、 [evalu](#evaluateoncallframe) [、](#stepout) [setblackboxpatterns](#setblackboxpatterns) [、](#setvariablevalue) [mssetデバッガ propertyvalue](#mssetdebuggerpropertyvalue) |
| [**イベント**](#events) | [Scriptparsed 解析](#scriptparsed)、 [breakpointresolved 解決](#breakpointresolved)、[一時停止](#paused)、[再開](#resumed) |
| [**型**](#types) | [Breakpointid](#breakpointid)、[呼び出しフレーム id](#callframeid)、[位置](#location)、 [breaklocation](#breaklocation)、 [callframe](#callframe)、[スコープ](#scope) |
| [**依存関係**](#dependencies) | [ランタイム](runtime.md) |
## メソッド

### [有効]
指定したページに対してデバッガーを有効にします。 クライアントは、このコマンドの結果が受信されるまで、デバッグが有効になっていると想定することはできません。


---

### [無効]
指定されたページのデバッガーを無効にします。


---

### Getのブレークポイント
ブレークポイントで可能な場所を返します。 開始と終了の範囲の場所の scriptId は同じである必要があります。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>start</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>範囲の先頭から、ブレークポイントの場所を検索します。</td>
        </tr>
        <tr>
            <td>終了</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>[範囲の終わり] は、使用可能なブレークポイントの場所 (除外) を検索します。 指定しない場合、スクリプトの末尾が範囲の末尾として使用されます。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>場所</td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td>可能なブレークポイントの場所の一覧。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpointsActive
ページのすべてのブレークポイントをアクティブ化または非アクティブ化します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>active</td>
            <td><code class="flyout">boolean</code></td>
            <td>ブレークポイントのアクティブな状態の新しい値。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpointByUrl
URL または URL regex で指定された場所に JavaScript のブレークポイントを設定します。 このコマンドを発行すると、既に解析されているすべてのスクリプトのブレークポイントが解決され、プロパティに返され <code>locations</code> ます。 さらに一致するスクリプトの解析により、後続のイベントが発行され <code>breakpointResolved</code> ます。 この論理ブレークポイントは、ページの読み込みを維持します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>ブレークポイントを設定する行番号。</td>
        </tr>
        <tr>
            <td>url <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイントを設定するリソースの URL です。</td>
        </tr>
        <tr>
            <td>urlRegex <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイントを設定するリソースの Url の Regex パターン。 <code>url</code>またはどちらか <code>urlRegex</code> を指定する必要があります。</td>
        </tr>
        <tr>
            <td>列番号 <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>ブレークポイントを設定する行のオフセット。</td>
        </tr>
        <tr>
            <td>条件 <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイント条件として使用する式。 指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>追加で参照するために作成したブレークポイントの Id です。</td>
        </tr>
        <tr>
            <td>場所</td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td>このブレークポイントが追加されたときに解決される場所の一覧です。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpoint ポイント
JavaScript のブレークポイントを特定の場所に設定します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>元</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>ブレークポイントを設定する場所。</td>
        </tr>
        <tr>
            <td>条件 <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイント条件として使用する式。 指定すると、この式が true と評価された場合にのみ、デバッガーはブレークポイントで停止します。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>追加で参照するために作成したブレークポイントの Id です。</td>
        </tr>
        <tr>
            <td>作動時の割り当て</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>このブレークポイントが解決される場所。</td>
        </tr>
    </tbody>
</table>

---

### removeBreakpoint ポイント
JavaScript のブレークポイントを削除します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### パス
ステートメントの手順を実行します。


---

### ステップイン
関数呼び出しの手順。


---

### stepOut
関数呼び出しの手順を実行します。


---

### pause
次の JavaScript ステートメントで停止します。


---

### resume
JavaScript の実行を再開します。


---

### getScriptSource
指定された id のスクリプトのソースを返します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>ソースを取得するスクリプトの Id です。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptSource</td>
            <td><code class="flyout">string</code></td>
            <td>スクリプトソース。</td>
        </tr>
    </tbody>
</table>

---

### setPauseOnExceptions
例外の状態に対する一時停止を定義します。 すべての例外、不明な例外、または例外を停止するように設定できます。 例外の状態での最初の一時停止 <code>none</code> 。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>州</td>
            <td><code class="flyout">string</code> <br/> <i>許可される値: なし、不明、すべて</i></td>
            <td>例外モードで一時停止します。</td>
        </tr>
    </tbody>
</table>

---

### evaluateOnCallFrame
指定した呼び出しフレームで式を評価します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Callフレーム Id</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>を評価するために、フレーム識別子を呼び出します。</td>
        </tr>
        <tr>
            <td>expression</td>
            <td><code class="flyout">string</code></td>
            <td>評価する式。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>より</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>評価結果のオブジェクトラッパー。</td>
        </tr>
    </tbody>
</table>

---

### Set変数値
Callframe の変数の値を変更します。 オブジェクトベースのスコープはサポートされていないため、手動で手動で作成する必要があります。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scopeNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>0ベースのスコープの数がスコープチェーンに一覧表示されています。 "Local"、"クロージャ"、"catch" のスコープ型のみを使用できます。 その他のスコープは手動で操作できます。</td>
        </tr>
        <tr>
            <td>variableName</td>
            <td><code class="flyout">string</code></td>
            <td>変数名。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td>新しい変数値。</td>
        </tr>
        <tr>
            <td>Callフレーム Id</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>変数を保持する callframe の Id です。</td>
        </tr>
    </tbody>
</table>

---

### setBlackboxPatterns
<span><b>的. </b></span>前の blackbox パターンを、渡されたものに置き換えます。 すべてのパターンに一致する url を持つスクリプトのステップ/一時停止をスキップするようにバックエンドに強制します。 デバッガーは、"ステップイン" を複数回実行して、ブラックボックススクリプトを終了しようとします。最後に、失敗した場合は、"ステップアウト" に従います。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>傾向</td>
            <td><code class="flyout">string[]</code></td>
            <td>Blackbox の状態のスクリプト url を確認するために使用される regexps の配列です。</td>
        </tr>
    </tbody>
</table>

---

### Mssetデバッガ Propertyvalue
<span><b>的. </b></span>Microsoft: 指定された debugger プロパティを指定された値に設定します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>debuggerPropertyId</td>
            <td><code class="flyout">string</code></td>
            <td>Microsoft: プロパティ id (msDebuggerPropertyId など) を設定します。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## イベント

### scriptParsed
スクリプトの解析時に発生します。 このイベントは、デバッガーを有効にしているときに、既知の収集されていないすべてのスクリプトに対しても発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>解析されたスクリプトの識別子。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>解析されたスクリプトの URL または名前 (存在する場合)。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>指定した URL のリソース内のスクリプトの行オフセット (スクリプトタグの場合)。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>指定した URL のリソース内のスクリプトの列オフセット。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプトの最終行。</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプトの最後の行の長さ。</td>
        </tr>
        <tr>
            <td>executionContextId</td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td>スクリプト作成コンテキストを指定します。</td>
        </tr>
        <tr>
            <td>sourceMapURL <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スクリプト (存在する場合) に関連付けられたソースマップの URL。</td>
        </tr>
        <tr>
            <td>全長 <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>的. </b></span>このスクリプトの長さ。</td>
        </tr>
        <tr>
            <td>msParentId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>的. </b></span>これは親ドキュメント ID です。</td>
        </tr>
        <tr>
            <td>msMimeType <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>的. </b></span>Mime の種類です。</td>
        </tr>
        <tr>
            <td>msIsDynamicCode <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>的. </b></span>これは、動的コードであるかどうかを示します。</td>
        </tr>
        <tr>
            <td>msLongDocumentId <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>的. </b></span>これは長いドキュメント ID です。</td>
        </tr>
    </tbody>
</table>

---

### breakpointResolved 解決
ブレークポイントが実際のスクリプトと場所に解決されたときに発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>ブレークポイントの一意の識別子。</td>
        </tr>
        <tr>
            <td>元</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>実際のブレークポイントの位置。</td>
        </tr>
        <tr>
            <td>msLength <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>的. </b></span>Microsoft: ブレークポイントの場所のコード長 (文字数)。</td>
        </tr>
    </tbody>
</table>

---

### paused (一時停止)
デバッガーがブレークポイントまたは例外のために中断したときに発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>callFrames</td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td>呼び出しスタックが停止しました。</td>
        </tr>
        <tr>
            <td>から</td>
            <td><code class="flyout">string</code> <br/> <i>許可される値: ブレークポイント、ステップ、例外、その他</i></td>
            <td>一時停止理由。</td>
        </tr>
        <tr>
            <td>data <br/> <i>オプション</i></td>
            <td><code class="flyout">object</code></td>
            <td>ブレーク固有の補助プロパティを含むオブジェクト。</td>
        </tr>
        <tr>
            <td>ヒットブレークポイント <br/> <i>オプション</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>ブレークポイント Id のヒット</td>
        </tr>
    </tbody>
</table>

---

### 復帰
デバッガーの実行を再開したときに発生します。


---

## 型

### <a name="breakpointid"></a> BreakpointId `string`

ブレークポイント識別子。


---

### <a name="callframeid"></a> Callフレーム Id `string`

通話フレーム識別子。


---

### <a name="location"></a> 位置情報 `object`

ソースコード内の場所。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプト内の行番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>列番号 <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプトの列番号 (0 ベース)</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft: この呼び出しフレームのコード長 (文字数)。</td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> BreakLocation `object`

ソースコード内の位置を中断します。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>で報告されるスクリプト識別子 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプト内の行番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>列番号 <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプトの列番号 (0 ベース)</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft: この呼び出しフレームのコード長 (文字数)。</td>
        </tr>
        <tr>
            <td>型 <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>指定可能な値: デバッガステートメント、call、return。</td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> CallFrame `object`

JavaScript 呼び出しフレーム。 コールスタックは、呼び出しフレームの配列によって形成されます。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Callフレーム Id</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>通話フレーム識別子。 この識別子は、デバッガーが一時停止されている場合にのみ有効です。</td>
        </tr>
        <tr>
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>この呼び出しフレームで呼び出される JavaScript 関数の名前。</td>
        </tr>
        <tr>
            <td>関数の場所 <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b>的. </b></span>ソースコード内の場所。</td>
        </tr>
        <tr>
            <td>元</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>ソースコード内の場所。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript スクリプト名または url。</td>
        </tr>
        <tr>
            <td>scopeChain</td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td>この呼び出しフレームのスコープチェーン。</td>
        </tr>
        <tr>
            <td>これ</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> この呼び出しフレームのオブジェクト。</td>
        </tr>
        <tr>
            <td>戻り <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>返される値 (関数が戻り値の位置にある場合)。</td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> 適用範囲 `object`

スコープの説明。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>型</td>
            <td><code class="flyout">string</code> <br/> <i>許可される値: global、local、with、クロージャ、catch、block、script、eval、module</i></td>
            <td>スコープ型。</td>
        </tr>
        <tr>
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>スコープを表すオブジェクト。 <code>global</code>And スコープは実際のオブジェクトを表し、スコープ <code>with</code> の残りの部分については、スコープ変数をプロパティとして列挙する人為的な一時的なオブジェクトです。</td>
        </tr>
        <tr>
            <td>name <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td>startLocation <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>スコープが開始されるソースコード内の場所</td>
        </tr>
        <tr>
            <td>endLocation <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>スコープが終了するソースコード内の場所</td>
        </tr>
    </tbody>
</table>

---

## 依存関係

[ランタイム](runtime.md)