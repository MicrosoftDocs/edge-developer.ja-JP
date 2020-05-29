---
description: オーバーレイドメインの参照。 オーバーレイドメインは、視覚表示修飾要素とノード選択の相互作用を公開します。
title: オーバーレイドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: a7657e2abc99e45894f19f6557f12f78f8ee9c75
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569599"
---
# オーバーレイ
オーバーレイドメインは、視覚表示修飾要素とノード選択の相互作用を公開します。

| | |
|-|-|
| [**メソッド**](#methods) | [有効化](#enable)、[無効化](#disable)、 [setInspectMode](#setinspectmode) |
| [**イベント**](#events) | [inspectNodeRequested](#inspectnoderequested)、 [nodeHighlightRequested](#nodehighlightrequested) |
| [**依存関係**](#dependencies) | [DOM](dom.md) |
## メソッド

### [有効]
およびイベントの報告を有効に <code>nodeHighlightRequested</code> します <code>inspectElementRequested</code>

</p>

---

### [無効]
オーバーレイドメインイベントのレポートを無効にします

</p>

---

### setInspectMode
クライアントの要素選択モードを設定します

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
            <td>モード</td>
            <td><code class="flyout">string</code></td>
            <td>検査モード。  有効な値は、"searchForNode" と "none" です。</td>
        </tr>
        <tr>
            <td>highlightConfig <br/> <i>オプション</i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td>調査中に使用する強調表示構成</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### inspectNodeRequested
ユーザーが特定のノードを検査するよう求めたことをクライアントに通知します。

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
            <td>backendNodeId</td>
            <td><a href="dom.md#backendnodeid"><code class="flyout">DOM.BackendNodeId</code></a></td>
            <td>要求されたノードのバックエンドノード ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### nodeHighlightRequested
ユーザーがノードの上にマウスポインターを置いて、ノードを検査することを示します。

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
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td>考慮対象のノードのノード ID</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依存関係

[DOM](dom.md)