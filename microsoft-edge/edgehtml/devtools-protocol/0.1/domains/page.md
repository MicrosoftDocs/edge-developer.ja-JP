---
description: ページ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属しています。
title: ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55575e54b9125d7ff544c23c81da4b15d3b56fb1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234801"
---
# ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

検査されたページに関連するアクションとイベントは、ページ ドメインに属しています。

| | |
|-|-|
| [**メソッド**](#methods) | [有効、](#enable)[無効、](#disable)[移動](#navigate) |
| [**型**](#types) | [FrameId](#frameid) |
## メソッド

### [有効]
ページ ドメイン通知を有効にします。


---

### [無効]
ページ ドメイン通知を無効にします。


---

### ナビゲート
現在のページを特定の URL に移動します。

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
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>ページの移動先の URL。</td>
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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b>試験的。 </b></span>移動するフレーム ID です。</td>
        </tr>
    </tbody>
</table>

---

## 型

### <a name="frameid"></a> FrameId `string`

一意のフレーム識別子。


---
