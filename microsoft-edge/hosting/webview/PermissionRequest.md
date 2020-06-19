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
# <span data-ttu-id="ec919-104">PermissionRequest オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ec919-104">PermissionRequest object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="ec919-105">権限要求に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec919-105">Provides information about a permission request.</span></span> <span data-ttu-id="ec919-106">このオブジェクトは、 [Mswebviewpermissionrequested さ](../webview.md#mswebviewpermissionrequested)れた webview イベントのイベント引数の permissionrequest プロパティから取得できます。</span><span class="sxs-lookup"><span data-stu-id="ec919-106">This object is available from the permissionRequest property of the event args from the [MSWebViewPermissionRequested](../webview.md#mswebviewpermissionrequested) webview event.</span></span>  

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

## <span data-ttu-id="ec919-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="ec919-107">Methods</span></span>  

### <span data-ttu-id="ec919-108">許可</span><span class="sxs-lookup"><span data-stu-id="ec919-108">allow</span></span>  

<span data-ttu-id="ec919-109">許可の要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="ec919-109">Allows the request for permission.</span></span>  

#### <span data-ttu-id="ec919-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec919-110">Parameters</span></span>  

<span data-ttu-id="ec919-111">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-111">This method has no parameters.</span></span>  

#### <span data-ttu-id="ec919-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ec919-112">Return value</span></span>  

<span data-ttu-id="ec919-113">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-113">This method does not return a value.</span></span>  

### <span data-ttu-id="ec919-114">延期</span><span class="sxs-lookup"><span data-stu-id="ec919-114">defer</span></span>  

<span data-ttu-id="ec919-115">PermissionRequest を同期できるようにするのではなく、ユーザーとのやり取りや、他の非同期操作の実行には、PermissionRequest で defer () を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec919-115">If instead of synchronously allowing or disallowing a PermissionRequest, you require time to interact with the user or take some other asynchronous action, call defer() on the PermissionRequest.</span></span>  <span data-ttu-id="ec919-116">これで、PermissionRequest が getDeferredPermissionRequests と getDeferredPermissionRequestById の DeferredPermissionRequest として利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ec919-116">The PermissionRequest will now be available as a DeferredPermissionRequest from getDeferredPermissionRequests and getDeferredPermissionRequestById.</span></span>  <span data-ttu-id="ec919-117">一致する id プロパティを使って、現在の PermissionRequest と対応する DeferredPermissionRequest を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ec919-117">You can correlate the current PermissionRequest with the corresponding DeferredPermissionRequest via the matching id property.</span></span>  

#### <span data-ttu-id="ec919-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec919-118">Parameters</span></span>  

<span data-ttu-id="ec919-119">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-119">This method has no parameters.</span></span>  

#### <span data-ttu-id="ec919-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="ec919-120">Return value</span></span>  

<span data-ttu-id="ec919-121">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-121">This method does not return a value.</span></span>  

### <span data-ttu-id="ec919-122">拒否</span><span class="sxs-lookup"><span data-stu-id="ec919-122">deny</span></span>  

<span data-ttu-id="ec919-123">権限のリクエストを拒否します。</span><span class="sxs-lookup"><span data-stu-id="ec919-123">Denies the request for permission.</span></span>  

#### <span data-ttu-id="ec919-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec919-124">Parameters</span></span>  

<span data-ttu-id="ec919-125">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-125">This method has no parameters.</span></span>  

#### <span data-ttu-id="ec919-126">戻り値</span><span class="sxs-lookup"><span data-stu-id="ec919-126">Return value</span></span>  

<span data-ttu-id="ec919-127">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="ec919-127">This method does not return a value.</span></span>  

## <span data-ttu-id="ec919-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ec919-128">Properties</span></span>  

### <span data-ttu-id="ec919-129">id</span><span class="sxs-lookup"><span data-stu-id="ec919-129">id</span></span>  

<span data-ttu-id="ec919-130">Defer メソッドを使用している場合に、現在の PermissionRequest と対応する DeferredPermissionRequest を関連付けるために使用できる一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ec919-130">A unique ID that can be used to correlate the current PermissionRequest with a corresponding DeferredPermissionRequest if the defer method is used.</span></span>  <span data-ttu-id="ec919-131">Defer メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec919-131">See the defer method.</span></span>  

<span data-ttu-id="ec919-132">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ec919-132">This property is read-only.</span></span>  

