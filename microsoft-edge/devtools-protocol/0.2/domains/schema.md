---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: d0fbe9cde742d255797a2460b940732ffa5b8f27
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882878"
---
# スキーマドメイン-DevTools プロトコルバージョン 0.2 (EdgeHTML)  

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
