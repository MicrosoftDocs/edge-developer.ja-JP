---
description: ページドメインの参照。 検査されたページに関連するアクションとイベントは、ページドメインに属しています。
title: ページドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 688cc1fcfce0b81c5eed0c858a4a60b4754c49a4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569601"
---
# Page
検査されたページに関連するアクションとイベントは、ページドメインに属しています。

| | |
|-|-|
| [**メソッド**](#methods) | [有効化](#enable)、[無効化](#disable)、[移動](#navigate)、 [getフレームツリー](#getframetree) |
| [**イベント**](#events) | [フレームアタッチ](#frameattached)、[フレーム分離](#framedetached)、 [framenavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domcontenteventfired](#domcontenteventfired) |
| [**型**](#types) | フレーム[id](#frameid)、[フレーム、フレーム](#frame)[ツリー](#frametree) |
## メソッド

### [有効]
ページドメインの通知を有効にします。

</p>

---

### [無効]
ページドメインの通知を無効にします。

</p>

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
        <tr>
            <td>フレーム Id <br/> <i>オプション</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>移動するフレーム id。 指定しない場合、上のページが移動します。</td>
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
            <td>移動されるフレーム id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### Getフレームツリー
存在するフレームツリー構造体を返します。

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
            <td>フレームツリー</td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td>フレームツリー構造を表示します。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### フレーム添付
フレームが親にアタッチされたときに発生します。

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
            <td>フレーム Id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>添付されたフレームの Id です。</td>
        </tr>
        <tr>
            <td>Parentフレーム Id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>親フレーム識別子。</td>
        </tr>
        <tr>
            <td>スタック <br/> <i>オプション</i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td>フレームがアタッチされたときの JavaScript スタックトレース。 script からフレームが開始された場合にのみ設定されます。</td>
        </tr>
    </tbody>
</table>
</p>

---

### フレームのデタッチ
Frame が親から切り離されたときに発生します。

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
            <td>フレーム Id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>デタッチされたフレームの Id です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### Framのゲート
フレームのナビゲーションが完了した後に発生します。

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
            <td>時間</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>Frame オブジェクト</td>
        </tr>
    </tbody>
</table>
</p>

---

### loadEventFired
Onload イベントに対応しています。

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
            <td>示</td>
            <td><code class="flyout">number</code></td>
            <td>エポックからのミリ秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

### domContentEventFired
OnDOMContentLoaded イベントに対応しています。

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
            <td>示</td>
            <td><code class="flyout">number</code></td>
            <td>エポックからのミリ秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 型

### <a name="frameid"></a> フレーム Id `string`

一意のフレーム識別子。

</p>

---

### <a name="frame"></a> フレーム `object`

ページのフレームに関する情報。

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
            <td>id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>Frame の一意の識別子。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>オプション</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>親フレームの一意の識別子。</td>
        </tr>
        <tr>
            <td>name <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>タグで指定されているフレームの名前。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>フレームドキュメントの URL。</td>
        </tr>
        <tr>
            <td>securityOrigin</td>
            <td><code class="flyout">string</code></td>
            <td>フレームドキュメントのセキュリティ基準。</td>
        </tr>
        <tr>
            <td>Mime</td>
            <td><code class="flyout">string</code></td>
            <td>ブラウザーで決定されるフレームドキュメントの Mime。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> フレームツリー `object`

フレーム階層に関する情報。

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
            <td>時間</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>このツリー項目のフレーム情報。</td>
        </tr>
        <tr>
            <td>childFrames <br/> <i>オプション</i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td>子フレーム。</td>
        </tr>
    </tbody>
</table>
</p>

---
