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
# <span data-ttu-id="d8db0-104">DeferredPermissionRequest オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d8db0-104">DeferredPermissionRequest object</span></span>

<span data-ttu-id="d8db0-105">特殊なデバイス機能 (地理位置情報、ポインターロックなど) にアクセスするために、 [webview](../webview.md)のコンテンツによるエンドユーザーアクセス許可の遅延要求を表します。</span><span class="sxs-lookup"><span data-stu-id="d8db0-105">Represents a deferred request by the content of the [webview](../webview.md) for end-user permission to access specialized device functionality (such as geolocation, or pointer lock).</span></span>

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

## <span data-ttu-id="d8db0-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8db0-106">Methods</span></span>

### <span data-ttu-id="d8db0-107">許可</span><span class="sxs-lookup"><span data-stu-id="d8db0-107">allow</span></span>

<span data-ttu-id="d8db0-108">許可の要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="d8db0-108">Allows the request for permission.</span></span>

```js
deferredPermissionRequest.allow();
```

#### <span data-ttu-id="d8db0-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8db0-109">Parameters</span></span>

<span data-ttu-id="d8db0-110">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="d8db0-110">This method has no parameters.</span></span>

#### <span data-ttu-id="d8db0-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8db0-111">Return value</span></span>

<span data-ttu-id="d8db0-112">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="d8db0-112">This method does not return a value.</span></span>

### <span data-ttu-id="d8db0-113">拒否</span><span class="sxs-lookup"><span data-stu-id="d8db0-113">deny</span></span>

<span data-ttu-id="d8db0-114">権限のリクエストを拒否します。</span><span class="sxs-lookup"><span data-stu-id="d8db0-114">Denies the request for permission.</span></span>

```js
deferredPermissionRequest.deny();
```

#### <span data-ttu-id="d8db0-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8db0-115">Parameters</span></span>

<span data-ttu-id="d8db0-116">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="d8db0-116">This method has no parameters.</span></span>

#### <span data-ttu-id="d8db0-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8db0-117">Return value</span></span>

<span data-ttu-id="d8db0-118">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="d8db0-118">This method does not return a value.</span></span>

## <span data-ttu-id="d8db0-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8db0-119">Properties</span></span>

### <span data-ttu-id="d8db0-120">id</span><span class="sxs-lookup"><span data-stu-id="d8db0-120">id</span></span>

<span data-ttu-id="d8db0-121">以前の MSWebViewPermissionRequested されたイベントの PermissionRequest オブジェクトと現在の DeferredPermissionRequest を関連付けるために使用できる一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d8db0-121">A unique ID that can be used to correlate the current DeferredPermissionRequest with a PermissionRequest object from a previous MSWebViewPermissionRequested event.</span></span> <span data-ttu-id="d8db0-122">**Permissionrequested さ**れた defer メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8db0-122">See the **PermissionRequested.defer** method.</span></span>

<span data-ttu-id="d8db0-123">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="d8db0-123">This property is read-only.</span></span>

```js
var id = deferredPermissionRequest.id;
```

##### <span data-ttu-id="d8db0-124">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="d8db0-124">Property value</span></span>

<span data-ttu-id="d8db0-125">種類:**符号なし長**</span><span class="sxs-lookup"><span data-stu-id="d8db0-125">Type: **Unsigned long**</span></span>

### <span data-ttu-id="d8db0-126">型</span><span class="sxs-lookup"><span data-stu-id="d8db0-126">type</span></span>

<span data-ttu-id="d8db0-127">要求されるアクセス許可の種類。</span><span class="sxs-lookup"><span data-stu-id="d8db0-127">The type of permission being requested.</span></span> <span data-ttu-id="d8db0-128">これは、次のいずれかの文字列値になります。</span><span class="sxs-lookup"><span data-stu-id="d8db0-128">This may be one of the following string values:</span></span>

