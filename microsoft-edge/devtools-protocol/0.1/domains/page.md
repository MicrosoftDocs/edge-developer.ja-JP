---
description: ページドメインの参照。 検査されたページに関連するアクションとイベントは、ページドメインに属しています。
title: ページドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1602673eae1c04f60046a898dbadeab1b59f9ce5
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882941"
---
# ページドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)  

検査されたページに関連するアクションとイベントは、ページドメインに属しています。

| | |
|-|-|
| [**メソッド**](#methods) | [有効化](#enable)、[無効化](#disable)、[移動](#navigate) |
| [**型**](#types) | [フレーム Id](#frameid) |
## メソッド

### [有効]
ページドメインの通知を有効にします。


---

### [無効]
ページドメインの通知を無効にします。


---

### ナビゲート
指定した URL に現在のページを移動します。

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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>フレーム Id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b>的. </b></span>移動されるフレーム id。</td>
        </tr>
    </tbody>
</table>

---

## 型

### <a name="frameid"></a> フレーム Id `string`

一意のフレーム識別子。


---
