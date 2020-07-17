---
description: Runtime ドメインの参照。 ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
title: ランタイムドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 710b3b3e0383f1f6feb7947e0468730d2e0b0e66
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882864"
---
# ランタイムドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)  

ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [evaluate](#evaluate)、 [callfunctionon](#callfunctionon)、 [waitpromise](#awaitpromise)、 [getProperties](#getproperties)、 [globalLexicalScopeNames](#globallexicalscopenames)、 [releaseobject](#releaseobject)、 [releaseobjectgroup](#releaseobjectgroup)、 [discardConsoleEntries](#discardconsoleentries) |
| [**イベント**](#events) | [Executioncontextcreated](#executioncontextcreated)、 [executioncontextcreated](#executioncontextdestroyed)、 [executioncontextsクリアー](#executioncontextscleared)、 [exceptionthrown](#exceptionthrown)、 [consoleAPICalled](#consoleapicalled) |
| [**型**](#types) | [Scriptid](#scriptid)、 [remoteobjectid](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [remoteobjectid](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [callargument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [executioncontextdescription](#executioncontextdescription)、 [exceptiondetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [callargument](#callframe)、 [StackTrace](#stacktrace) |
## メソッド

### [有効]
およびイベントのレポートを有効にし <code>executionContextCreated</code> <code>executionContextDestroyed</code> <code>executionContextsCleared</code> ます。 レポートを有効にすると、 <code>executionContextCreated</code> 既存の実行コンテキストごとに、イベントが直ちに送信されます。

</p>

---

### [無効]
およびイベントの報告を無効 <code>executionContextCreated</code> にし <code>executionContextDestroyed</code> <code>executionContextsCleared</code> ます。

</p>

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
            <td>includeCommandLineAPI <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>評価中にコマンドライン API を使用できるかどうかを決定します。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>複数のオブジェクトを解放するために使用できるシンボリックグループ名。</td>
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
</p>

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
        <tr>
            <td>executionContextId <br/> <i>オプション</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>関数の呼び出しに使用するグローバルオブジェクトを指定します。 ExecutionContextId または objectId のいずれかを指定する必要があります。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>複数のオブジェクトを解放するために使用できるシンボリックグループ名。 ObjectGroup が指定されておらず、objectId が指定されていない場合、objectGroup は object から継承されます。</td>
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
</p>

---

### awaitPromise
指定された promise オブジェクト id を使用して、約束にハンドラーを追加します。

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
            <td>promiseObjectId</td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>約束の識別子。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>結果が、値によって送信される必要がある JSON オブジェクトであると想定されるかどうか。</td>
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
            <td>約束の結果。  Promise が拒否された場合は、拒否されます。</td>
        </tr>
    </tbody>
</table>
</p>

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
            <td>プロパティを返すオブジェクトの識別子。 objectId はデバッガーからである必要があります。 evaluateOnCallFrame () 関数。</td>
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
</p>

---

### globalLexicalScopeNames
すべての let、const、および class 変数を本体のグローバルスコープから返します。

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
            <td>名</td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### releaseObject
指定した id のリモートオブジェクトを解放します。

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
            <td>解放するオブジェクトの識別子。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### releaseObjectGroup
指定したグループに属しているすべてのリモートオブジェクトを解放します。

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
            <td>objectGroup</td>
            <td><code class="flyout">string</code></td>
            <td>シンボリックオブジェクトグループ名。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### discardConsoleEntries
収集された例外とコンソール API の呼び出しを破棄します。

</p>

---

## イベント

### executionContextCreated
新しい実行コンテキストが作成されたときに発行されます。

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
            <td>context</td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td>新しく作成された実行コンテキスト。</td>
        </tr>
    </tbody>
</table>
</p>

---

### executionContextDestroyed
実行コンテキストが破棄されたときに発行されます。

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
            <td>executionContextId</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>破棄されたコンテキストの Id</td>
        </tr>
    </tbody>
</table>
</p>

---

### executionContextsCleared
ブラウザーですべての executionContexts が消去されたときに発行される

</p>

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
</p>

---

### consoleAPICalled


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
            <td>型</td>
            <td><code class="flyout">string</code> <br/> <i>許可される値: ログ、情報、警告、エラー、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、Startgroup折りたたまれた、endGroup</i></td>
            <td>通話の種類。 これには、ログ、情報、警告、エラー、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、Groupcollapsed が含まれます。</td>
        </tr>
        <tr>
            <td>引数</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td>引数を呼び出します。</td>
        </tr>
        <tr>
            <td>executionContextId</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>本体の呼び出しが行われたコンテキストの識別子</td>
        </tr>
        <tr>
            <td>示 <br/> <i>オプション</i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>通話のタイムスタンプ。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>オプション</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>使用可能な場合にスタックトレースがキャプチャされる</td>
        </tr>
    </tbody>
</table>
</p>

---

## 型

### <a name="scriptid"></a> ScriptId `string`

一意のスクリプト識別子。

</p>

---

### <a name="remoteobjectid"></a> RemoteObjectId `string`

一意のオブジェクト識別子。

</p>

---

### <a name="unserializablevalue"></a> UnserializableValue `string`

Stringified にすることができないプリミティブ値。

##### 許可される値
無限大、NaN、-無限大、-0
</p>

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
            <td><code class="flyout">string</code> <br/> <i>許可される値: null、エラー、promise、ノード</i></td>
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
</p>

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
</p>

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
</p>

---

### <a name="executioncontextid"></a> ExecutionContextId `integer`

実行コンテキストの Id です。

</p>

---

### <a name="executioncontextdescription"></a> ExecutionContextDescription `object`

分離世界の説明。

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
            <td>id</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>実行コンテキストの一意の id。 これは、実行コンテキストスクリプトの評価を実行することを指定するために使うことができます。</td>
        </tr>
        <tr>
            <td>cdn</td>
            <td><code class="flyout">string</code></td>
            <td>実行コンテキストの起点。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>特定のコンテキストを説明する人間が読める名前。</td>
        </tr>
    </tbody>
</table>
</p>

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
</p>

---

### <a name="timestamp"></a> タイムスタンプ `integer`

エポックからのミリ秒数。

</p>

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
            <td>JavaScript スクリプト id。デバッガーが有効になっていない場合は、ScriptId が空になります。</td>
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
</p>

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
</p>

---
