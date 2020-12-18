---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7b4ec71b7799ae099c673bd81fa5b15a8ddd5d27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234794"
---
# スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

プロトコル スキーマに関する情報を提供します。

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
            <th>戻り値</th>
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

---

## 型

### <a name="domain"></a> ドメイン `object`

プロトコル ドメインの説明。

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
            <td>ドメインのバージョン。</td>
        </tr>
    </tbody>
</table>

---
