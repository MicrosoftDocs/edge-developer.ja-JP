---
description: 権限要求に関する情報を提供します。
title: PermissionRequest オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: c769bf122c3ca116d5783b73d0ff4f183d2cd52d
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752117"
---
# PermissionRequest オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

権限要求に関する情報を提供します。 このオブジェクトは、 [Mswebviewpermissionrequested さ](../webview.md#mswebviewpermissionrequested)れた webview イベントのイベント引数の permissionrequest プロパティから取得できます。  

```javascript
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

## メソッド  

### 許可  

許可の要求を許可します。  

#### パラメーター  

このメソッドにはパラメーターはありません。  

#### 戻り値  

このメソッドに戻り値はありません。  

### 延期  

PermissionRequest を同期できるようにするのではなく、ユーザーとのやり取りや、他の非同期操作の実行には、PermissionRequest で defer () を呼び出す必要があります。  これで、PermissionRequest が getDeferredPermissionRequests と getDeferredPermissionRequestById の DeferredPermissionRequest として利用できるようになります。  一致する id プロパティを使って、現在の PermissionRequest と対応する DeferredPermissionRequest を関連付けることができます。  

#### パラメーター  

このメソッドにはパラメーターはありません。  

#### 戻り値  

このメソッドに戻り値はありません。  

### 拒否  

権限のリクエストを拒否します。  

#### パラメーター  

このメソッドにはパラメーターはありません。  

#### 戻り値  

このメソッドに戻り値はありません。  

## プロパティ  

### id  

Defer メソッドを使用している場合に、現在の PermissionRequest と対応する DeferredPermissionRequest を関連付けるために使用できる一意の ID。  Defer メソッドを参照してください。  

このプロパティは読み取り専用です。  

##### プロパティ値  

種類:**符号なし長**  

### 州  

"Unknown"、"defer"、"allow"、または "deny" を返して、アクセス許可要求の現在の状態を示します。  状態の文字列は、どのメソッドの許可、拒否、または保留が呼び出されたかに関係なく、直前または "不明" が呼び出された場合に対応します。  

このプロパティは読み取り専用です。  

#### プロパティ値  

種類:**文字列**  

### 型  

要求されるアクセス許可の種類。 これは、次のいずれかの文字列値になります。  

*   **位置**情報: ナビゲータ経由で位置情報にアクセスします。  
*   **unlimitedIndexedDBQuota**: IndexedDB api が、保存されている通常のデータサイズの制限を無視することを許可します。  
*   **メディア**: ナビゲータメディアからのマイクとカメラへのアクセス。  
*   **pointerlock**ロック: 要素の requestPointerLock ロックを使って、マウスポインターのロックと制御を行うことができます。  
*   **webnotifications**: window 経由でデスクトップ通知を表示することができます。知ら.  
*   **画面**: メディアキャプチャ API を使ってスクリーンショットを撮ることができます。  
*   **immersiveview**: VR ディスプレイを制御できます。  

このプロパティは読み取り専用です。  

#### プロパティ値  

種類:**文字列**  

### uri  

アクセス許可を要求するドキュメントの Uniform Resource Identifier (URI)。  

このプロパティは読み取り専用です。  

#### プロパティ値  

種類:**文字列**  
