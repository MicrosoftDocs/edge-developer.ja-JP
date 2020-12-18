---
description: デバッガー ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 デバッガー ドメインは、JavaScript デバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
title: デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 24571b3a32acf085dd9ccbd641b1e5b06b3b9504
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234414"
---
# デバッガー ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

デバッガー ドメインは、JavaScript デバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable), [disable](#disable), [getPossibleBreakpoints](#getpossiblebreakpoints), [setBreakpointsActive](#setbreakpointsactive), [setBreakpointByUrl](#setbreakpointbyurl), [setBreakpoint , removeBreakpoint](#setbreakpoint), [stepOver](#stepover), [stepInto](#stepinto), [stepOut](#stepout), [pause](#pause), [resume](#resume), [getScriptSource](#getscriptsource), [setPauseOnExceptions](#setpauseonexceptions), [evaluateOnCallFrame](#evaluateoncallframe), [setVariableValue](#setvariablevalue), [setBlackboxPatterns](#setblackboxpatterns), [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue) [](#removebreakpoint) |
| [**イベント**](#events) | [scriptParsed](#scriptparsed), [ブレークポイントResolved](#breakpointresolved), [一時停止](#paused), [再開](#resumed) |
| [**型**](#types) | [BreakpointId](#breakpointid), [CallFrameId](#callframeid), [Location](#location), [BreakLocation](#breaklocation), [CallFrame](#callframe), [Scope](#scope) |
| [**依存関係**](#dependencies) | [ランタイム](runtime.md) |
## メソッド

### [有効]
指定したページのデバッガーを有効にします。 クライアントは、このコマンドの結果を受け取るまでデバッグが有効になっているとは想定しません。

</p>

---

### [無効]
特定のページのデバッガーを無効にします。

</p>

---

### getPossibleBreakpoints
ブレークポイントの可能性がある場所を返します。 開始範囲と終了範囲の場所の scriptId は同じである必要があります。

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
            <td>ブレークポイントの位置を検索する範囲の開始位置。</td>
        </tr>
        <tr>
            <td>終了</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>(除外する) のブレークポイントの位置を検索する範囲の終了。 指定しない場合、スクリプトの終了が範囲の終了として使用されます。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>locations</td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td>考えられるブレークポイントの場所の一覧。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setBreakpointsActive
ページ上のすべてのブレークポイントをアクティブ化/非アクティブ化します。

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
            <td>アクティブな状態のブレークポイントの新しい値。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setBreakpointByUrl
URL または URL regex で指定された特定の場所に JavaScript ブレークポイントを設定します。 このコマンドを発行すると、既存の解析済みスクリプトはすべてブレークポイントが解決され、プロパティで返 <code>locations</code> されます。 さらに一致するスクリプト解析では、後続の <code>breakpointResolved</code> イベントが発行されます。 この論理的なブレークポイントは、ページの再読み込み後に残ります。

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
            <td>ブレークポイントを設定する行番号です。</td>
        </tr>
        <tr>
            <td>url <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイントを設定するリソースの URL。</td>
        </tr>
        <tr>
            <td>urlRegex <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイントを設定するリソースの URL の正規表現パターン。 指定 <code>url</code> するか <code>urlRegex</code> 、指定する必要があります。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>ブレークポイントを設定する行のオフセット位置を指定します。</td>
        </tr>
        <tr>
            <td>condition <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイント条件として使用する式。 指定した場合、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>追加の参照用に作成されたブレークポイントの ID。</td>
        </tr>
        <tr>
            <td>locations</td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td>追加時にこのブレークポイントが解決された場所の一覧。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setBreakpoint
特定の場所に JavaScript のブレークポイントを設定します。

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
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>ブレークポイントを設定する場所。</td>
        </tr>
        <tr>
            <td>condition <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ブレークポイント条件として使用する式。 指定した場合、デバッガーは、この式が true と評価された場合にのみブレークポイントで停止します。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>追加の参照用に作成されたブレークポイントの ID。</td>
        </tr>
        <tr>
            <td>actualLocation</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>このブレークポイントが解決された場所。</td>
        </tr>
    </tbody>
</table>
</p>

---

### removeBreakpoint
JavaScript ブレークポイントを削除します。

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
</p>

---

### stepOver
ステートメントをステップオーバーします。

</p>

---

### stepInto
関数呼び出しにステップ します。

</p>

---

### stepOut
関数呼び出しをステップアウトします。

</p>

---

### pause
次の JavaScript ステートメントで停止します。

</p>

---

### resume
JavaScript の実行を再開します。

</p>

---

### getScriptSource
指定された ID を持つスクリプトのソースを返します。

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
            <td>ソースを取得するスクリプトの ID。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>scriptSource</td>
            <td><code class="flyout">string</code></td>
            <td>スクリプト ソース。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setPauseOnExceptions
例外状態での一時停止を定義します。 すべての例外、キャッチされていない例外、または例外がない場合に停止を設定できます。 例外の状態での最初の一時停止は次です <code>none</code> 。

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
            <td>state</td>
            <td><code class="flyout">string</code> <br/> <i>使用できる値: none、uncaught、all</i></td>
            <td>例外モードで一時停止します。</td>
        </tr>
    </tbody>
</table>
</p>

---

### evaluateOnCallFrame
特定の呼び出しフレームの式を評価します。

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
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>評価するコール フレーム識別子。</td>
        </tr>
        <tr>
            <td>式</td>
            <td><code class="flyout">string</code></td>
            <td>評価する式。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>result</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>評価結果のオブジェクト ラッパー。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setVariableValue
呼び出しフレーム内の変数の値を変更します。 オブジェクト ベースのスコープはサポートされていないので、手動でミュートする必要があります。

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
            <td>スコープ チェーンにリストされた 0 からスコープの数。 スコープの種類は 'local'、'closure' および 'catch' のみです。 他のスコープは手動で操作できます。</td>
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
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>変数を保持する呼び出しフレームの ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setBlackboxPatterns
<span><b>試験的。 </b></span>以前のブラックボックス パターンを渡されたパターンに置き換える。 パターンの 1 つと一致する URL を持つスクリプトで、ステップ/一時停止をスキップするバックエンドを強制的に実行します。 デバッガーは、何度か 'ステップ イン' を実行してブラックボックス 化されたスクリプトを残し、失敗した場合は最後に "ステップ アウト" を実行します。

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
            <td>patterns</td>
            <td><code class="flyout">string[]</code></td>
            <td>スクリプト URL でブラックボックスの状態を確認するために使用される regexps の配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### msSetDebuggerPropertyValue
<span><b>試験的。 </b></span>Microsoft: 指定されたデバッガー プロパティを指定された値に設定します。

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
            <td>Microsoft: 設定するプロパティ ID (つまり、msDebuggerPropertyId)。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### scriptParsed
スクリプトが解析された場合に発生します。 このイベントは、デバッガーを有効にした時点で、既知のすべてのスクリプトと未検出のスクリプトに対して発生します。

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
            <td>解析されたスクリプトの URL または名前 (指定されている場合)。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>指定された URL を持つリソース内のスクリプトの行オフセット (スクリプト タグの場合)。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>指定された URL を持つリソース内のスクリプトの列オフセット。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプトの最後の行。</td>
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
            <td>スクリプトに関連付けられているソース マップの URL (指定されている場合)。</td>
        </tr>
        <tr>
            <td>length <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>試験的。 </b></span>このスクリプトの長さ。</td>
        </tr>
        <tr>
            <td>msParentId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>試験的。 </b></span>これは親ドキュメント ID です。</td>
        </tr>
        <tr>
            <td>msMimeType <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>試験的。 </b></span>これは MIME タイプです。</td>
        </tr>
        <tr>
            <td>msIsDynamicCode <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>試験的。 </b></span>これは、動的コードかどうかを示します。</td>
        </tr>
        <tr>
            <td>msLongDocumentId <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>試験的。 </b></span>これは長いドキュメント ID です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### breakpointResolved
ブレークポイントが実際のスクリプトと場所に解決された場合に発生します。

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
            <td>ブレークポイントの一意識別子。</td>
        </tr>
        <tr>
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>ブレークポイントの実際の位置。</td>
        </tr>
        <tr>
            <td>msLength <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>試験的。 </b></span>Microsoft: ブレークポイントの位置にあるコードの長さ (文字数) です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### paused (一時停止)
ブレークポイントまたは例外のデバッガーが壊れた場合に発生します。

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
            <td>デバッガーが停止したコール スタック。</td>
        </tr>
        <tr>
            <td>reason</td>
            <td><code class="flyout">string</code> <br/> <i>使用できる値: ブレークポイント、ステップ、例外、その他、EventListener</i></td>
            <td>理由を一時停止します。</td>
        </tr>
        <tr>
            <td>data <br/> <i>オプション</i></td>
            <td><code class="flyout">object</code></td>
            <td>ブレーク固有の補助プロパティを含むオブジェクト。</td>
        </tr>
        <tr>
            <td>hitBreakpoints <br/> <i>オプション</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>ヒット ブレークポイントの ID</td>
        </tr>
        <tr>
            <td>asyncStackTrace <br/> <i>オプション</i></td>
            <td><!--  <a href="#stacktrace">  --><code class="flyout">StackTrace</code><!--  </a>  --></td>
            <td>JavaScript 非同期スタック トレース。</td>
        </tr>
    </tbody>
</table>
</p>

---

### resumed
デバッガーが実行を再開するときに発生します。

</p>

---

## 型

### <a name="breakpointid"></a> BreakpointId `string`

ブレークポイント識別子。

</p>

---

### <a name="callframeid"></a> CallFrameId `string`

呼び出しフレーム識別子。

</p>

---

### <a name="location"></a> 位置情報 `object`

ソース コード内の場所。

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
            <td>スクリプト内の行番号 (0 から開始)。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプト内の列番号 (0 から開始)。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft: この呼び出しフレームでのコードの長さ (文字数)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="breaklocation"></a> BreakLocation `object`

ソース コード内の場所を壊す。

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
            <td>スクリプト内の行番号 (0 から開始)。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>スクリプト内の列番号 (0 から開始)。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft: この呼び出しフレームでのコードの長さ (文字数)。</td>
        </tr>
        <tr>
            <td>型 <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>使用できる値: debuggerStatement、call、return。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callframe"></a> CallFrame `object`

JavaScript 呼び出しフレーム。 呼び出しフレームの配列が呼び出し履歴を形成します。

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
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>呼び出しフレーム識別子。 この識別子は、デバッガーが一時停止している間のみ有効です。</td>
        </tr>
        <tr>
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>この呼び出しフレームで呼び出される JavaScript 関数の名前。</td>
        </tr>
        <tr>
            <td>functionLocation <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b>試験的。 </b></span>ソース コード内の場所。</td>
        </tr>
        <tr>
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>ソース コード内の場所。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript スクリプト名または URL。</td>
        </tr>
        <tr>
            <td>scopeChain</td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td>この呼び出しフレームのスコープ チェーン。</td>
        </tr>
        <tr>
            <td>これ</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> オブジェクトを取得します。</td>
        </tr>
        <tr>
            <td>returnValue <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>関数が戻り値の位置にある場合に返される値。</td>
        </tr>
    </tbody>
</table>
</p>

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
            <td><code class="flyout">string</code> <br/> <i>使用できる値: global、local、with、closure、catch、block、script、eval、module、return</i></td>
            <td>スコープの種類。</td>
        </tr>
        <tr>
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>範囲を表すオブジェクト。 For <code>global</code> および <code>with</code> scopes it represents the actual object; for the rest of the scopes, it is artificial transient object enumerating scope variables as its properties.</td>
        </tr>
        <tr>
            <td>name <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td>startLocation <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>範囲が開始するソース コード内の場所</td>
        </tr>
        <tr>
            <td>endLocation <br/> <i>オプション</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>スコープが終了するソース コード内の場所</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依存関係

[ランタイム](runtime.md)
