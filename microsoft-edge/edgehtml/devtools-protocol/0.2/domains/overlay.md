---
description: オーバーレイ ドメインのリファレンス。 オーバーレイ ドメインは視覚的な視覚効果とノード選択操作を公開します。
title: オーバーレイ ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dcf5feff9983aa2e9e61ac0569938988812165f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234410"
---
# オーバーレイ

オーバーレイ ドメインは視覚的な視覚効果とノード選択操作を公開します

| | |
|-|-|
| [**メソッド**](#methods) | [有効](#enable)、[無効](#disable)[、setInspectMode](#setinspectmode) |
| [**イベント**](#events) | [inspectNodeRequested](#inspectnoderequested)、 [nodeHighlightRequested](#nodehighlightrequested) |
| [**依存関係**](#dependencies) | [DOM](dom.md) |
## メソッド

### [有効]
レポートとイベント <code>nodeHighlightRequested</code> を有効 <code>inspectElementRequested</code> にする

</p>

---

### [無効]
オーバーレイ ドメイン イベントのレポートを無効にします

</p>

---

### setInspectMode
クライアントの要素選択モードを設定します。

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
            <td>検査モード。  有効な値は、'searchForNode' および 'none' です。</td>
        </tr>
        <tr>
            <td>highlightConfig <br/> <i>オプション</i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td>検査中に使用する強調表示の構成</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### inspectNodeRequested
ユーザーが特定のノードを検査するメッセージをクライアントに通知します。

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
            <td>要求されたノードのバックエンド ノード ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### nodeHighlightRequested
ユーザーがノードの上にマウス ポインターを移動し、ノードを検査する可能性を示します。

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
            <td>考慮するノードのノード ID</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依存関係

[DOM](dom.md)
