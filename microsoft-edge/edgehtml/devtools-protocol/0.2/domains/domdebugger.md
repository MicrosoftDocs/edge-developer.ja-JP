---
description: DOMDebugger ドメインのリファレンス。 DOM デバッグでは、特定の DOM 操作とイベントにブレークポイントを設定できます。 JavaScript の実行は、通常のブレークポイント セットがある場合と同様に、これらの操作で停止します。
title: DOMDebugger ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97a9a8f2d0e49166f5f081e8bb0c0d5d3cdd93f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234412"
---
# DOMDebugger

DOM デバッグでは、特定の DOM 操作とイベントにブレークポイントを設定できます。 JavaScript の実行は、通常のブレークポイント セットがある場合と同様に、これらの操作で停止します。

| | |
|-|-|
| [**メソッド**](#methods) | [setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint) |
## メソッド

### setInstrumentationBreakpoint
<span><b>試験的。 </b></span>特定のネイティブ イベントにブレークポイントを設定します。

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
            <td>eventName</td>
            <td><code class="flyout">string</code></td>
            <td>停止するインストルメンテーション名。 有効な値: 'scriptFirstStatement'。</td>
        </tr>
    </tbody>
</table>
</p>

---

### removeInstrumentationBreakpoint
<span><b>試験的。 </b></span>特定のネイティブ イベントのブレークポイントを削除します。

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
            <td>eventName</td>
            <td><code class="flyout">string</code></td>
            <td>停止するインストルメンテーション名。 有効な値: 'scriptFirstStatement'。</td>
        </tr>
    </tbody>
</table>
</p>

---
