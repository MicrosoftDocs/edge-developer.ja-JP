---
description: DOM ドメインの参照。 このドメインは DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、が含まれているミラーオブジェクトで表され `id` ます。 これを使って、 `id` ノードの追加情報を取得したり、JavaScript オブジェクトラッパーなどに解決したりすることができます。クライアントが認識しているノードでのみ DOM イベントを受信することが重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを2回送信することはありません。 クライアントに送信されたノードに関する情報は、クライアント側で収集する必要があります。<p>`iframe`Owner 要素は、子ノードとして対応するドキュメント要素を返します。</p>
title: DOM ドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 9ebe5ff709ac2981cb2359b7279c5d4e5d375426
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569606"
---
# DOM
このドメインは DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、が含まれているミラーオブジェクトで表され `id` ます。 これを使って、 `id` ノードの追加情報を取得したり、JavaScript オブジェクトラッパーなどに解決したりすることができます。クライアントが認識しているノードでのみ DOM イベントを受信することが重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを2回送信することはありません。 クライアントに送信されたノードに関する情報は、クライアント側で収集する必要があります。<p>`iframe`Owner 要素は、子ノードとして対応するドキュメント要素を返します。</p>

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [getdocument](#getdocument)、 [highlightNode](#highlightnode)、 [hidehighlight 表示](#hidehighlight)、 [requestchildnodes](#requestchildnodes)、 [getdocument](#getattributes) [、](#getouterhtml)getdocument、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)、 [queryselector](#queryselector)、 [querySelectorAll](#queryselectorall)、 [requestnode](#requestnode)、 [resolveNode](#resolvenode)、 [setInspectedNode](#setinspectednode) |
| [**イベント**](#events) | [Setchildnodes](#setchildnodes)、 [attributeModified](#attributemodified)、 [attributeRemoved](#attributeremoved)、 [characterDataModified](#characterdatamodified)、 [childnodeinserted](#childnodeinserted)、 [childNodeRemoved](#childnoderemoved)、 [documentupdated](#documentupdated) |
| [**型**](#types) | [RGBA](#rgba)、 [HighlightConfig](#highlightconfig)、 [NodeId](#nodeid)、 [Node](#node)、 [backendnodeid](#backendnodeid)、[擬似型](#pseudotype) |
| [**依存関係**](#dependencies) | [言語](runtime.md) |
## メソッド

### [有効]
指定したページについて DOM agent を有効にします。

</p>

---

### [無効]
指定されたページの DOM エージェントを無効にします。 DOM を無効にすると、以前の有効な nodeIds が無効になります。

</p>

---

### getDocument
ルート DOM ノード (および必要に応じてサブツリー) を呼び出し元に返します。 通話 `getDocument` によって、以前に有効になったすべての nodeIds が無効になります

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
            <td>奥行</td>
            <td><code class="flyout">integer</code></td>
            <td>子が取得される最大の深度。既定値は2です。 サブツリー全体に-1 を使用します。</td>
        </tr>
        <tr>
            <td>貫通</td>
            <td><code class="flyout">boolean</code></td>
            <td>サブツリーを返すときに iframe を走査するかどうか (既定は false)。</td>
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
            <td>根本的</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>結果ノード。</td>
        </tr>
    </tbody>
</table>
</p>

---

### highlightNode
指定した id またはオブジェクトラッパーの Higlights DOM ノード。 nodeId、backendNodeId、または objectId を指定する必要があります。

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
            <td>強調表示するバックエンドノードの id です。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>強調表示されるノードの JavaScript オブジェクト id。</td>
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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>根本的</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>結果ノード。</td>
        </tr>
    </tbody>
</table>
</p>

---

### hideHighlight 表示
現在の DOM ノードの強調表示を非表示にします。

</p>

---

### requestChildNodes
指定した id を持つノードの子が、イベント形式で ghe 呼び出し元に返されるように要求 `setChildNodes` します。 `setChildNodes` これは、要求されたノードから指定された深さまで、前に子が返されていないノードごとに発生します。

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
            <td>子を取得するノードの Id です。</td>
        </tr>
        <tr>
            <td>奥行</td>
            <td><code class="flyout">integer</code></td>
            <td>子が取得される最大の深度。既定値は1です。 サブツリー全体に-1 を使用します。</td>
        </tr>
        <tr>
            <td>貫通</td>
            <td><code class="flyout">boolean</code></td>
            <td>サブツリーを返すときに iframe を走査するかどうか (既定は false)。</td>
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
            <td>Attibutes を取得するノードの Id です。</td>
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
            <td>属性</td>
            <td><code class="flyout">string[]</code></td>
            <td>ノード属性名と値のインターリーブ配列。</td>
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
            <td>ノードの識別子です。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>オプション</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>バックエンドノードの識別子。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>オプション</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>ノードラッパーの JavaScript オブジェクト id。</td>
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
            <td>outerHTML</td>
            <td><code class="flyout">string</code></td>
            <td>外部の HTML マークアップ。</td>
        </tr>
    </tbody>
</table>
</p>

---

### pushNodesByBackendIdsToFrontend
ノード Id を検索し、指定したバックエンドノード Id の親をすべて解決します

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
            <td>解決するノードのバックエンドノード Id</td>
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
            <td>nodeIds</td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>解決されたノードのノード Id</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelector
`querySelector`指定したノードで実行します。

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
            <td>照会するノードの Id です。</td>
        </tr>
        <tr>
            <td>スイッチ</td>
            <td><code class="flyout">string</code></td>
            <td>セレクター文字列。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>クエリセレクターの結果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelectorAll
`querySelectorAll`指定したノードで実行します。

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
            <td>照会するノードの Id です。</td>
        </tr>
        <tr>
            <td>スイッチ</td>
            <td><code class="flyout">string</code></td>
            <td>セレクター文字列。</td>
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
            <td>nodeIds</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>クエリセレクターの結果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### requestNode
指定したリモートオブジェクト Id を持つノードが発信者に送信されるように要求します。 ノードからルートへのパスを形成するすべてのノードは、一連の通知としてクライアントにも送信され `setChildNodes` ます。 要求されたノードを含むドキュメントがクライアントによって要求されていない場合は、0を返します。

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
            <td>ノードに変換する JavaScript オブジェクト Id。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>指定されたオブジェクトのノード Id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### resolveNode
指定された NodeId または BackendNodeId の JavaScript ノードオブジェクトを解決します。

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
            <td>解決するノードの Id です。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>オプション</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>解決するノードのバックエンドノード Id。</td>
        </tr>
        <tr>
            <td>objectGroup</td>
            <td><code class="flyout">string</code></td>
            <td>複数のオブジェクトを解放するために使用できるシンボリックグループ名。</td>
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
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>指定したノードの JavaScript オブジェクトラッパー。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setInspectedNode
<span><b>的. </b></span>$0-$ 4 経由で、指定した id の以前の検査済みノードを本体で参照できるようにします。

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
            <td>DOM ノード id にアクセスするには、コマンドライン API で $0-$ 4 を使います。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### setChildNodes
バックエンドが、DOM 構造が見つからないクライアントを提供するときに発生します。 これは、ほとんどの呼び出しで nodeIds を要求している場合に発生します。

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
            <td>子がある poplate の親ノード。</td>
        </tr>
        <tr>
            <td>ノード</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>子ノードの配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeModified
`Element`属性が変更されたときに発生します。

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
            <td>変更されたノードの Id です。</td>
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
属性が削除されたときに発生 `Element` します。

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
            <td>変更されたノードの Id です。</td>
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
ミラー `DOMCharacterDataModified` イベント。

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
            <td>変更されたノードの Id です。</td>
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
ミラー `DOMNodeInserted` イベント。

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
            <td>変更されたノードの Id です。</td>
        </tr>
        <tr>
            <td>前の Nodeid</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>挿入されたノードの前の兄弟の Id です。</td>
        </tr>
        <tr>
            <td>ノード</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>挿入されたノードデータ。</td>
        </tr>
    </tbody>
</table>
</p>

---

### childNodeRemoved
ミラー `DOMNodeRemoved` イベント。

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
            <td>変更されたノードの Id です。</td>
        </tr>
        <tr>
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>削除されたノードの Id です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### ドキュメントが更新されました
`Document`が全体的に更新されたときに発生します。 ノード id が無効になりました。

</p>

---

## 型

### <a name="rgba"></a> RGBA `object`

RGBA 色を保持する構造体。

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
            <td>終点</td>
            <td><code class="flyout">integer</code></td>
            <td>赤のコンポーネント。 [0-255] 範囲。</td>
        </tr>
        <tr>
            <td>agdlp</td>
            <td><code class="flyout">integer</code></td>
            <td>緑のコンポーネント。 [0-255] 範囲。</td>
        </tr>
        <tr>
            <td>]5d</td>
            <td><code class="flyout">integer</code></td>
            <td>青の要素。 [0-255] 範囲。</td>
        </tr>
        <tr>
            <td>a <br/> <i>オプション</i></td>
            <td><code class="flyout">number</code></td>
            <td>アルファコンポーネント。 [0-1] 範囲。 既定値は 1 です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> HighlightConfig `object`

ページ要素の強調表示用の構成データ。

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
            <td>[コンテンツ] ボックスが強調表示された塗りつぶしの色。 Default は透過的です。</td>
        </tr>
        <tr>
            <td>paddingColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>パディングの強調表示の色。 Default は透過的です。</td>
        </tr>
        <tr>
            <td>borderColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>境界線の塗りつぶしの色が強調表示されます。 Default は透過的です。</td>
        </tr>
        <tr>
            <td>marginColor <br/> <i>オプション</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>余白には塗りつぶしの色が強調表示されています。 Default は透過的です。</td>
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
            <td>このノードを参照するために使用されるノード識別子。 バックエンドは、クライアントが認識している nodeId を持つノードについて、DOM イベントを発生させます。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>オプション</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>親ノードのノード識別子 (存在する場合)。</td>
        </tr>
        <tr>
            <td>backendNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>ノードのバックエンドノード識別子。 BackendNodeIds はクライアントに対して知っている可能性があるが、このノードについては DOM イベントをプッシュしません。</td>
        </tr>
        <tr>
            <td>nodeType</td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`の nodeType。</td>
        </tr>
        <tr>
            <td>nodeName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`の nodeName。</td>
        </tr>
        <tr>
            <td>localName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`の localName</td>
        </tr>
        <tr>
            <td>nodeValue</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`の nodeValue</td>
        </tr>
        <tr>
            <td>childNodeCount <br/> <i>オプション</i></td>
            <td><code class="flyout">integer</code></td>
            <td>ノードの子カウント `Container` 。</td>
        </tr>
        <tr>
            <td>子供 <br/> <i>オプション</i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>子が要求されたときの、このノードの子ノード。</td>
        </tr>
        <tr>
            <td>属性 <br/> <i>オプション</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>`Element`フラット配列 ' [name1, value1, name2, value2] の形式のノードの属性</td>
        </tr>
        <tr>
            <td>documentURL <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>ノードが指しているドキュメントの URL `Document` 。</td>
        </tr>
        <tr>
            <td>baseURL <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document`ノードが url の完了に使用するドキュメント URL。</td>
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
            <td>internalSubset セット <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` ノードの internalSubset セット。</td>
        </tr>
        <tr>
            <td>xmlVersion <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` XML ドキュメントの場合、ノードの xml バージョン。</td>
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
            <td>フレーム Id <br/> <i>オプション</i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td>Frame owner 要素のフレーム ID。</td>
        </tr>
        <tr>
            <td>contentDocument <br/> <i>オプション</i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>Frame owner 要素のコンテンツドキュメント。</td>
        </tr>
        <tr>
            <td>isSVG <br/> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>ノードが SVG の場合は True です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> BackendNodeId `integer`

フロントエンドにプッシュされていない可能性があるノードを参照するために使用される一意の DOM ノード識別子。

</p>

---

### <a name="pseudotype"></a> 擬似の型 `string`

疑似要素型。

##### 許可される値
1行目、1文字目、前、後、選択範囲
</p>

---

## 依存関係

[言語](runtime.md)