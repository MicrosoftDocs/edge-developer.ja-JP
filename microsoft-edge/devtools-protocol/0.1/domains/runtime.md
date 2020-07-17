---
description: Runtime ドメインの参照。 ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
title: ランタイムドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 15d6cd254ddbe2337e3db850620dc3eb20a5ea67
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882934"
---
# ランタイムドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)  

ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [evaluate](#evaluate)、 [callfunctionon](#callfunctionon)、 [getProperties](#getproperties) |
| [**イベント**](#events) | [Executioncontextscleared](#executioncontextscleared)、 [exceptionthrown](#exceptionthrown) |
| [**型**](#types) | [Scriptid](#scriptid)、 [remoteobjectid](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [remoteobjectid](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [callargument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [exceptiondetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [callargument](#callframe)、 [StackTrace](#stacktrace) |
## メソッド

### [有効]
イベントの報告を有効に <code>executionContextsCleared</code> します。


---

### [無効]
イベントの報告を無効に <code>executionContextsCleared</code> します。


---

### ぜひ
グローバルオブジェクトで式を評価します。

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
            <td>expression</td>
            <td><code class="flyout">string</code></td>
            <td>評価する式。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。 <code>setPauseOnException</code>State の上書き。</td>
        </tr>
        <tr>
            <td>contextId <br/> <i>オプション</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>評価を実行する実行コンテキストを指定します。 パラメーターを省略すると、検査されたページのコンテキストで評価が実行されます。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果が、値によって送信される必要がある JSON オブジェクトであると想定されるかどうか。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</td>
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
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>評価結果。</td>
        </tr>
    </tbody>
</table>

---

### callFunctionOn
指定したオブジェクトで指定された宣言の関数を呼び出します。 結果のオブジェクトグループがターゲットオブジェクトから継承されます。

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
            <td>呼び出す関数の対象となるオブジェクトの識別子。 ObjectId または executionContextId のいずれかを指定する必要があります。  objectId は、evaluate () 関数からのものである必要があります。</td>
        </tr>
        <tr>
            <td>arguments <br/> <i>オプション</i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td>引数を呼び出します。 すべての呼び出し引数は、ターゲットオブジェクトと同じ JavaScript ワールドに属している必要があります。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>サイレントモードでは、評価中にスローされる例外は報告されず、実行を一時停止しません。 <code>setPauseOnException</code>State の上書き。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果が JSON オブジェクトであると想定されるかどうか。値で送信する必要があるかどうか。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果としての値を実行する必要があるかどうか <code>await</code> 、待機中の promise が解決されるかどうか。</td>
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
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>通話の結果。</td>
        </tr>
    </tbody>
</table>

---

### getProperties
指定されたオブジェクトのプロパティを返します。 結果のオブジェクトグループがターゲットオブジェクトから継承されます。

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
            <td>プロパティを返すオブジェクトの識別子。  objectId はデバッガーからである必要があります。 evaluateOnCallFrame () 関数。</td>
        </tr>
        <tr>
            <td>ownProperties <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>True の場合は、プロトタイプチェーンではなく、要素自体にのみ属しているプロパティを返します。</td>
        </tr>
        <tr>
            <td>accessorPropertiesOnly <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>的. </b></span>True の場合は、アクセサープロパティ (getter/setter) のみを返します。内部プロパティは返されません。</td>
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
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td>オブジェクトのプロパティ。</td>
        </tr>
    </tbody>
</table>

---

## イベント

### executionContextsCleared
ブラウザーですべての executionContexts が消去されたときに発行される


---

### 例外のスロー
例外がスローされて処理不能になったときに発行されます。

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
            <td>示</td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>例外のタイムスタンプ。</td>
        </tr>
        <tr>
            <td>例外の詳細</td>
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

Stringified にすることができないプリミティブ値。

##### 許可される値
無限大、NaN、-無限大、-0

---

### <a name="remoteobject"></a> RemoteObject `object`

元の JavaScript オブジェクトを参照する Mirror オブジェクト。

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
            <td><code class="flyout">string</code> <br/> <i>使用できる値: object、関数、undefined、string、number、boolean、symbol</i></td>
            <td>オブジェクトの種類。</td>
        </tr>
        <tr>
            <td>subtype <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code> <br/> <i>指定可能な値: null、エラー、promise</i></td>
            <td>オブジェクトサブタイプのヒント。 型の値のみに指定され <code>object</code> ます。</td>
        </tr>
        <tr>
            <td>名 <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>オブジェクトクラス (コンストラクター) 名。 型の値のみに指定され <code>object</code> ます。</td>
        </tr>
        <tr>
            <td>value <br/> <i>オプション</i></td>
            <td><code class="flyout">any</code></td>
            <td>プリミティブ値または JSON 値に応じたリモートオブジェクトの値 (要求された場合)。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>オプション</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>JSON 値は、JSON では使用できません。 stringified <code>value</code>が、このプロパティを取得します。</td>
        </tr>
        <tr>
            <td>description <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>オブジェクトの文字列表現。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>一意のオブジェクト識別子 (プリミティブ以外の値の場合)。</td>
        </tr>
        <tr>
            <td>msDebuggerPropertyId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>的. </b></span>Microsoft: このオブジェクトに関連付けられているデバッガープロパティ id。</td>
        </tr>
    </tbody>
</table>

---

### <a name="propertydescriptor"></a> PropertyDescriptor `object`

オブジェクトプロパティ記述子。

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
            <td>プロパティ名またはシンボルの説明。</td>
        </tr>
        <tr>
            <td>value <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティに関連付けられた値。</td>
        </tr>
        <tr>
            <td>書き <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティに関連付けられている値が変更される可能性がある場合は True (データ記述子のみ)。</td>
        </tr>
        <tr>
            <td>取得 <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティの getter として機能する関数、または <code>undefined</code> getter (アクセサー記述子のみ) がない場合。</td>
        </tr>
        <tr>
            <td>set <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティの setter として機能する関数、または <code>undefined</code> setter (アクセサー記述子のみ) がない場合。</td>
        </tr>
        <tr>
            <td>構成</td>
            <td><code class="flyout">boolean</code></td>
            <td>このプロパティ記述子の型が変更される可能性がある場合、およびプロパティが対応するオブジェクトから削除される可能性がある場合は True です。</td>
        </tr>
        <tr>
            <td>加算</td>
            <td><code class="flyout">boolean</code></td>
            <td>対応するオブジェクトのプロパティの列挙中にこのプロパティが表示される場合は True です。</td>
        </tr>
        <tr>
            <td>例外 <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>評価中に結果がスローされた場合は True です。</td>
        </tr>
        <tr>
            <td>isOwn <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティがそのオブジェクトに対して所有されている場合は True。</td>
        </tr>
        <tr>
            <td>msReturnValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>的. </b></span>Microsoft: プロパティが戻り値の場合は True です。</td>
        </tr>
        <tr>
            <td>symbol <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>プロパティが型の場合は、プロパティのシンボルオブジェクト `symbol` 。 </td>
        </tr>
    </tbody>
</table>

---

### <a name="callargument"></a> CallArgument `object`

関数呼び出しの引数を表します。 リモートオブジェクト id <code>objectId</code> 、プリミティブ <code>value</code> 、unserializable プリミティブ値、またはどちらも指定しないようにします (未定義の場合)。

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
            <td>Stringified にすることができないプリミティブ値。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>リモートオブジェクトハンドル。</td>
        </tr>
    </tbody>
</table>

---

### <a name="executioncontextid"></a> ExecutionContextId `integer`

実行コンテキストの Id です。


---

### <a name="exceptiondetails"></a> 例外の詳細 `object`

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
            <td>例外 id。</td>
        </tr>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>例外テキスト。利用可能な場合は、exception オブジェクトと共に使用する必要があります。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>例外の場所 (0 ベース) の行番号。</td>
        </tr>
        <tr>
            <td>列番号</td>
            <td><code class="flyout">integer</code></td>
            <td>例外の場所の列番号 (0 ベース)</td>
        </tr>
        <tr>
            <td>scriptId <br/> <i>オプション</i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>例外の場所のスクリプト ID。</td>
        </tr>
        <tr>
            <td>url <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スクリプトが報告されなかったときに使用される、例外の場所の URL です。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>オプション</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>JavaScript スタックトレース (利用可能な場合)。</td>
        </tr>
        <tr>
            <td>エラー <br/> <i>オプション</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>例外オブジェクト (使用可能な場合)。</td>
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

エポックからのミリ秒数。


---

### <a name="callframe"></a> CallFrame `object`

実行時エラーとアサーションのスタックエントリ。

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
            <td>JavaScript スクリプト id。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript スクリプト名または url。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript のスクリプト行番号 (0 ベース)。</td>
        </tr>
        <tr>
            <td>列番号</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript スクリプトの列番号 (0 ベース)。</td>
        </tr>
    </tbody>
</table>

---

### <a name="stacktrace"></a> StackTrace `object`

アサーションまたはエラーメッセージのフレームを呼び出します。

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
            <td>このスタックトレースの文字列ラベル。 Async トレースの場合、これは非同期呼び出しを開始した関数の名前である可能性があります。</td>
        </tr>
        <tr>
            <td>callFrames</td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td>JavaScript 関数名。</td>
        </tr>
        <tr>
            <td>所属 <br/> <i>オプション</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>このスタックの前にある非同期 JavaScript スタックトレース (使用可能な場合)。</td>
        </tr>
    </tbody>
</table>

---
