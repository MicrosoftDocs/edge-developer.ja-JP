---
description: DOM ドメインの参照。 このドメインは、DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、ミラー オブジェクトで表されます `id` 。 これは `id` 、Node に関する追加情報の取得、JavaScript オブジェクト ラッパーへの解決などに使用できます。クライアントが DOM イベントを受け取るのは、クライアントに既知のノードについてのみ重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを 2 回送信する必要はありません。 クライアントに送信されたノードに関する情報を収集する必要があります。<p>所有者要素 `iframe` は、対応するドキュメント要素を子ノードとして返します。</p>
title: DOM ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7d9861a2395f7b24142a41efea9ac599907dec27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234790"
---
# DOM

このドメインは、DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、ミラー オブジェクトで表されます `id` 。 これは `id` 、Node に関する追加情報の取得、JavaScript オブジェクト ラッパーへの解決などに使用できます。クライアントが DOM イベントを受け取るのは、クライアントに既知のノードについてのみ重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを 2 回送信する必要はありません。 クライアントに送信されたノードに関する情報を収集する必要があります。<p>所有者要素 `iframe` は、対応するドキュメント要素を子ノードとして返します。</p>

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [getDocument](#getdocument)、 [highlightNode](#highlightnode)、 [hideHighlight](#hidehighlight)、 [requestChildNodes](#requestchildnodes)、 [getAttributes](#getattributes)、 [getOuterHTML](#getouterhtml)、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), querySelector , [querySelectorAll](#queryselectorall), requestNode , [](#queryselector) [resolveNode](#requestnode), [setInspectedNode](#setinspectednode) [](#resolvenode) |
| [**イベント**](#events) | [setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated) |
| [**型**](#types) | [](#rgba)RGBA、HighlightConfig、NodeId、Node、BackendNodeId [、PseudoType](#pseudotype) [](#highlightconfig) [](#nodeid) [](#node) [](#backendnodeid) |
| [**依存関係**](#dependencies) | [ランタイム](runtime.md) |
## メソッド

### [有効]
指定されたページの DOM エージェントを有効にする。

</p>

---

### [無効]
指定されたページの DOM エージェントを無効にします。 DOM を無効にすると、以前に有効だった nodeId が無効になります。

</p>

---

### getDocument
ルート DOM ノード (および必要に応じてサブツリー) を呼び出し元に返します。 呼 `getDocument` び出しにより、以前に有効だった nodeId が無効になります

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
            <td>depth</td>
            <td><code class="flyout">integer</code></td>
            <td>子を取得する最大深度 (既定値は 2)。 サブツリー全体に -1 を使用します。</td>
        </tr>
        <tr>
            <td>(1)</td>
            <td><code class="flyout">boolean</code></td>
            <td>サブツリーを返す際に iframe をスキャンするかどうかを指定します (既定値は false)。</td>
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
            <td>root</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>結果ノード。</td>
        </tr>
    </tbody>
</table>
</p>

---

### highlightNode
特定の ID またはオブジェクト ラッパーを持つ DOM ノードを休止します。 nodeId、backendNodeId、または objectId を指定する必要があります。

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
            <td>nodeId <br/> <i>オプション</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>強調表示するノードの識別子。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>オプション</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>強調表示するバックエンド ノードの識別子。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>強調表示するノードの JavaScript オブジェクト ID。</td>
        </tr>
        <tr>
            <td>higlightConfig</td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td>強調表示の外観の記述子。</td>
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
            <td>root</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>結果ノード。</td>
        </tr>
    </tbody>
</table>
</p>

---

### hideHighlight
現在の DOM ノードの強調表示を非表示にします。

</p>

---

### requestChildNodes
特定の ID を持つノードの子がイベントの形式で呼び出し元に返される要求 `setChildNodes` 。 `setChildNodes` は、要求されたノードから指定された深さまで、以前に子を返していないノードごとに発生します。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>子を取得するノードの ID。</td>
        </tr>
        <tr>
            <td>depth</td>
            <td><code class="flyout">integer</code></td>
            <td>子を取得する最大深度 (既定値は 1)。 サブツリー全体に -1 を使用します。</td>
        </tr>
        <tr>
            <td>(1)</td>
            <td><code class="flyout">boolean</code></td>
            <td>サブツリーを返す際に iframe をスキャンするかどうかを指定します (既定値は false)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getAttributes
指定されたノードの属性を返します。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>属性を取得するノードの ID。</td>
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
            <td>attributes</td>
            <td><code class="flyout">string[]</code></td>
            <td>ノード属性の名前と値のインターリーブ配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getOuterHTML
ノードの HTML マークアップを返します。

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
            <td>nodeId <br/> <i>オプション</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>ノードの識別子。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>オプション</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>バックエンド ノードの識別子。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>ノード ラッパーの JavaScript オブジェクト ID。</td>
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
            <td>outerHTML</td>
            <td><code class="flyout">string</code></td>
            <td>外部 HTML マークアップ。</td>
        </tr>
    </tbody>
</table>
</p>

---

### pushNodesByBackendIdsToFrontend
ノード ID を検索し、指定されたバックエンド ノード ID のすべての親を解決します。

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
            <td>backendNodeIds</td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td>解決するノードのバックエンド ノードの ID</td>
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
            <td>nodeIds</td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>解決されたノードのノード ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelector
指定された `querySelector` ノードで実行されます。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>クエリを実行するノードの ID。</td>
        </tr>
        <tr>
            <td>selector</td>
            <td><code class="flyout">string</code></td>
            <td>セレクター文字列。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>クエリ セレクターの結果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelectorAll
指定された `querySelectorAll` ノードで実行されます。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>クエリを実行するノードの ID。</td>
        </tr>
        <tr>
            <td>selector</td>
            <td><code class="flyout">string</code></td>
            <td>セレクター文字列。</td>
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
            <td>nodeIds</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>クエリ セレクターの結果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### requestNode
指定されたリモート オブジェクト ID を持つノードが呼び出し元に送信される要求。 ノードからルートへのパスを形成するノードも、一連の通知としてクライアントに送信 `setChildNodes` されます。 要求されたノードを含むドキュメントがクライアントによって要求されていない場合は、0 を返します。

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
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>ノードに変換する JavaScript オブジェクト ID。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>特定のオブジェクトのノード ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### resolveNode
指定された NodeId または BackendNodeId の JavaScript ノード オブジェクトを解決します。

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
            <td>nodeId <br/> <i>オプション</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>解決するノードの ID。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>オプション</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>解決するノードのバックエンド ノード ID。</td>
        </tr>
        <tr>
            <td>objectGroup</td>
            <td><code class="flyout">string</code></td>
            <td>複数のオブジェクトを解放するために使用できるシンボリック グループ名。</td>
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
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>特定のノードの JavaScript オブジェクト ラッパー。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setInspectedNode
<span><b>試験的。 </b></span>コンソールで、ID が $0 ~ $4 の前の検査済みノードを参照できます。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>コマンド ライン API で $0 ~$4 を使用してアクセスできる DOM ノード ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### setChildNodes
バックエンドがクライアントに DOM 構造の欠落を提供する場合に発生します。 これは、nodeIds を要求しているほとんどの呼び出しで発生します。

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
            <td>parentId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>子を含む親ノード。</td>
        </tr>
        <tr>
            <td>nodes</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>子ノードの配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeModified
`Element`'s 属性が変更された場合に発生します。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>変更されたノードの ID。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>属性値。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeRemoved
`Element`'s 属性が削除された場合に発生します。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>変更されたノードの ID。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名。</td>
        </tr>
    </tbody>
</table>
</p>

---

### characterDataModified
Mirrors `DOMCharacterDataModified` イベント。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>変更されたノードの ID。</td>
        </tr>
        <tr>
            <td>charcterData</td>
            <td><code class="flyout">string</code></td>
            <td>新しいテキスト値。</td>
        </tr>
    </tbody>
</table>
</p>

---

### childNodeInserted
Mirrors `DOMNodeInserted` イベント。

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
            <td>parentNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>変更されたノードの ID。</td>
        </tr>
        <tr>
            <td>previousNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>挿入されたノードの前の兄弟の ID。</td>
        </tr>
        <tr>
            <td>node</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>挿入されたノード データ。</td>
        </tr>
    </tbody>
</table>
</p>

---

### childNodeRemoved
Mirrors `DOMNodeRemoved` イベント。

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
            <td>parentNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>変更されたノードの ID。</td>
        </tr>
        <tr>
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>削除されたノードの ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### documentUpdated
完全に `Document` 更新された場合に発生します。 ノード ID が無効です。

</p>

---

## 型

### <a name="rgba"></a> RGBA `object`

RGBA カラーを保持する構造体。

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
            <td>r</td>
            <td><code class="flyout">integer</code></td>
            <td>[0- 255] の範囲の赤いコンポーネント。</td>
        </tr>
        <tr>
            <td>g</td>
            <td><code class="flyout">integer</code></td>
            <td>[0- 255] の範囲の緑のコンポーネント。</td>
        </tr>
        <tr>
            <td>b</td>
            <td><code class="flyout">integer</code></td>
            <td>[0~ 255] の範囲の青色のコンポーネント。</td>
        </tr>
        <tr>
            <td>a <br/> <i>オプション</i></td>
            <td><code class="flyout">number</code></td>
            <td>[0- 1] の範囲のアルファ成分。 既定値は 1 です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> HighlightConfig `object`

ページ要素を強調表示する構成データ。

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
            <td>contentColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>コンテンツ ボックスの強調表示の塗りつぶしの色。 既定値は透明です。</td>
        </tr>
        <tr>
            <td>paddingColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>パディングの強調表示の塗りつぶしの色。 既定値は透明です。</td>
        </tr>
        <tr>
            <td>borderColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>枠線の強調表示の塗りつぶしの色を指定します。 既定値は透明です。</td>
        </tr>
        <tr>
            <td>marginColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>余白の強調表示の塗りつぶしの色。 既定値は透明です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> NodeId `integer`

一意の DOM ノード識別子

</p>

---

### <a name="node"></a> ノード `object`

実際の DOM ノードを表す Mirror オブジェクト。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>このノードを参照するために使用されるノード識別子。 バックエンドは、クライアントに既知の nodeId を持つノードに対して DOM イベントを発生します。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>オプション</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>親 Node のノード識別子 (ノードがある場合)。</td>
        </tr>
        <tr>
            <td>backendNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>ノードのバックエンド ノード識別子。 BackendNodeIds は、クライアントに既知のノードを参照しますが、このノードに関する DOM イベントはプッシュされません。</td>
        </tr>
        <tr>
            <td>nodeType</td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`'s nodeType.</td>
        </tr>
        <tr>
            <td>nodeName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s nodeName.</td>
        </tr>
        <tr>
            <td>localName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s localName</td>
        </tr>
        <tr>
            <td>nodeValue</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s nodeValue</td>
        </tr>
        <tr>
            <td>childNodeCount <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>ノードの子 `Container` 数。</td>
        </tr>
        <tr>
            <td>子供 <br/> <i>オプション</i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>子を指定して要求された場合の、このノードの子ノード。</td>
        </tr>
        <tr>
            <td>attributes <br/> <i>オプション</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>フラット配列 `Element` '[name1, value1, name2, value2] の形式のノードの属性</td>
        </tr>
        <tr>
            <td>documentURL <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ノードが指 `Document` すドキュメント URL。</td>
        </tr>
        <tr>
            <td>baseURL <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ノードが URL の `Document` 完了に使用するドキュメント URL。</td>
        </tr>
        <tr>
            <td>publicId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` ノードの publicId。</td>
        </tr>
        <tr>
            <td>systemId <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` ノードの systemId。</td>
        </tr>
        <tr>
            <td>internalSubset <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` ノードの internalSubset。</td>
        </tr>
        <tr>
            <td>xmlVersion <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` XML ドキュメントの場合のノードの xml バージョン。</td>
        </tr>
        <tr>
            <td>name <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` ノードの名前。</td>
        </tr>
        <tr>
            <td>value <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` ノードの値。</td>
        </tr>
        <tr>
            <td>frameId <br/> <i>オプション</i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td>フレーム所有者要素のフレーム ID。</td>
        </tr>
        <tr>
            <td>contentDocument <br/> <i>オプション</i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>フレーム所有者要素のコンテンツ ドキュメント。</td>
        </tr>
        <tr>
            <td>isSVG <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>ノードが SVG の場合は True。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> BackendNodeId `integer`

フロントエンドにプッシュされていない可能性があるノードを参照するために使用される一意の DOM ノード識別子。

</p>

---

### <a name="pseudotype"></a> PseudoType `string`

擬似要素型。

##### 使用できる値
最初の行、最初の文字、前、後、選択範囲
</p>

---

## 依存関係

[ランタイム](runtime.md)
