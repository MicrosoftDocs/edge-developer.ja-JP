---
description: 操作が正常に完了したか失敗したかを公開します
title: MSWebViewAsyncOperation オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: d6e03af2a0205938f19120076aa0ad622539d7e5
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752126"
---
# <span data-ttu-id="3f94e-104">MSWebViewAsyncOperation オブジェクト</span><span class="sxs-lookup"><span data-stu-id="3f94e-104">MSWebViewAsyncOperation object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="3f94e-105">操作が正常に完了したか失敗したかを公開します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-105">Exposes whether the operation completed successfully or failed.</span></span>  

## <span data-ttu-id="3f94e-106">イベント</span><span class="sxs-lookup"><span data-stu-id="3f94e-106">Events</span></span>  

### <span data-ttu-id="3f94e-107">完了</span><span class="sxs-lookup"><span data-stu-id="3f94e-107">complete</span></span>  

<span data-ttu-id="3f94e-108">操作が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-108">Indicates that the operation completed.</span></span>  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```  

#### <span data-ttu-id="3f94e-109">イベント情報</span><span class="sxs-lookup"><span data-stu-id="3f94e-109">Event Information</span></span>  

|  |  |  
|:--- |:--- |  
| **<span data-ttu-id="3f94e-110">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f94e-110">Interface</span></span>** | **<span data-ttu-id="3f94e-111">イベント</span><span class="sxs-lookup"><span data-stu-id="3f94e-111">Event</span></span>** |  
| **<span data-ttu-id="3f94e-112">同期</span><span class="sxs-lookup"><span data-stu-id="3f94e-112">Synchronous</span></span>** |<span data-ttu-id="3f94e-113">はい</span><span class="sxs-lookup"><span data-stu-id="3f94e-113">Yes</span></span> |  
| **<span data-ttu-id="3f94e-114">バブル</span><span class="sxs-lookup"><span data-stu-id="3f94e-114">Bubbles</span></span>** |<span data-ttu-id="3f94e-115">なし</span><span class="sxs-lookup"><span data-stu-id="3f94e-115">No</span></span> |   
| **<span data-ttu-id="3f94e-116">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="3f94e-116">Cancelable</span></span>** |<span data-ttu-id="3f94e-117">なし</span><span class="sxs-lookup"><span data-stu-id="3f94e-117">No</span></span> |  

### <span data-ttu-id="3f94e-118">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="3f94e-118">error</span></span>  

<span data-ttu-id="3f94e-119">操作でエラーがあったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-119">Indicates that there was an error with the operation.</span></span>  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```  

#### <span data-ttu-id="3f94e-120">イベント情報</span><span class="sxs-lookup"><span data-stu-id="3f94e-120">Event Information</span></span>  

|  |  |  
|:--- |:--- |  
| **<span data-ttu-id="3f94e-121">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f94e-121">Interface</span></span>** | **<span data-ttu-id="3f94e-122">イベント</span><span class="sxs-lookup"><span data-stu-id="3f94e-122">Event</span></span>** |  
| **<span data-ttu-id="3f94e-123">同期</span><span class="sxs-lookup"><span data-stu-id="3f94e-123">Synchronous</span></span>** | <span data-ttu-id="3f94e-124">はい</span><span class="sxs-lookup"><span data-stu-id="3f94e-124">Yes</span></span> |  
| **<span data-ttu-id="3f94e-125">バブル</span><span class="sxs-lookup"><span data-stu-id="3f94e-125">Bubbles</span></span>** | <span data-ttu-id="3f94e-126">なし</span><span class="sxs-lookup"><span data-stu-id="3f94e-126">No</span></span> |  
| **<span data-ttu-id="3f94e-127">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="3f94e-127">Cancelable</span></span>** | <span data-ttu-id="3f94e-128">なし</span><span class="sxs-lookup"><span data-stu-id="3f94e-128">No</span></span> |  

## <span data-ttu-id="3f94e-129">メソッド</span><span class="sxs-lookup"><span data-stu-id="3f94e-129">Methods</span></span>  

### <span data-ttu-id="3f94e-130">start</span><span class="sxs-lookup"><span data-stu-id="3f94e-130">start</span></span>  

<span data-ttu-id="3f94e-131">非同期タスクを開始するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3f94e-131">Called to start the async task.</span></span>  

```javascript
MSWebViewAsyncOperation.start();
```  

### <span data-ttu-id="3f94e-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f94e-132">Parameters</span></span>  

<span data-ttu-id="3f94e-133">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="3f94e-133">This method does not have parameters.</span></span>  

### <span data-ttu-id="3f94e-134">戻り値</span><span class="sxs-lookup"><span data-stu-id="3f94e-134">Return value</span></span>  

<span data-ttu-id="3f94e-135">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="3f94e-135">This method does not return a value.</span></span>  

## <span data-ttu-id="3f94e-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f94e-136">Properties</span></span>  

