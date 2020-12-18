---
description: ランタイム ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
title: ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 942a105199c8740fb7f7496b2a68e3eb0cc46fb4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234426"
---
# ランタイム ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。

| | |
|-|-|
| [**メソッド**](#methods) | [有効](#enable)、[無効、](#disable)[評価](#evaluate)[、callFunctionOn、getProperties](#callfunctionon) [](#getproperties) |
| [**イベント**](#events) | [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown) |
| [**型**](#types) | [ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace) |
## メソッド

### [有効]
イベントのレポートを有効 <code>executionContextsCleared</code> にする。


---

### [無効]
イベントのレポートを無効 <code>executionContextsCleared</code> にします。


---

### evaluate
グローバル オブジェクトの式を評価します。

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
            <td>式</td>
            <td><code class="flyout">string</code></td>
            <td>評価する式。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。 状態を上書 <code>setPauseOnException</code> きします。</td>
        </tr>
        <tr>
            <td>contextId <br/> <i>オプション</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>評価を実行する実行コンテキストを指定します。 パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻るかどうかを指定します。</td>
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
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>評価結果。</td>
        </tr>
    </tbody>
</table>

---

### callFunctionOn
指定されたオブジェクトの特定の宣言を使用して関数を呼び出します。 結果のオブジェクト グループはターゲット オブジェクトから継承されます。

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
            <td>functionDeclaration</td>
            <td><code class="flyout">string</code></td>
            <td>呼び出す関数の宣言。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>関数を呼び出すオブジェクトの識別子。 objectId または executionContextId のいずれかを指定する必要があります。  objectId は Runtime.evaluate() 関数の値である必要があります。</td>
        </tr>
        <tr>
            <td>arguments <br/> <i>オプション</i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td>引数を呼び出します。 すべての呼び出し引数は、ターゲット オブジェクトと同じ JavaScript ワールドに属している必要があります。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>サイレント モードでは、評価中にスローされた例外は報告されません。また、実行を一時停止しません。 状態を上書 <code>setPauseOnException</code> きします。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果が、値によって送信される JSON オブジェクトとして期待されるかどうか。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果の値に <code>await</code> 対して実行を行い、待ち状態の promise が解決された後に戻るかどうかを指定します。</td>
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
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>呼び出しの結果。</td>
        </tr>
    </tbody>
</table>

---

### getProperties
指定したオブジェクトのプロパティを返します。 結果のオブジェクト グループはターゲット オブジェクトから継承されます。

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
            <td>objectId</td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>プロパティを返すオブジェクトの識別子。  objectId は Debugger.evaluateOnCallFrame() 関数の値である必要があります。</td>
        </tr>
        <tr>
            <td>ownProperties <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>true の場合、プロトタイプ チェーンではなく、要素自体にのみ属するプロパティを返します。</td>
        </tr>
        <tr>
            <td>accessorPropertiesOnly <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>試験的。 </b></span>true の場合、アクセサー プロパティ (getter/setter を使用) のみを返します。内部プロパティも返されません。</td>
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
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td>オブジェクトのプロパティ。</td>
        </tr>
    </tbody>
</table>

---

## イベント

### executionContextsCleared
ブラウザーですべての executionContexts がクリアされた場合に発行されます。


---

### exceptionThrown
例外がスローされ、処理されない場合に発行されます。

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
            <td>timestamp</td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>例外のタイムスタンプ。</td>
        </tr>
        <tr>
            <td>exceptionDetails</td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## 型

### <a name="scriptid"></a> ScriptId `string`

一意のスクリプト識別子。


---

### <a name="remoteobjectid"></a> RemoteObjectId `string`

一意のオブジェクト識別子。


---

### <a name="unserializablevalue"></a> UnserializableValue `string`

JSON 文字列化できないプリミティブ値。

##### 使用できる値
Infinity、NaN、-Infinity、-0

---

### <a name="remoteobject"></a> RemoteObject `object`

元の JavaScript オブジェクトを参照するミラー オブジェクト。

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
            <td><code class="flyout">string</code> <br/> <i>有効な値: object、function、undefined、string、number、boolean、symbol</i></td>
            <td>オブジェクトの種類。</td>
        </tr>
        <tr>
            <td>subtype <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code> <br/> <i>使用できる値: null、error、promise</i></td>
            <td>オブジェクトサブタイプのヒント。 型の値 <code>object</code> にのみ指定します。</td>
        </tr>
        <tr>
            <td>className <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>オブジェクト クラス (コンストラクター) 名。 型の値 <code>object</code> にのみ指定します。</td>
        </tr>
        <tr>
            <td>value <br/> <i>オプション</i></td>
            <td><code class="flyout">any</code></td>
            <td>プリミティブ値または JSON 値の場合のリモート オブジェクト値 (要求された場合)。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>オプション</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>JSON 文字列化できないプリミティブ値には、次の値が含まれます。 <code>value</code>が、このプロパティを取得します。</td>
        </tr>
        <tr>
            <td>description <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>オブジェクトの文字列表現。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>一意のオブジェクト識別子 (プリミティブ値以外の場合)。</td>
        </tr>
        <tr>
            <td>msDebuggerPropertyId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>試験的。 </b></span>Microsoft: このオブジェクトに関連付けられているデバッガー プロパティ ID。</td>
        </tr>
    </tbody>
</table>

---

### <a name="propertydescriptor"></a> PropertyDescriptor `object`

オブジェクト プロパティ記述子。

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
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>プロパティ名または記号の説明。</td>
        </tr>
        <tr>
            <td>value <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティに関連付けられている値。</td>
        </tr>
        <tr>
            <td>書き込み可能 <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>True の 場合は、プロパティに関連付けられている値が変更される可能性があります (データ記述子のみ)。</td>
        </tr>
        <tr>
            <td>取得 <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティの getter として機能する関数、または getter がない場合 (アクセサー記述子 <code>undefined</code> のみ)。</td>
        </tr>
        <tr>
            <td>set <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティのセッターとして機能する関数、または setter がない場合 (アクセサー <code>undefined</code> 記述子のみ)。</td>
        </tr>
        <tr>
            <td>構成可能</td>
            <td><code class="flyout">boolean</code></td>
            <td>True の 場合は、このプロパティ記述子の型が変更され、対応するオブジェクトからプロパティが削除される可能性があります。</td>
        </tr>
        <tr>
            <td>enumerable</td>
            <td><code class="flyout">boolean</code></td>
            <td>True の 場合、このプロパティは、対応するオブジェクトのプロパティの列挙中に表示されます。</td>
        </tr>
        <tr>
            <td>wasThrown <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>True の 場合は、評価中に結果がスローされます。</td>
        </tr>
        <tr>
            <td>isOwn <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>True の 場合は、オブジェクトのプロパティが所有されています。</td>
        </tr>
        <tr>
            <td>msReturnValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>試験的。 </b></span>Microsoft: プロパティが戻り値の場合は True。</td>
        </tr>
        <tr>
            <td>symbol <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティが型の場合、プロパティ シンボル `symbol` オブジェクト。 </td>
        </tr>
    </tbody>
</table>

---

### <a name="callargument"></a> CallArgument `object`

関数呼び出しの引数を表します。 リモート オブジェクト ID、プリミティブ、読み取りできないプリミティブ値、または <code>objectId</code> <code>value</code> (未定義の場合) どちらも指定する必要はありません。

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
            <td>value <br/> <i>オプション</i></td>
            <td><code class="flyout">any</code></td>
            <td>プリミティブ値またはシリアル化可能な javascript オブジェクト。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>オプション</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>JSON 文字列化できないプリミティブ値。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>リモート オブジェクト ハンドル。</td>
        </tr>
    </tbody>
</table>

---

### <a name="executioncontextid"></a> ExecutionContextId `integer`

実行コンテキストの ID。


---

### <a name="exceptiondetails"></a> ExceptionDetails `object`

スクリプトのコンパイルまたは実行中にスローされた例外 (またはエラー) に関する詳細情報。

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
            <td>exceptionId</td>
            <td><code class="flyout">integer</code></td>
            <td>例外 ID。</td>
        </tr>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>例外テキスト。利用可能な場合は例外オブジェクトと共に使用する必要があります。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>例外の場所の行番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>例外の場所の列番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>scriptId <br/> <i>オプション</i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>例外の場所のスクリプト ID。</td>
        </tr>
        <tr>
            <td>url <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スクリプトが報告されていないときに使用される例外の場所の URL。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>オプション</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>JavaScript スタック トレース (利用可能な場合)。</td>
        </tr>
        <tr>
            <td>exception <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>Exception オブジェクト (使用可能な場合)。</td>
        </tr>
        <tr>
            <td>executionContextId <br/> <i>オプション</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>例外が発生したコンテキストの識別子。</td>
        </tr>
    </tbody>
</table>

---

### <a name="timestamp"></a> タイムスタンプ `integer`

エポックからのミリ秒単位の値です。


---

### <a name="callframe"></a> CallFrame `object`

ランタイム エラーとアサーションのスタック エントリ。

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
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 関数名。</td>
        </tr>
        <tr>
            <td>scriptId</td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>JavaScript スクリプト ID。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript スクリプト名または URL。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript スクリプト行番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript スクリプトの列番号 (0 ベース)。</td>
        </tr>
    </tbody>
</table>

---

### <a name="stacktrace"></a> StackTrace `object`

アサーションまたはエラー メッセージの呼び出しフレーム。

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
            <td>description <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>このスタック トレースの文字列ラベル。 非同期トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</td>
        </tr>
        <tr>
            <td>callFrames</td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td>JavaScript 関数名。</td>
        </tr>
        <tr>
            <td>parent <br/> <i>オプション</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>このスタックより前の非同期 JavaScript スタック トレース (利用可能な場合)。</td>
        </tr>
    </tbody>
</table>

---