##### <span data-ttu-id="ec919-133">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="ec919-133">Property value</span></span>  

<span data-ttu-id="ec919-134">種類:**符号なし長**</span><span class="sxs-lookup"><span data-stu-id="ec919-134">Type: **Unsigned long**</span></span>  

### <span data-ttu-id="ec919-135">州</span><span class="sxs-lookup"><span data-stu-id="ec919-135">state</span></span>  

<span data-ttu-id="ec919-136">"Unknown"、"defer"、"allow"、または "deny" を返して、アクセス許可要求の現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="ec919-136">Returns "unknown", "defer", "allow", or "deny" to indicate the current state of permission request.</span></span>  <span data-ttu-id="ec919-137">状態の文字列は、どのメソッドの許可、拒否、または保留が呼び出されたかに関係なく、直前または "不明" が呼び出された場合に対応します。</span><span class="sxs-lookup"><span data-stu-id="ec919-137">The state string will correspond to whichever method allow, deny, or defer was called last or "unknown" if none of the methods have been called.</span></span>  

<span data-ttu-id="ec919-138">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ec919-138">This property is read-only.</span></span>  

#### <span data-ttu-id="ec919-139">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="ec919-139">Property value</span></span>  

<span data-ttu-id="ec919-140">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="ec919-140">Type: **String**</span></span>  

### <span data-ttu-id="ec919-141">型</span><span class="sxs-lookup"><span data-stu-id="ec919-141">type</span></span>  

<span data-ttu-id="ec919-142">要求されるアクセス許可の種類。</span><span class="sxs-lookup"><span data-stu-id="ec919-142">The type of permission being requested.</span></span> <span data-ttu-id="ec919-143">これは、次のいずれかの文字列値になります。</span><span class="sxs-lookup"><span data-stu-id="ec919-143">This may be one of the following string values:</span></span>  

*   <span data-ttu-id="ec919-144">**位置**情報: ナビゲータ経由で位置情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ec919-144">**geolocation**: access to location data via navigator.geolocation.</span></span>  
*   <span data-ttu-id="ec919-145">**unlimitedIndexedDBQuota**: IndexedDB api が、保存されている通常のデータサイズの制限を無視することを許可します。</span><span class="sxs-lookup"><span data-stu-id="ec919-145">**unlimitedIndexedDBQuota**: allow IndexedDB APIs to ignore the usual stored data size limit.</span></span>  
*   <span data-ttu-id="ec919-146">**メディア**: ナビゲータメディアからのマイクとカメラへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="ec919-146">**media**: access to the microphone and camera via navigator.getUserMedia.</span></span>  
*   <span data-ttu-id="ec919-147">**pointerlock**ロック: 要素の requestPointerLock ロックを使って、マウスポインターのロックと制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ec919-147">**pointerlock**: ability to lock and control the mouse pointer via Element.requestPointerLock.</span></span>  
*   <span data-ttu-id="ec919-148">**webnotifications**: window 経由でデスクトップ通知を表示することができます。知ら.</span><span class="sxs-lookup"><span data-stu-id="ec919-148">**webnotifications**: ability to show desktop notifications via window.Notification.</span></span>  
*   <span data-ttu-id="ec919-149">**画面**: メディアキャプチャ API を使ってスクリーンショットを撮ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec919-149">**screen**: ability to take screen shots via the Media Capture API.</span></span>  
*   <span data-ttu-id="ec919-150">**immersiveview**: VR ディスプレイを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ec919-150">**immersiveview**: ability to control a VR display.</span></span>  

<span data-ttu-id="ec919-151">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ec919-151">This property is read-only.</span></span>  

#### <span data-ttu-id="ec919-152">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="ec919-152">Property value</span></span>  

<span data-ttu-id="ec919-153">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="ec919-153">Type: **String**</span></span>  

### <span data-ttu-id="ec919-154">uri</span><span class="sxs-lookup"><span data-stu-id="ec919-154">uri</span></span>  

<span data-ttu-id="ec919-155">アクセス許可を要求するドキュメントの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="ec919-155">The Uniform Resource Identifier (URI) of the document requesting permission.</span></span>  

<span data-ttu-id="ec919-156">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ec919-156">This property is read-only.</span></span>  

#### <span data-ttu-id="ec919-157">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="ec919-157">Property value</span></span>  

<span data-ttu-id="ec919-158">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="ec919-158">Type: **String**</span></span>  
