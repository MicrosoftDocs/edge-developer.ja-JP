---
description: DOMDebugger ドメインの参照。 DOM デバッグでは、特定の DOM 操作およびイベントに対してブレークポイントを設定することができます。 通常のブレークポイントが設定されている場合と同様に、JavaScript の実行はこの操作によって停止されます。
title: DOMDebugger ドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 437a88ff93bda36d85a8f5632c1a02aa205d049b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569600"
---
# DOMDebugger
DOM デバッグでは、特定の DOM 操作およびイベントに対してブレークポイントを設定することができます。 通常のブレークポイントが設定されている場合と同様に、JavaScript の実行はこの操作によって停止されます。

| | |
|-|-|
| [**メソッド**](#methods) | [setInstrumentationBreakpoint](#setinstrumentationbreakpoint)、 [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint) |
## メソッド

### setInstrumentationBreakpoint
<span><b>的. </b></span>特定のネイティブイベントにブレークポイントを設定します。

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
            <td>停止するインストルメンテーション名。 有効な値: ' scriptFirstStatement '。</td>
        </tr>
    </tbody>
</table>
</p>

---

### removeInstrumentationBreakpoint
<span><b>的. </b></span>特定のネイティブイベントのブレークポイントを削除します。

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
            <td>停止するインストルメンテーション名。 有効な値: ' scriptFirstStatement '。</td>
        </tr>
    </tbody>
</table>
</p>

---