- <span data-ttu-id="d8db0-129">**位置**情報: ナビゲータ経由で位置情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d8db0-129">**geolocation**: access to location data via navigator.geolocation.</span></span>
- <span data-ttu-id="d8db0-130">**unlimitedIndexedDBQuota**: IndexedDB api が、保存されている通常のデータサイズの制限を無視することを許可します。</span><span class="sxs-lookup"><span data-stu-id="d8db0-130">**unlimitedIndexedDBQuota**: allow IndexedDB APIs to ignore the usual stored data size limit.</span></span>
- <span data-ttu-id="d8db0-131">**メディア**: ナビゲータメディアからのマイクとカメラへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="d8db0-131">**media**: access to the microphone and camera via navigator.getUserMedia.</span></span>
- <span data-ttu-id="d8db0-132">**pointerlock**ロック: 要素の requestPointerLock ロックを使って、マウスポインターのロックと制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d8db0-132">**pointerlock**: ability to lock and control the mouse pointer via Element.requestPointerLock.</span></span>
- <span data-ttu-id="d8db0-133">**webnotifications**: window 経由でデスクトップ通知を表示することができます。知ら.</span><span class="sxs-lookup"><span data-stu-id="d8db0-133">**webnotifications**: ability to show desktop notifications via window.Notification.</span></span>
- <span data-ttu-id="d8db0-134">**画面**: メディアキャプチャ API を使ってスクリーンショットを撮ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8db0-134">**screen**: ability to take screen shots via the Media Capture API.</span></span>
- <span data-ttu-id="d8db0-135">**immersiveview**: VR ディスプレイを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d8db0-135">**immersiveview**: ability to control a VR display.</span></span>

<span data-ttu-id="d8db0-136">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="d8db0-136">This property is read-only.</span></span>

```js
var type = deferredPermissionRequest.type;
```

#### <span data-ttu-id="d8db0-137">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="d8db0-137">Property value</span></span>

<span data-ttu-id="d8db0-138">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="d8db0-138">Type: **String**</span></span>

### <span data-ttu-id="d8db0-139">uri</span><span class="sxs-lookup"><span data-stu-id="d8db0-139">uri</span></span>

<span data-ttu-id="d8db0-140">アクセス許可を要求するドキュメントの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="d8db0-140">The Uniform Resource Identifier (URI) of the document requesting permission.</span></span>

<span data-ttu-id="d8db0-141">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="d8db0-141">This property is read-only.</span></span>

```js
var uri = deferredPermissionRequest.uri;
```

##### <span data-ttu-id="d8db0-142">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="d8db0-142">Property value</span></span>

<span data-ttu-id="d8db0-143">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="d8db0-143">Type: **String**</span></span>

## <span data-ttu-id="d8db0-144">要件</span><span class="sxs-lookup"><span data-stu-id="d8db0-144">Requirements</span></span>

|                                           |                                      |
|-------------------------------------------|--------------------------------------|
| <strong><span data-ttu-id="d8db0-145">サポートされている最小クライアント数</span><span class="sxs-lookup"><span data-stu-id="d8db0-145">Minimum supported client</span></span></strong> | <span data-ttu-id="d8db0-146">Windows 10 [Windows ストアアプリのみ]</span><span class="sxs-lookup"><span data-stu-id="d8db0-146">Windows 10 [Windows Store apps only]</span></span> |
| <strong><span data-ttu-id="d8db0-147">サポートされている最小のサーバー</span><span class="sxs-lookup"><span data-stu-id="d8db0-147">Minimum supported server</span></span></strong> |            <span data-ttu-id="d8db0-148">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="d8db0-148">Not supported</span></span>             |
| <strong><span data-ttu-id="d8db0-149">サポートされている最小電話</span><span class="sxs-lookup"><span data-stu-id="d8db0-149">Minimum supported phone</span></span></strong>  |            <span data-ttu-id="d8db0-150">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="d8db0-150">Not supported</span></span>             |
