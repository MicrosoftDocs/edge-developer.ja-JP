---
description: 操作が正常に完了したか失敗したかを公開します
title: MSWebViewAsyncOperation オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: ebb89c0fc645ebcd97357af10af2be650d8218b9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569237"
---
# <span data-ttu-id="db752-104">MSWebViewAsyncOperation オブジェクト</span><span class="sxs-lookup"><span data-stu-id="db752-104">MSWebViewAsyncOperation object</span></span>

<span data-ttu-id="db752-105">操作が正常に完了したか失敗したかを公開します。</span><span class="sxs-lookup"><span data-stu-id="db752-105">Exposes whether the operation completed successfully or failed.</span></span> 

## <span data-ttu-id="db752-106">イベント</span><span class="sxs-lookup"><span data-stu-id="db752-106">Events</span></span>

### <span data-ttu-id="db752-107">完了</span><span class="sxs-lookup"><span data-stu-id="db752-107">complete</span></span>

<span data-ttu-id="db752-108">操作が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="db752-108">Indicates that the operation completed.</span></span> 

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```

#### <span data-ttu-id="db752-109">イベント情報</span><span class="sxs-lookup"><span data-stu-id="db752-109">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="db752-110">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db752-110">Interface</span></span>** | **<span data-ttu-id="db752-111">イベント</span><span class="sxs-lookup"><span data-stu-id="db752-111">Event</span></span>**
|**<span data-ttu-id="db752-112">同期</span><span class="sxs-lookup"><span data-stu-id="db752-112">Synchronous</span></span>** |<span data-ttu-id="db752-113">はい</span><span class="sxs-lookup"><span data-stu-id="db752-113">Yes</span></span> |    
|**<span data-ttu-id="db752-114">バブル</span><span class="sxs-lookup"><span data-stu-id="db752-114">Bubbles</span></span>**     |<span data-ttu-id="db752-115">なし</span><span class="sxs-lookup"><span data-stu-id="db752-115">No</span></span> |   
|**<span data-ttu-id="db752-116">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="db752-116">Cancelable</span></span>**  |<span data-ttu-id="db752-117">なし</span><span class="sxs-lookup"><span data-stu-id="db752-117">No</span></span> |        


### <span data-ttu-id="db752-118">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="db752-118">error</span></span>

<span data-ttu-id="db752-119">操作でエラーがあったことを示します。</span><span class="sxs-lookup"><span data-stu-id="db752-119">Indicates that there was an error with the operation.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```

#### <span data-ttu-id="db752-120">イベント情報</span><span class="sxs-lookup"><span data-stu-id="db752-120">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="db752-121">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db752-121">Interface</span></span>** | **<span data-ttu-id="db752-122">イベント</span><span class="sxs-lookup"><span data-stu-id="db752-122">Event</span></span>**
|**<span data-ttu-id="db752-123">同期</span><span class="sxs-lookup"><span data-stu-id="db752-123">Synchronous</span></span>** |<span data-ttu-id="db752-124">はい</span><span class="sxs-lookup"><span data-stu-id="db752-124">Yes</span></span> |    
|**<span data-ttu-id="db752-125">バブル</span><span class="sxs-lookup"><span data-stu-id="db752-125">Bubbles</span></span>**     |<span data-ttu-id="db752-126">なし</span><span class="sxs-lookup"><span data-stu-id="db752-126">No</span></span> |   
|**<span data-ttu-id="db752-127">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="db752-127">Cancelable</span></span>**  |<span data-ttu-id="db752-128">なし</span><span class="sxs-lookup"><span data-stu-id="db752-128">No</span></span> |            


## <span data-ttu-id="db752-129">メソッド</span><span class="sxs-lookup"><span data-stu-id="db752-129">Methods</span></span>

### <span data-ttu-id="db752-130">start</span><span class="sxs-lookup"><span data-stu-id="db752-130">start</span></span>

<span data-ttu-id="db752-131">非同期タスクを開始するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="db752-131">Called to start the async task.</span></span> 

```js
MSWebViewAsyncOperation.start();
```

### <span data-ttu-id="db752-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db752-132">Parameters</span></span>

<span data-ttu-id="db752-133">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="db752-133">This method does not have parameters.</span></span>

### <span data-ttu-id="db752-134">戻り値</span><span class="sxs-lookup"><span data-stu-id="db752-134">Return value</span></span>

<span data-ttu-id="db752-135">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="db752-135">This method does not return a value.</span></span>

## <span data-ttu-id="db752-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="db752-136">Properties</span></span>

### <span data-ttu-id="db752-137">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="db752-137">error</span></span>

