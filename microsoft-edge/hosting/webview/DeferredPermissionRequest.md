---
description: デバイス機能にアクセスするためのユーザーアクセス許可の遅延要求を表します。
title: DeferredPermissionRequest オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 6013f20195fc0f5d4f33b871a9c1b01392bf023e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569246"
---
# DeferredPermissionRequest オブジェクト

特殊なデバイス機能 (地理位置情報、ポインターロックなど) にアクセスするために、 [webview](../webview.md)のコンテンツによるエンドユーザーアクセス許可の遅延要求を表します。

```js
// In this sample, when we receive a permission request we construct some basic UI to ask the
// user if they want to give permission.
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    const requestContainer = document.createElement("div");

    // We use this function as the handler for the allow and deny buttons.
    function completeDeferredPermissionRequest(allow) {
        // Find the DeferredPermissionRequest using the id of the PermissionRequest we deferred.
        const deferredPermissionRequest = webview.getDeferredPermissionRequestById(permissionRequest.id);
        if (allow) {
            deferredPermissionRequest.allow();
        }
        else {
            deferredPermissionRequest.deny();
        }
        requestContainer.parentElement.removeChild(requestContainer);
    }

    // Construct some simple UI to tell the user about the permission request and get their
    // feedback via the allow and deny buttons
    const description = document.createElement("span");
    description.textContent = "Allow " + uri + " to access " + type + "?";

    const allow = document.createElement("button");
    allow.textContent = "Allow";
    allow.addEventListener("click", () => completeDeferredPermissionRequest(true));

    const deny = document.createElement("button");
    deny.textContent = "Deny";
    deny.addEventListener("click", () => completeDeferredPermissionRequest(false));

    requestContainer.appendChild(description);
    requestContainer.appendChild(allow);
    requestContainer.appendChild(deny);
    document.body.appendChild(requestContainer);

    permissionRequest.defer();
});
```

## メソッド

### 許可

許可の要求を許可します。

```js
deferredPermissionRequest.allow();
```

#### パラメーター

このメソッドにはパラメーターはありません。

#### 戻り値

このメソッドに戻り値はありません。

### 拒否

権限のリクエストを拒否します。

```js
deferredPermissionRequest.deny();
```

#### パラメーター

このメソッドにはパラメーターはありません。

#### 戻り値

このメソッドに戻り値はありません。

## プロパティ

### id

以前の MSWebViewPermissionRequested されたイベントの PermissionRequest オブジェクトと現在の DeferredPermissionRequest を関連付けるために使用できる一意の ID。 **Permissionrequested さ**れた defer メソッドを参照してください。

このプロパティは読み取り専用です。

```js
var id = deferredPermissionRequest.id;
```

##### プロパティ値

種類:**符号なし長**

### 型

要求されるアクセス許可の種類。 これは、次のいずれかの文字列値になります。

- **位置**情報: ナビゲータ経由で位置情報にアクセスします。
- **unlimitedIndexedDBQuota**: IndexedDB api が、保存されている通常のデータサイズの制限を無視することを許可します。
- **メディア**: ナビゲータメディアからのマイクとカメラへのアクセス。
- **pointerlock**ロック: 要素の requestPointerLock ロックを使って、マウスポインターのロックと制御を行うことができます。
- **webnotifications**: window 経由でデスクトップ通知を表示することができます。知ら.
- **画面**: メディアキャプチャ API を使ってスクリーンショットを撮ることができます。
- **immersiveview**: VR ディスプレイを制御できます。

このプロパティは読み取り専用です。

```js
var type = deferredPermissionRequest.type;
```

#### プロパティ値

種類:**文字列**

### uri

アクセス許可を要求するドキュメントの Uniform Resource Identifier (URI)。

このプロパティは読み取り専用です。

```js
var uri = deferredPermissionRequest.uri;
```

##### プロパティ値

種類:**文字列**

## 要件

|                                           |                                      |
|-------------------------------------------|--------------------------------------|
| <strong>サポートされている最小クライアント数</strong> | Windows 10 [Windows ストアアプリのみ] |
| <strong>サポートされている最小のサーバー</strong> |            サポートされていないアプリ             |
| <strong>サポートされている最小電話</strong>  |            サポートされていないアプリ             |
