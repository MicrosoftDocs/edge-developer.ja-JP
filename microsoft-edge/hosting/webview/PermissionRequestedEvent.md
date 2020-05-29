---
description: 現在の権限要求に関するイベント情報を提供します。
title: PermissionRequestedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/04/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 07fccebc9e061d4ee7a85e48271aaf9c0574e1ef
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570660"
---
# PermissionRequestedEvent オブジェクト

現在のアクセス許可要求に関するイベント情報を提供します。

```js
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    switch (permissionRequest.type) {
        case "geolocation":
        case "media":
        case "pointerlock":
        case "webnotifications":
        case "screen":
        case "immersiveview":
            if (permissionRequest.uri.startsWith("https://www.example.com/")) {
                // Implicitly trust particular URI
                permissionRequest.allow();
            }
            else if (permissionRequest.uri.startsWith("https://")) {
                // Defer the request so we can ask the user to allow or deny the request
                permissionRequest.defer();
                // Later we'll need to use webview.getDeferredPermissionRequestById for this
                // request and call allow or deny.
                promptUserForDeferredPermissionRequest(
                    permissionRequest.id,
                    permissionRequest.uri,
                    permissionRequest.type);
            }
            else {
                // Implicitly deny non-https URIs
                permissionRequest.deny();
            }
            break;

        case "unlimitedIndexedDBQuota":
        default:
            permissionRequest.deny();
            break;
    }
});
```

## プロパティ

### permissionRequest

[Webview](../webview.md)のコンテンツによって行われたエンドユーザーのアクセス許可要求を表す**[permissionrequest](permissionrequest.md)** オブジェクトを返します。

このプロパティは読み取り専用です。