<span data-ttu-id="db752-138">発生したエラー。</span><span class="sxs-lookup"><span data-stu-id="db752-138">The error that occured.</span></span>

<span data-ttu-id="db752-139">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="db752-139">This property is read-only.</span></span>

```js
var error = MSWebViewAsyncOperation.error;
```

#### <span data-ttu-id="db752-140">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-140">Property value</span></span>
<span data-ttu-id="db752-141">種類: **Domerror**</span><span class="sxs-lookup"><span data-stu-id="db752-141">Type: **DOMError**</span></span>

### <span data-ttu-id="db752-142">oncomplete</span><span class="sxs-lookup"><span data-stu-id="db752-142">oncomplete</span></span>

<span data-ttu-id="db752-143">**Complete**イベントハンドラー。</span><span class="sxs-lookup"><span data-stu-id="db752-143">The **complete** event handler.</span></span> 

```js
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```

#### <span data-ttu-id="db752-144">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-144">Property value</span></span>
<span data-ttu-id="db752-145">種類: **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="db752-145">Type: **EventHandler**</span></span>

### <span data-ttu-id="db752-146">時</span><span class="sxs-lookup"><span data-stu-id="db752-146">onerror</span></span>

<span data-ttu-id="db752-147">**エラー**イベントハンドラー。</span><span class="sxs-lookup"><span data-stu-id="db752-147">The **error** event handler.</span></span> 

```js
var onerror = MSWebViewAsyncOperation.onerror;
```

#### <span data-ttu-id="db752-148">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-148">Property value</span></span>
<span data-ttu-id="db752-149">種類: **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="db752-149">Type: **EventHandler**</span></span>

### <span data-ttu-id="db752-150">readyState</span><span class="sxs-lookup"><span data-stu-id="db752-150">readyState</span></span>

<span data-ttu-id="db752-151">オブジェクトのレディ状態を記述します。</span><span class="sxs-lookup"><span data-stu-id="db752-151">Describes the ready state of the object.</span></span>

<span data-ttu-id="db752-152">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="db752-152">This property is read-only.</span></span>

```js
var readyState = MSWebViewAsyncOperation.readyState;
```

#### <span data-ttu-id="db752-153">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-153">Property value</span></span>
<span data-ttu-id="db752-154">種類:**符号なし短い**</span><span class="sxs-lookup"><span data-stu-id="db752-154">Type: **unsigned short**</span></span>

### <span data-ttu-id="db752-155">より</span><span class="sxs-lookup"><span data-stu-id="db752-155">result</span></span>

<span data-ttu-id="db752-156">操作の結果。</span><span class="sxs-lookup"><span data-stu-id="db752-156">The result of the operation.</span></span>

<span data-ttu-id="db752-157">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="db752-157">This property is read-only.</span></span>

```js
var result = MSWebViewAsyncOperation.result;
```

#### <span data-ttu-id="db752-158">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-158">Property value</span></span>
<span data-ttu-id="db752-159">種類: any</span><span class="sxs-lookup"><span data-stu-id="db752-159">Type: any</span></span>

### <span data-ttu-id="db752-160">ターゲット</span><span class="sxs-lookup"><span data-stu-id="db752-160">target</span></span>

<span data-ttu-id="db752-161">操作のターゲット。</span><span class="sxs-lookup"><span data-stu-id="db752-161">The target of the operation.</span></span> 

<span data-ttu-id="db752-162">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="db752-162">This property is read-only.</span></span>

```js
var target = MSWebViewAsyncOperation.target;
```

#### <span data-ttu-id="db752-163">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-163">Property value</span></span>
<span data-ttu-id="db752-164">Type: [ **MSHTMLWebViewElement**](../webview.md)</span><span class="sxs-lookup"><span data-stu-id="db752-164">Type: [**MSHTMLWebViewElement**](../webview.md)</span></span>

### <span data-ttu-id="db752-165">型</span><span class="sxs-lookup"><span data-stu-id="db752-165">type</span></span>

<span data-ttu-id="db752-166">操作の型。</span><span class="sxs-lookup"><span data-stu-id="db752-166">The type of the operation.</span></span>

<span data-ttu-id="db752-167">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="db752-167">This property is read-only.</span></span>

```js
var type = MSWebViewAsyncOperation.type;
```

#### <span data-ttu-id="db752-168">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="db752-168">Property value</span></span>
<span data-ttu-id="db752-169">種類:**符号なし短い**</span><span class="sxs-lookup"><span data-stu-id="db752-169">Type: **unsigned short**</span></span>
