---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: df86e6669956c14b7c905514fc44376f71eaa993
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569594"
---
# スキーマ
プロトコルスキーマに関する情報を提供します。

| | |
|-|-|
| [**メソッド**](#methods) | [getDomains](#getdomains) |
| [**型**](#types) | [ドメイン](#domain) |
## メソッド

### getDomains
サポートされているドメインを返します。

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
            <td>domains</td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td>サポートされているドメインの一覧。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 型

### <a name="domain"></a> ドメイン `object`

プロトコルドメインの説明。

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
            <td>ドメイン名。</td>
        </tr>
        <tr>
            <td>version</td>
            <td><code class="flyout">string</code></td>
            <td>ドメインバージョン。</td>
        </tr>
    </tbody>
</table>
</p>

---