### <span data-ttu-id="3f94e-137">error (エラー)</span><span class="sxs-lookup"><span data-stu-id="3f94e-137">error</span></span>  

<span data-ttu-id="3f94e-138">発生したエラー。</span><span class="sxs-lookup"><span data-stu-id="3f94e-138">The error that occurred.</span></span>  

<span data-ttu-id="3f94e-139">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-139">This property is read-only.</span></span>  

```javascript
var error = MSWebViewAsyncOperation.error;
```  

#### <span data-ttu-id="3f94e-140">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-140">Property value</span></span>  

<span data-ttu-id="3f94e-141">種類: **Domerror**</span><span class="sxs-lookup"><span data-stu-id="3f94e-141">Type: **DOMError**</span></span>  

### <span data-ttu-id="3f94e-142">oncomplete</span><span class="sxs-lookup"><span data-stu-id="3f94e-142">oncomplete</span></span>  

<span data-ttu-id="3f94e-143">**Complete**イベントハンドラー。</span><span class="sxs-lookup"><span data-stu-id="3f94e-143">The **complete** event handler.</span></span>  

```javascript
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```  

#### <span data-ttu-id="3f94e-144">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-144">Property value</span></span>  

<span data-ttu-id="3f94e-145">種類: **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="3f94e-145">Type: **EventHandler**</span></span>  

### <span data-ttu-id="3f94e-146">時</span><span class="sxs-lookup"><span data-stu-id="3f94e-146">onerror</span></span>  

<span data-ttu-id="3f94e-147">**エラー**イベントハンドラー。</span><span class="sxs-lookup"><span data-stu-id="3f94e-147">The **error** event handler.</span></span>  

```javascript
var onerror = MSWebViewAsyncOperation.onerror;
```  

#### <span data-ttu-id="3f94e-148">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-148">Property value</span></span>  

<span data-ttu-id="3f94e-149">種類: **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="3f94e-149">Type: **EventHandler**</span></span>  

### <span data-ttu-id="3f94e-150">readyState</span><span class="sxs-lookup"><span data-stu-id="3f94e-150">readyState</span></span>  

<span data-ttu-id="3f94e-151">オブジェクトのレディ状態を記述します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-151">Describes the ready state of the object.</span></span>  

<span data-ttu-id="3f94e-152">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-152">This property is read-only.</span></span>  

```javascript
var readyState = MSWebViewAsyncOperation.readyState;
```  

#### <span data-ttu-id="3f94e-153">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-153">Property value</span></span>  

<span data-ttu-id="3f94e-154">種類:**符号なし短い**</span><span class="sxs-lookup"><span data-stu-id="3f94e-154">Type: **unsigned short**</span></span>  

### <span data-ttu-id="3f94e-155">より</span><span class="sxs-lookup"><span data-stu-id="3f94e-155">result</span></span>  

<span data-ttu-id="3f94e-156">操作の結果。</span><span class="sxs-lookup"><span data-stu-id="3f94e-156">The result of the operation.</span></span>  

<span data-ttu-id="3f94e-157">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-157">This property is read-only.</span></span>  

```javascript
var result = MSWebViewAsyncOperation.result;
```  

#### <span data-ttu-id="3f94e-158">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-158">Property value</span></span>  

<span data-ttu-id="3f94e-159">種類: any</span><span class="sxs-lookup"><span data-stu-id="3f94e-159">Type: any</span></span>  

### <span data-ttu-id="3f94e-160">ターゲット</span><span class="sxs-lookup"><span data-stu-id="3f94e-160">target</span></span>  

<span data-ttu-id="3f94e-161">操作のターゲット。</span><span class="sxs-lookup"><span data-stu-id="3f94e-161">The target of the operation.</span></span>  

<span data-ttu-id="3f94e-162">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-162">This property is read-only.</span></span>  

```javascript
var target = MSWebViewAsyncOperation.target;
```  

#### <span data-ttu-id="3f94e-163">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-163">Property value</span></span>  

<span data-ttu-id="3f94e-164">Type: [ **MSHTMLWebViewElement**](../webview.md)</span><span class="sxs-lookup"><span data-stu-id="3f94e-164">Type: [**MSHTMLWebViewElement**](../webview.md)</span></span>  

### <span data-ttu-id="3f94e-165">型</span><span class="sxs-lookup"><span data-stu-id="3f94e-165">type</span></span>  

<span data-ttu-id="3f94e-166">操作の型。</span><span class="sxs-lookup"><span data-stu-id="3f94e-166">The type of the operation.</span></span>  

<span data-ttu-id="3f94e-167">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-167">This property is read-only.</span></span>  

```javascript
var type = MSWebViewAsyncOperation.type;
```  

#### <span data-ttu-id="3f94e-168">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="3f94e-168">Property value</span></span>  

<span data-ttu-id="3f94e-169">種類:**符号なし短い**</span><span class="sxs-lookup"><span data-stu-id="3f94e-169">Type: **unsigned short**</span></span>  
