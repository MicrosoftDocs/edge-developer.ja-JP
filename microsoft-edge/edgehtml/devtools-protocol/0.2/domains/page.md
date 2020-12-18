---
description: ページ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1849a2e2aa2f53cef9dff5d03ac991d368a6f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234411"
---
# ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

検査されたページに関連するアクションとイベントは、ページ ドメインに属します。

| | |
|-|-|
| [**メソッド**](#methods) | [有効](#enable)、[無効、](#disable)[移動](#navigate)[、getFrameTree](#getframetree) |
| [**イベント**](#events) | [frameAttached](#frameattached)、 [frameDetached](#framedetached)、 [frameNavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domContentEventFired](#domcontenteventfired) |
| [**型**](#types) | [](#frameid)FrameId、Frame、FrameTree [](#frame) [](#frametree) |
## メソッド

### [有効]
ページ ドメイン通知を有効にします。

</p>

---

### [無効]
ページ ドメイン通知を無効にします。

</p>

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
        <tr>
            <td>frameId <br/> <i>オプション</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>移動するフレーム ID。 指定しない場合、トップ ページに移動します。</td>
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
            <td>移動するフレーム ID です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getFrameTree
現在のフレーム ツリー構造を返します。

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
            <td>frameTree</td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td>現在のフレーム ツリー構造。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### frameAttached
フレームが親にアタッチされている場合に発生します。

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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>アタッチされているフレームの ID。</td>
        </tr>
        <tr>
            <td>parentFrameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>親フレーム識別子。</td>
        </tr>
        <tr>
            <td>stack <br/> <i>オプション</i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td>フレームがアタッチされた場合の JavaScript スタック トレース。スクリプトからフレームが開始された場合にのみ設定されます。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameDetached
フレームが親からデタッチされた場合に発生します。

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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>デタッチされたフレームの ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameNavigated
フレームのナビゲーションが完了すると発生します。

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
            <td>frame</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>Frame オブジェクト。</td>
        </tr>
    </tbody>
</table>
</p>

---

### loadEventFired
window.onload イベントに対応します。

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
            <td>timestamp</td>
            <td><code class="flyout">number</code></td>
            <td>エポックからのミリ秒。</td>
        </tr>
    </tbody>
</table>
</p>

---

### domContentEventFired
document.onDOMContentLoaded イベントに対応します。

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
            <td>timestamp</td>
            <td><code class="flyout">number</code></td>
            <td>エポックからのミリ秒。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 型

### <a name="frameid"></a> FrameId `string`

一意のフレーム識別子。

</p>

---

### <a name="frame"></a> フレーム `object`

ページ上のフレームに関する情報。

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
            <td>フレームの一意識別子。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>オプション</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>親フレームの一意識別子。</td>
        </tr>
        <tr>
            <td>name <br/> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>タグで指定されているフレームの名前。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>フレーム ドキュメントの URL。</td>
        </tr>
        <tr>
            <td>securityOrigin</td>
            <td><code class="flyout">string</code></td>
            <td>フレーム ドキュメントのセキュリティの原点。</td>
        </tr>
        <tr>
            <td>mimeType</td>
            <td><code class="flyout">string</code></td>
            <td>ブラウザーによって決まる、ドキュメントの mimeType をフレームします。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> FrameTree `object`

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
            <td>frame</td>
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
