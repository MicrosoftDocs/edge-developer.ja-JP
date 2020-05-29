---
title: MSApp API リファレンス
description: Blob と MSStream オブジェクトの作成を可能にするヘルパー関数を提供します。 MSApp オブジェクトとメンバーは、JavaScript を使った Windows アプリでサポートされています。
author: mattwojo
ms.author: mattwoj
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp、PWA、ファイルアップロード、ブログ、Msapp、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 0ed8cefa918bd44f3b2c4e8312d2c1d3b4ace8fc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570787"
---
# <span data-ttu-id="26e81-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="26e81-105">MSApp</span></span>

<span data-ttu-id="26e81-106">MSApp オブジェクトとそのメンバーは、JavaScript を使った Windows アプリでのみサポートされます (PWAs を含む Windows API 機能へのアクセスなど)。</span><span class="sxs-lookup"><span data-stu-id="26e81-106">The MSApp object and its members are supported only for Windows apps using JavaScript (including PWAs accessing Windows API features).</span></span> <span data-ttu-id="26e81-107">MSApp オブジェクトは、ms appx URI スキームを使って読み込まれた Windows アプリの HTML ドキュメントのローカルコンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (そのため、そのメソッドとプロパティはありません)。</span><span class="sxs-lookup"><span data-stu-id="26e81-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>

<span data-ttu-id="26e81-108">[Blob](https://developer.mozilla.org/docs/Web/API/Blob)と[msstream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)オブジェクトを作成するためのヘルパー関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="26e81-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>

```javascript
var result = MSApp.method;
```

| | |
| :--- | :--- |
| [**<span data-ttu-id="26e81-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="26e81-109">Methods</span></span>**](#msapp-methods) | <span data-ttu-id="26e81-110">[Cleartemporarywebdataasync](#cleartemporarywebdataasync)、 [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)、 [createDataPackage](#createdatapackage)、 [createDataPackageFromSelection](#createdatapackagefromselection)、 [createFileFromStorageFile](#createfilefromstoragefile)、 [createstreamfrominputstream](#createstreamfrominputstream)、 [execAsyncAtPriority](#execasyncatpriority)、 [execatpriority](#execatpriority)、 [getcurrentpriority](#getcurrentpriority)、 [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)、[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)、 [getViewId](#getviewid)、 [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher)、 [pagehandlesallapplicationactivations アクティブ](#pagehandlesallapplicationactivations)化、 [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts)、 [terminateApp](#terminateapp)。</span><span class="sxs-lookup"><span data-stu-id="26e81-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span> |

| | |
| :--- | :--- |
| [**<span data-ttu-id="26e81-111">定数</span><span class="sxs-lookup"><span data-stu-id="26e81-111">Constants</span></span>**](#msapp-constants) | <span data-ttu-id="26e81-112">[current](#current)、 [high](#high)、 [idle](#idle)、 [normal](#normal)。</span><span class="sxs-lookup"><span data-stu-id="26e81-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>|

| | |
| :--- | :--- |
| [<span data-ttu-id="26e81-113">**MSAppAsyncOperation**インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26e81-113">**MSAppAsyncOperation** interface</span></span>](#msappasyncoperation) | [<span data-ttu-id="26e81-114">start</span><span class="sxs-lookup"><span data-stu-id="26e81-114">start</span></span>](#start) |

## <span data-ttu-id="26e81-115">MSApp のメソッド</span><span class="sxs-lookup"><span data-stu-id="26e81-115">MSApp Methods</span></span>

### <span data-ttu-id="26e81-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="26e81-116">clearTemporaryWebDataAsync</span></span> 
<span data-ttu-id="26e81-117">アプリまたは[WebView](../../webview.md)のキャッシュと indexedDB データをクリアします。</span><span class="sxs-lookup"><span data-stu-id="26e81-117">Clears cache and indexedDB data for the app or [WebView](../../webview.md).</span></span>

```javascript
var retval = MSApp.clearTemporaryWebDataAsync(#); 
```

#### <span data-ttu-id="26e81-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-118">Parameters</span></span>
<span data-ttu-id="26e81-119">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-119">This method has no parameters.</span></span>

#### <span data-ttu-id="26e81-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-120">Return value</span></span>
<span data-ttu-id="26e81-121">種類[`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="26e81-121">Type: [`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)</span></span>

<span data-ttu-id="26e81-122">非同期操作を表します。</span><span class="sxs-lookup"><span data-stu-id="26e81-122">Represents an asynchronous action.</span></span>

### <span data-ttu-id="26e81-123">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="26e81-123">createBlobFromRandomAccessStream</span></span>
<span data-ttu-id="26e81-124">オブジェクトから[Blob](https://developer.mozilla.org/docs/Web/API/Blob)を作成 [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) します。</span><span class="sxs-lookup"><span data-stu-id="26e81-124">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span> <span data-ttu-id="26e81-125">このメソッドは、アプリ内のオブジェクトを処理するときに使用 `IRandomAccessStream` し、ストリームから W3C ベースのオブジェクトを作成するために使います。</span><span class="sxs-lookup"><span data-stu-id="26e81-125">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span> <span data-ttu-id="26e81-126">Blob を作成したら、 [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader)、 [URL api](https://developer.mozilla.org/docs/Web/API/URL)、 [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)と共に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="26e81-126">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span> 

```javascript
var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
```

#### <span data-ttu-id="26e81-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-127">Parameters</span></span>

`type` <span data-ttu-id="26e81-128">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-128">[in]</span></span>

|<span data-ttu-id="26e81-129">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-129">Type</span></span> | <span data-ttu-id="26e81-130">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-130">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-131">String</span><span class="sxs-lookup"><span data-stu-id="26e81-131">String</span></span> | <span data-ttu-id="26e81-132">データのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="26e81-132">Content type of the data.</span></span> <span data-ttu-id="26e81-133">この文字列は、RFC 2616 のセクション3.7 で定義されているメディアタイプトークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="26e81-133">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>

`stream` <span data-ttu-id="26e81-134">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-134">[in]</span></span>

|<span data-ttu-id="26e81-135">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-135">Type</span></span> | <span data-ttu-id="26e81-136">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-136">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-137">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-137">Any</span></span> | <span data-ttu-id="26e81-138">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)が Blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-138">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>

#### <span data-ttu-id="26e81-139">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-139">Return value</span></span>
|<span data-ttu-id="26e81-140">型</span><span class="sxs-lookup"><span data-stu-id="26e81-140">Type</span></span> | <span data-ttu-id="26e81-141">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-141">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-142">ラージ</span><span class="sxs-lookup"><span data-stu-id="26e81-142">Blob</span></span> | <span data-ttu-id="26e81-143">ストリームを含む新しい blob オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="26e81-143">New blob object that contains the stream.</span></span>

#### <span data-ttu-id="26e81-144">例外</span><span class="sxs-lookup"><span data-stu-id="26e81-144">Exceptions</span></span>
|<span data-ttu-id="26e81-145">エラー</span><span class="sxs-lookup"><span data-stu-id="26e81-145">Exception</span></span> | <span data-ttu-id="26e81-146">状況</span><span class="sxs-lookup"><span data-stu-id="26e81-146">Condition</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-147">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="26e81-147">TypeMismatchError</span></span> | <span data-ttu-id="26e81-148">ノードの型は、予期されるパラメーターの型と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-148">The node type is incompatible with the expected parameter type.</span></span> <span data-ttu-id="26e81-149">Internet Explorer 10 より前のバージョンの場合は、TYPE_MISMATCH_ERR が返されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-149">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>

#### <span data-ttu-id="26e81-150">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-150">Remarks</span></span>
<span data-ttu-id="26e81-151">Window オブジェクトの MSApp 名前空間を使って、Windows ランタイム型から Blob を作成します。</span><span class="sxs-lookup"><span data-stu-id="26e81-151">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span> <span data-ttu-id="26e81-152">このメソッドは、実質的には、指定されたオブジェクトに対するライトラッパーである blob を作成 [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) します。</span><span class="sxs-lookup"><span data-stu-id="26e81-152">This method will create a blob that is essentially a light wrapper over the [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span> <span data-ttu-id="26e81-153">Blob はこのストリームの有効期間を所有しており、blob が破棄されるとストリームは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="26e81-153">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span> 

#### <span data-ttu-id="26e81-154">例</span><span class="sxs-lookup"><span data-stu-id="26e81-154">Example</span></span>

```javascript
var randomAccessStream = dataPackage.GetData("image/bmp");
var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});

document.getElementById("imagetag").src = url; 
```

### <span data-ttu-id="26e81-155">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="26e81-155">createDataPackage</span></span>
<span data-ttu-id="26e81-156">ユーザーまたはアプリケーションが指定した範囲を、共有可能な HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="26e81-156">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>

```javascript
var retVal = MSApp.createDataPackage(object); 
```

#### <span data-ttu-id="26e81-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-157">Parameters</span></span>
`object` <span data-ttu-id="26e81-158">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-158">[in]</span></span>

|<span data-ttu-id="26e81-159">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-159">Type</span></span> | <span data-ttu-id="26e81-160">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-160">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-161">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-161">Any</span></span> | <span data-ttu-id="26e81-162">この範囲は、選択オブジェクトから、または手動で作成することができ `window.selection.getRangeAt(0)` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-162">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>

#### <span data-ttu-id="26e81-163">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-163">Return value</span></span>
|<span data-ttu-id="26e81-164">型</span><span class="sxs-lookup"><span data-stu-id="26e81-164">Type</span></span> | <span data-ttu-id="26e81-165">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-165">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-166">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-166">Any</span></span> | <span data-ttu-id="26e81-167">指定した範囲の HTML マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26e81-167">Contains the HTML markup for the specified range.</span></span>

#### <span data-ttu-id="26e81-168">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-168">Remarks</span></span>
<span data-ttu-id="26e81-169">このメソッドは、 [TextRange](/uwp/api/windows.ui.xaml.documents.textrange)ではなく、[ドキュメントオブジェクトモデル (DOM) 範囲](https://developer.mozilla.org/docs/Web/API/Range)のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="26e81-169">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span> <span data-ttu-id="26e81-170">指定した範囲の返されるデータパッケージには、クリップボード形式の HTML マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26e81-170">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>

<span data-ttu-id="26e81-171">返されるデータパッケージに使用できるプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-171">There are no available properties for the returned data package.</span></span>

### <span data-ttu-id="26e81-172">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="26e81-172">createDataPackageFromSelection</span></span> 
<span data-ttu-id="26e81-173">ユーザーまたはアプリケーションの選択範囲を、共有可能な HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="26e81-173">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>

```javascript
var retVal = MSApp.createDataPackageFromSelection(); 
```

#### <span data-ttu-id="26e81-174">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-174">Parameters</span></span>
<span data-ttu-id="26e81-175">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-175">This method has no parameters.</span></span>

#### <span data-ttu-id="26e81-176">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-176">Return value</span></span>
|<span data-ttu-id="26e81-177">型</span><span class="sxs-lookup"><span data-stu-id="26e81-177">Type</span></span> | <span data-ttu-id="26e81-178">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-178">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-179">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-179">Any</span></span> | <span data-ttu-id="26e81-180">指定した範囲の HTML マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26e81-180">Contains the HTML markup for the specified range.</span></span>

#### <span data-ttu-id="26e81-181">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-181">Remarks</span></span>
<span data-ttu-id="26e81-182">選択されたデータパッケージには、クリップボード形式の HTML マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26e81-182">The returned data package for the selection contains HTML markup in clipboard format.</span></span> <span data-ttu-id="26e81-183">アプリケーションの UI 内の任意の場所でユーザーが選択されていない場合、は `createDataPackageFromSelection` null を返します。</span><span class="sxs-lookup"><span data-stu-id="26e81-183">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns null.</span></span>

<span data-ttu-id="26e81-184">返されるデータパッケージに使用できるプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-184">There are no available properties for the returned data package.</span></span>
 
### <span data-ttu-id="26e81-185">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="26e81-185">createFileFromStorageFile</span></span> 
<span data-ttu-id="26e81-186">WinRT を[WinRT](/uwp/api/) [`StorageFile`](/uwp/api/windows.storage.storagefile) 標準の W3C オブジェクトに変換 [`File`](https://developer.mozilla.org/docs/Web/API/File) します。</span><span class="sxs-lookup"><span data-stu-id="26e81-186">Converts a [WinRT](/uwp/api/) [`StorageFile`](/uwp/api/windows.storage.storagefile) to a standard W3C [`File`](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>

```javascript
var retVal = MSApp.createFileFromStorageFile(storageFile); 
```

#### <span data-ttu-id="26e81-187">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-187">Parameters</span></span>
`storageFile` <span data-ttu-id="26e81-188">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-188">[in]</span></span>

|<span data-ttu-id="26e81-189">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-189">Type</span></span> | <span data-ttu-id="26e81-190">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-190">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-191">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-191">Any</span></span> | <span data-ttu-id="26e81-192">ストレージファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-192">Contains the storage file.</span></span>

#### <span data-ttu-id="26e81-193">例外</span><span class="sxs-lookup"><span data-stu-id="26e81-193">Exceptions</span></span>
|<span data-ttu-id="26e81-194">エラー</span><span class="sxs-lookup"><span data-stu-id="26e81-194">Exception</span></span> | <span data-ttu-id="26e81-195">状況</span><span class="sxs-lookup"><span data-stu-id="26e81-195">Condition</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-196">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="26e81-196">TypeMismatchError</span></span> | <span data-ttu-id="26e81-197">指定された W3C ファイル参照は無効です。</span><span class="sxs-lookup"><span data-stu-id="26e81-197">The specified W3C file reference is invalid.</span></span> <span data-ttu-id="26e81-198">Internet Explorer 10 より前のバージョンの場合は、TYPE_MISMATCH_ERR が返されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-198">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>

### <span data-ttu-id="26e81-199">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="26e81-199">createStreamFromInputStream</span></span>  

<span data-ttu-id="26e81-200">からを作成 [`MSStream`](https://msdn.microsoft.com/library/hh772328) [`InputStream`](https://msdn.microsoft.com/library/hh772327) します。</span><span class="sxs-lookup"><span data-stu-id="26e81-200">Creates an [`MSStream`](https://msdn.microsoft.com/library/hh772328) from an [`InputStream`](https://msdn.microsoft.com/library/hh772327).</span></span>  


```javascript
var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
```

#### <span data-ttu-id="26e81-201">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-201">Parameters</span></span>
`type` <span data-ttu-id="26e81-202">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-202">[in]</span></span>

|<span data-ttu-id="26e81-203">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-203">Type</span></span> | <span data-ttu-id="26e81-204">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-204">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-205">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-205">DOMString</span></span> | <span data-ttu-id="26e81-206">データのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="26e81-206">Content type of the data.</span></span> <span data-ttu-id="26e81-207">この文字列は、RFC 2616 のセクション3.7 で定義されているメディアタイプトークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="26e81-207">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span> <span data-ttu-id="26e81-208">([「MIME の種類、](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types) ie、テキスト/プレーン、テキスト/html、画像/jpeg、画像/ogg、音声/mpeg、オーディオ/ビデオ、音声/ビデオ、音声/、audio/\*、video/mp4 など)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-208">([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types) ie. text/plain, text/html, image/jpeg, image/png, audio/mpeg, audio/ogg, audio/\*, video/mp4, etc.).</span></span> 

`inputStream` <span data-ttu-id="26e81-209">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-209">[in]</span></span>

|<span data-ttu-id="26e81-210">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-210">Type</span></span> | <span data-ttu-id="26e81-211">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-211">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-212">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-212">Any</span></span> | <span data-ttu-id="26e81-213">は [`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream) 、に保存され `MSStream` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-213">The [`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>

#### <span data-ttu-id="26e81-214">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-214">Remarks</span></span>
<span data-ttu-id="26e81-215">このメソッドは、コンテンツの種類と参照を受け取り `IInputStream` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-215">This method takes a content-type, and the `IInputStream` reference.</span></span> <span data-ttu-id="26e81-216">次に、メソッドは、渡された stream 参照が型のインスタンスであり、存在しない場合は、スローされたことを確認し `IInputStream` `DOMException TYPE_MISMATCH_ERR` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-216">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span> <span data-ttu-id="26e81-217">エラーが発生しない場合は、 `createStreamFromInputStream` `MSStream` (入力から) を作成します。</span><span class="sxs-lookup"><span data-stu-id="26e81-217">If no error occurs, `createStreamFromInputStream` creates an `MSStream` (from its inputs).</span></span>

#### <span data-ttu-id="26e81-218">例</span><span class="sxs-lookup"><span data-stu-id="26e81-218">Example</span></span>
<span data-ttu-id="26e81-219">を `IInputStream` 使用してを作成でき `MSStream` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-219">An `IInputStream` can be used to create an `MSStream`.</span></span> <span data-ttu-id="26e81-220">`MSStreams`本来は1回限りのオブジェクトであるため、で作成されたすべての url は、 `URL.createObjectURL` イメージ要素によって最初に解決された時点で失効されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-220">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span> <span data-ttu-id="26e81-221">さらに、ストリームを使用した後、このオブジェクトの2番目の URL への要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="26e81-221">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>

```javascript
var inputStream = myInputStream; //get InputStream from socket API, etc.
var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
document.getElementById("imagetag").src = URL.createObjectURL(stream); 
```

### <span data-ttu-id="26e81-222">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="26e81-222">execAsyncAtPriority</span></span> 
<span data-ttu-id="26e81-223">指定した優先度に従って、後で実行されるようにコールバックをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="26e81-223">Schedules a callback to be executed at a later time according to the given priority.</span></span> 

```javascript
MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
```

#### <span data-ttu-id="26e81-224">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-224">Parameters</span></span>
`asynchronousCallback` <span data-ttu-id="26e81-225">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-225">[in]</span></span>

|<span data-ttu-id="26e81-226">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-226">Type</span></span> | <span data-ttu-id="26e81-227">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-227">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-228">機能</span><span class="sxs-lookup"><span data-stu-id="26e81-228">Function</span></span> | <span data-ttu-id="26e81-229">非同期的に実行されるコールバック関数。指定した優先度の優先順位でディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="26e81-229">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>

`priority` <span data-ttu-id="26e81-230">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-230">[in]</span></span>

|<span data-ttu-id="26e81-231">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-231">Type</span></span> | <span data-ttu-id="26e81-232">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-232">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-233">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-233">DOMString</span></span> | <span data-ttu-id="26e81-234">AsynchronousCallback コールバックが実行されるコンテキストの優先度の値。</span><span class="sxs-lookup"><span data-stu-id="26e81-234">The contextual priority value at which the asynchronousCallback callback is run.</span></span> <span data-ttu-id="26e81-235">[Msapp の定数](#msapp-constants)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-235">See [MSApp Constants](#msapp-constants).</span></span>

`args` <span data-ttu-id="26e81-236">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-236">[in]</span></span>

|<span data-ttu-id="26e81-237">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-237">Type</span></span> | <span data-ttu-id="26e81-238">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-238">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-239">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-239">Any</span></span> | <span data-ttu-id="26e81-240">SynchronousCallback callback 関数 (パラメーター1およびオン) に渡されるオプションの連続する引数。</span><span class="sxs-lookup"><span data-stu-id="26e81-240">An optional series of arguments that are passed to the synchronousCallback callback function (as parameters 1 and on).</span></span>

#### <span data-ttu-id="26e81-241">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-241">Return value</span></span>
<span data-ttu-id="26e81-242">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-242">This method does not return a value.</span></span>

#### <span data-ttu-id="26e81-243">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-243">Remarks</span></span>
<span data-ttu-id="26e81-244">指定した `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-244">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span> `asynchronousCallback` <span data-ttu-id="26e81-245">指定した優先順位に従ってディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="26e81-245">will be dispatched according to the provided priority.</span></span> <span data-ttu-id="26e81-246">通常の優先度は、既存のメソッドと同じです [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 。</span><span class="sxs-lookup"><span data-stu-id="26e81-246">Normal priority is equivalent to the existing [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span> <span data-ttu-id="26e81-247">コールバックが実行されると、コールバックの実行中に、現在のコンテキスト優先順位が、指定された priority パラメーター値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-247">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>

<span data-ttu-id="26e81-248">Callback パラメーターには、 `asynchronousCallback` 任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="26e81-248">The `asynchronousCallback` callback parameter can be any function.</span></span> <span data-ttu-id="26e81-249">パラメーターの後に引数が指定された場合は、 `priority` すべてコールバック関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-249">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>

<span data-ttu-id="26e81-250">このように `execAtPriority` 、callback 関数によって返されるオブジェクト `asynchronousCallback` は無視されます (これによって返されることはありません `execAsyncAtPriority` )。</span><span class="sxs-lookup"><span data-stu-id="26e81-250">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored (and not returned via `execAsyncAtPriority`).</span></span>

### <span data-ttu-id="26e81-251">Exec優先度</span><span class="sxs-lookup"><span data-stu-id="26e81-251">execAtPriority</span></span> 
<span data-ttu-id="26e81-252">指定したコンテキスト優先順位で、指定したコールバック関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="26e81-252">Runs the specified callback function at the given contextual priority.</span></span>

```javascript
var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
```

#### <span data-ttu-id="26e81-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-253">Parameters</span></span>
`synchronousCallback` <span data-ttu-id="26e81-254">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-254">[in]</span></span>

|<span data-ttu-id="26e81-255">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-255">Type</span></span> | <span data-ttu-id="26e81-256">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-256">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-257">機能</span><span class="sxs-lookup"><span data-stu-id="26e81-257">Function</span></span> | <span data-ttu-id="26e81-258">指定した優先度のコンテキストの優先順位で、同期的に実行されるコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="26e81-258">The callback function to run synchronously at the given priority contextual priority.</span></span>

`priority` <span data-ttu-id="26e81-259">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-259">[in]</span></span>

|<span data-ttu-id="26e81-260">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-260">Type</span></span> | <span data-ttu-id="26e81-261">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-261">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-262">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-262">DOMString</span></span> | <span data-ttu-id="26e81-263">コールバック関数の実行時に現在のコンテキスト優先順位値が設定される、指定された優先度の値 `synchronousCallback` 。</span><span class="sxs-lookup"><span data-stu-id="26e81-263">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span> <span data-ttu-id="26e81-264">[Msapp の定数](#msapp-constants)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-264">See [MSApp Constants](#msapp-constants).</span></span>

`args` <span data-ttu-id="26e81-265">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-265">[in]</span></span>

|<span data-ttu-id="26e81-266">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-266">Type</span></span> | <span data-ttu-id="26e81-267">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-267">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-268">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-268">Any</span></span> | <span data-ttu-id="26e81-269">コールバック関数に渡されるオプションの連続する引数 `synchronousCallback` (パラメーター1と on)。</span><span class="sxs-lookup"><span data-stu-id="26e81-269">An optional series of arguments that are passed to the `synchronousCallback` callback function (as parameters 1 and on).</span></span>

#### <span data-ttu-id="26e81-270">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-270">Return value</span></span>
|<span data-ttu-id="26e81-271">型</span><span class="sxs-lookup"><span data-stu-id="26e81-271">Type</span></span> | <span data-ttu-id="26e81-272">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-272">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-273">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-273">Any</span></span> | <span data-ttu-id="26e81-274">コールバックの戻り値 (該当する場合) を返し `synchronousCallback` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-274">Returns the return value of the `synchronousCallback` callback (as applicable).</span></span>

#### <span data-ttu-id="26e81-275">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-275">Remarks</span></span>
<span data-ttu-id="26e81-276">指定した `synchronousCallback` コールバックメソッドは、同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-276">The provided `synchronousCallback` callback method is execute synchronously.</span></span> <span data-ttu-id="26e81-277">指定したコールバック関数の期間について、現在のコンテキストの優先度が、指定された priority 値 (priority 引数で指定) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-277">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span> <span data-ttu-id="26e81-278">コールバック関数の実行が終了すると、呼び出しの前の値が優先され `execAtPriority` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-278">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span> <span data-ttu-id="26e81-279">戻り値は、 `execAtPriority` (指定されているように) コールバックメソッドの戻り値です。</span><span class="sxs-lookup"><span data-stu-id="26e81-279">The return value from `execAtPriority` is the return value of the callback method (as provided).</span></span>
 
<span data-ttu-id="26e81-280">Callback パラメーターには、 `synchronousCallback` 任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="26e81-280">The `synchronousCallback` callback parameter can be any function.</span></span> <span data-ttu-id="26e81-281">Priority パラメーターの後に引数を指定すると、指定したコールバックメソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-281">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span> <span data-ttu-id="26e81-282">Callback パラメーターが値を返す場合、この値も戻り値になり `execAtPriority` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-282">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>

#### <span data-ttu-id="26e81-283">例</span><span class="sxs-lookup"><span data-stu-id="26e81-283">Example</span></span>

```javascript
var user = Windows.System.UserProfile.UserInformation;

MSApp.execAtPriority(function () { // This callback executes synchronously.
  user.getFirstNameAsync().then(function () { // Dispatches at high priority.
    return user.getLastNameAsync();
  }).done(function () { // Dispatches at high priority.
    // USEFUL CODE HERE
  });
}, MSApp.HIGH); // The second argument of the execAtPriority method.
```

### <span data-ttu-id="26e81-284">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="26e81-284">getCurrentPriority</span></span> 
<span data-ttu-id="26e81-285">現在のコンテキストの優先度を返します。</span><span class="sxs-lookup"><span data-stu-id="26e81-285">Returns the current contextual priority.</span></span>

```javascript
var retval = MSApp.getCurrentPriority();
```

#### <span data-ttu-id="26e81-286">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-286">Parameters</span></span>
<span data-ttu-id="26e81-287">ありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-287">None.</span></span> 

#### <span data-ttu-id="26e81-288">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-288">Return value</span></span>
|<span data-ttu-id="26e81-289">型</span><span class="sxs-lookup"><span data-stu-id="26e81-289">Type</span></span> | <span data-ttu-id="26e81-290">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-290">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-291">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-291">DOMString</span></span> | <span data-ttu-id="26e81-292">戻り値は、、またはのいずれかの文字列です `MSApp.HIGH` `MSApp.NORMAL` `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="26e81-292">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>

#### <span data-ttu-id="26e81-293">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-293">Remarks</span></span>
<span data-ttu-id="26e81-294">このメソッドは現在のコンテキスト優先度 ( [`MSApp Constants`](#msapp-constants) を参照) を返します。これは、およびとの間で変更することができ `execAtPriority` `execAsyncAtPriority` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-294">This method returns the current contextual priority (see [`MSApp Constants`](#msapp-constants)), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>

#### <span data-ttu-id="26e81-295">例</span><span class="sxs-lookup"><span data-stu-id="26e81-295">Example</span></span>

```javascript
if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
  // YOUR CODE HERE
}
```

### <span data-ttu-id="26e81-296">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="26e81-296">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="26e81-297">廃止された同期 API。</span><span class="sxs-lookup"><span data-stu-id="26e81-297">Synchronous API that has been deprecated.</span></span> <span data-ttu-id="26e81-298">Windows 10 の場合は、を参照してください `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="26e81-298">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span> <span data-ttu-id="26e81-299">Windows 8 アプリと8.1 アプリの場合は、 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-299">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="26e81-300">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="26e81-300">getHtmlPrintDocumentSourceAsync</span></span>
<span data-ttu-id="26e81-301">印刷対象のソースコンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="26e81-301">Returns the source content that is to be printed.</span></span>

#### <span data-ttu-id="26e81-302">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-302">Parameters</span></span>
`htmlDoc` <span data-ttu-id="26e81-303">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-303">[in]</span></span>

|<span data-ttu-id="26e81-304">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-304">Type</span></span> | <span data-ttu-id="26e81-305">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-305">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-306">Document</span><span class="sxs-lookup"><span data-stu-id="26e81-306">Document</span></span> | <span data-ttu-id="26e81-307">印刷する HTML 文書。</span><span class="sxs-lookup"><span data-stu-id="26e81-307">The HTML document to be printed.</span></span> <span data-ttu-id="26e81-308">これは、ルートドキュメント、iframe 内のドキュメント、ドキュメントフラグメント、または SVG ドキュメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="26e81-308">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span> <span data-ttu-id="26e81-309">HtmlDoc は、要素ではなく、文書である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-309">Be aware that htmlDoc must be a document, not an element.</span></span>

#### <span data-ttu-id="26e81-310">例 1</span><span class="sxs-lookup"><span data-stu-id="26e81-310">Example 1</span></span>

```javascript
var printTask = event.request.createPrintTask(title, function (args) {
                var deferral = args.getDeferral();
                var getPrintDocumentSourceAsync;
                if (MSApp.getHtmlPrintDocumentSourceAsync) { // Windows 10
                    getPrintDocumentSourceAsync = MSApp.getHtmlPrintDocumentSourceAsync(document);
                } else {
                    getPrintDocumentSourceAsync = WinJS.Promise.as(MSApp.getHtmlPrintDocumentSource(document));
                }
                getPrintDocumentSourceAsync.then(function (source) {
                    args.setSource(source);
                    deferral.complete();
                }, function (error) {
                    console.error(error);
                    deferral.complete();
                });
            });
```

#### <span data-ttu-id="26e81-311">例 2</span><span class="sxs-lookup"><span data-stu-id="26e81-311">Example 2</span></span>

```javascript
    function registerForPrintContract() {
            var printManager = Windows.Graphics.Printing.PrintManager.getForCurrentView();
            printManager.onprinttaskrequested = onPrintTaskRequested;
            console.log("Print Contract registered. Use the Print button to print.", "sample", "status");
    }
    
    // Variable to hold the document source to print
    var gHtmlPrintDocumentSource = null;
    
    // Print event handler for printing via the PrintManager API.
    function onPrintTaskRequested(printEvent) {
        var printTask = printEvent.request.createPrintTask("Print Sample", function (args) {
            args.setSource(gHtmlPrintDocumentSource);
    
            // Register the handler for print task completion event
            printTask.oncompleted = onPrintTaskCompleted;
        });
    }
    
    // Print Task event handler is invoked when the print job is completed.
    function onPrintTaskCompleted(printTaskCompletionEvent) {
        // Notify the user about the failure
        if (printTaskCompletionEvent.completion === Windows.Graphics.Printing.PrintTaskCompletion.failed) {
            console.log("Failed to print.", "sample", "error");
        }
    }
    
    // Executed just before printing.
    var beforePrint = function () {
        // Replace with code to be executed just before printing the current document:
    };
    
    // Executed immediately after printing.
    var afterPrint = function () {
        // Replace with code to be executed immediately after printing the current document:
    };
    
    function printButtonHandler() {
        // Optionally, functions to be executed immediately before and after printing can be configured as following:
        window.document.body.onbeforeprint = beforePrint;
        window.document.body.onafterprint = afterPrint;
    
        // Get document source to print
        MSApp.getHtmlPrintDocumentSourceAsync(document).then(function (htmlPrintDocumentSource) {
            gHtmlPrintDocumentSource = htmlPrintDocumentSource;
    
            // If the print contract is registered, the print experience is invoked.
            Windows.Graphics.Printing.PrintManager.showPrintUIAsync();
        });
    }
```

### <span data-ttu-id="26e81-312">getViewId</span><span class="sxs-lookup"><span data-stu-id="26e81-312">getViewId</span></span> 
<span data-ttu-id="26e81-313">複数のウィンドウのサポート。</span><span class="sxs-lookup"><span data-stu-id="26e81-313">Support for multiple windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="26e81-314">Win 8.1 JavaScript の UWP アプリでは、depricated になった MSApp DOM Api を使用して複数のウィンドウがサポートされていました。</span><span class="sxs-lookup"><span data-stu-id="26e81-314">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span> <span data-ttu-id="26e81-315">Windows 10 では、、、 `window.open` `window` および新しいを使用 `MSApp.getViewId` します。</span><span class="sxs-lookup"><span data-stu-id="26e81-315">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>

| <span data-ttu-id="26e81-316">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-316">Description</span></span> |<span data-ttu-id="26e81-317">Windows 10</span><span class="sxs-lookup"><span data-stu-id="26e81-317">Windows 10</span></span> | <span data-ttu-id="26e81-318">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="26e81-318">Windows 8.1</span></span> |  
|:---- |:---- |:--- |  
| <span data-ttu-id="26e81-319">新しいウィンドウを作成する</span><span class="sxs-lookup"><span data-stu-id="26e81-319">Create new window</span></span> | [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) | [`MSApp.createNewView`](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
|<span data-ttu-id="26e81-320">新しい window オブジェクト</span><span class="sxs-lookup"><span data-stu-id="26e81-320">New window object</span></span> | [`window`](https://developer.mozilla.org/docs/Web/API/Window) |[`MSAppView`](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  

```javascript
var retval = MSApp.getViewId(window); 
```

#### <span data-ttu-id="26e81-321">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-321">Parameters</span></span>
`window`

|<span data-ttu-id="26e81-322">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-322">Type</span></span> | <span data-ttu-id="26e81-323">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-323">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-324">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-324">DOMString</span></span> | <span data-ttu-id="26e81-325">DOM ドキュメントを含むウィンドウを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="26e81-325">An object representing a window containing a DOM document.</span></span> | 

#### <span data-ttu-id="26e81-326">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-326">Return value</span></span>

`viewId`

|<span data-ttu-id="26e81-327">型</span><span class="sxs-lookup"><span data-stu-id="26e81-327">Type</span></span> | <span data-ttu-id="26e81-328">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-328">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-329">Number</span><span class="sxs-lookup"><span data-stu-id="26e81-329">Number</span></span> | <span data-ttu-id="26e81-330">さまざまな api と共に使うことができ [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-330">Can be used with the various [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span> 

#### <span data-ttu-id="26e81-331">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-331">Remarks</span></span>
<span data-ttu-id="26e81-332">[`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) [`window`](https://developer.mozilla.org/docs/Web/API/Window) 新しいウィンドウの作成にはを使用しますが、WinRT api を操作するには、API を追加し `MSApp.getViewId` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-332">Use [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) and [`window`](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span> <span data-ttu-id="26e81-333">`window`パラメーターとしてオブジェクトを受け取り、 `viewId` さまざまな api で使うことができる数値を返し [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-333">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span> 

##### <span data-ttu-id="26e81-334">Visibility の遅延</span><span class="sxs-lookup"><span data-stu-id="26e81-334">Delaying Visibility</span></span> 
<span data-ttu-id="26e81-335">WinRT のビューは通常は非表示になり、エンド開発者は、 `TryShowAsStandaloneAsync` 完全に準備ができたらビューを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-335">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span> <span data-ttu-id="26e81-336">Web 環境では、 `window.open` ウィンドウがすぐに表示され、エンドユーザーはコンテンツの読み込みとレンダリングを監視できます。</span><span class="sxs-lookup"><span data-stu-id="26e81-336">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span> <span data-ttu-id="26e81-337">新しい windows で WinRT のビューを操作し、すぐに表示されないようにするには、オプションを追加し `window.open` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-337">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span> <span data-ttu-id="26e81-338">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="26e81-338">For example:</span></span>
`let newWindow = window.open("https://example.com", null, "msHideView=yes");`

##### <span data-ttu-id="26e81-339">主要なウィンドウの相違点</span><span class="sxs-lookup"><span data-stu-id="26e81-339">Primary Window Differences</span></span>
<span data-ttu-id="26e81-340">OS によって最初に開かれるプライマリウィンドウは、開かれるセカンダリウィンドウとは動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="26e81-340">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span> 

|<span data-ttu-id="26e81-341">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-341">Description</span></span> | <span data-ttu-id="26e81-342">プライマリ</span><span class="sxs-lookup"><span data-stu-id="26e81-342">Primary</span></span> | <span data-ttu-id="26e81-343">セカンダリ</span><span class="sxs-lookup"><span data-stu-id="26e81-343">Secondary</span></span> |
|:---- |:--- |:--- |
|<span data-ttu-id="26e81-344">ウィンドウ。開く</span><span class="sxs-lookup"><span data-stu-id="26e81-344">window.open</span></span> | <span data-ttu-id="26e81-345">許可されます</span><span class="sxs-lookup"><span data-stu-id="26e81-345">Allowed</span></span> | <span data-ttu-id="26e81-346">Disallowed</span><span class="sxs-lookup"><span data-stu-id="26e81-346">Disallowed</span></span> |
|<span data-ttu-id="26e81-347">ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26e81-347">window.close</span></span> | <span data-ttu-id="26e81-348">アプリを閉じる</span><span class="sxs-lookup"><span data-stu-id="26e81-348">Close app</span></span> | <span data-ttu-id="26e81-349">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="26e81-349">Close window</span></span> |
| <span data-ttu-id="26e81-350">ナビゲーションの制限</span><span class="sxs-lookup"><span data-stu-id="26e81-350">Navigation restrictions</span></span> | <span data-ttu-id="26e81-351">ACUR のみ</span><span class="sxs-lookup"><span data-stu-id="26e81-351">ACUR only</span></span> | <span data-ttu-id="26e81-352">制限なし</span><span class="sxs-lookup"><span data-stu-id="26e81-352">No restrictions</span></span> |

<span data-ttu-id="26e81-353">セカンダリウィンドウを開くことを許可しない制約は、[フィードバック](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)に応じて将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26e81-353">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>

##### <span data-ttu-id="26e81-354">同じ元の通信制限</span><span class="sxs-lookup"><span data-stu-id="26e81-354">Same Origin Communication Restrictions</span></span> 
<span data-ttu-id="26e81-355">同期、同じ元のウィンドウ、クロスウィンドウ、スクリプト呼び出しの適切なサポートを防ぐ困難な技術上の問題があります。</span><span class="sxs-lookup"><span data-stu-id="26e81-355">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span> <span data-ttu-id="26e81-356">同じ元のウィンドウを開くと、1つのウィンドウのスクリプトは、他のウィンドウで関数を直接呼び出すことができ、一部の呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="26e81-356">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span> `postMessage` <span data-ttu-id="26e81-357">通話は正常に機能します。可能であれば、問題を解決するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="26e81-357">calls work just fine and is the recommended way to do things if possible.</span></span> <span data-ttu-id="26e81-358">この問題を改善するための作業は進行中です。</span><span class="sxs-lookup"><span data-stu-id="26e81-358">Work to improve this issue is in progress.</span></span>


### <span data-ttu-id="26e81-359">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="26e81-359">isTaskScheduledAtPriorityOrHigher</span></span> 
<span data-ttu-id="26e81-360">指定した優先度レベル以上で、保留中の作業があるかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="26e81-360">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>

```javascript
var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
```

#### <span data-ttu-id="26e81-361">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-361">Parameters</span></span>
`priority` <span data-ttu-id="26e81-362">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-362">[in]</span></span>

|<span data-ttu-id="26e81-363">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-363">Type</span></span> | <span data-ttu-id="26e81-364">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-364">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-365">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-365">DOMString</span></span> | <span data-ttu-id="26e81-366">未解決のキューに入っている作業を照会するには、priority の値 ( [Msapp 定数](#msapp-constants)を参照) を指定します。</span><span class="sxs-lookup"><span data-stu-id="26e81-366">A priority value (see [MSApp Constants](#msapp-constants)) specifying the priority level and above to query for any outstanding queued work.</span></span>

#### <span data-ttu-id="26e81-367">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-367">Return value</span></span>
|<span data-ttu-id="26e81-368">型</span><span class="sxs-lookup"><span data-stu-id="26e81-368">Type</span></span> | <span data-ttu-id="26e81-369">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-369">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-370">ブール値</span><span class="sxs-lookup"><span data-stu-id="26e81-370">Boolean</span></span> | <span data-ttu-id="26e81-371">`true`指定した優先度レベル以上のキューに入っている作業があるかどうかを返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-371">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>

#### <span data-ttu-id="26e81-372">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-372">Remarks</span></span>
<span data-ttu-id="26e81-373">この `isTaskScheduledAtPriorityOrHigher` メソッドは、javascript コードがさまざまな優先度レベル (以上) に保留中の作業があるかどうかを判断するための手段を提供します。これにより、呼び出し元の javascript コードが優先度の高い作業によって得られることが意図されています。</span><span class="sxs-lookup"><span data-stu-id="26e81-373">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels (or above) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>

#### <span data-ttu-id="26e81-374">例</span><span class="sxs-lookup"><span data-stu-id="26e81-374">Example</span></span>

```javascript
function performIdleWork(array_in) {
  var idx = 0;

  function performIdleWorkHelper() {
    for (; idx < array_in.length; ++idx) {

      // USEFUL CODE HERE 

      if (MSApp.isTaskScheduledAtPriorityOrHigher(MSApp.NORMAL)) {
        MSApp.execAsyncAtPriority(performIdleWorkHelper, msPriority.IDLE);
        break;
      } // if
    } // for
  } // performIdleWorkHelper

  performIdleWorkHelper();
} // performIdleWork
```

### <span data-ttu-id="26e81-375">pageHandlesAllApplicationActivations アクティベーション</span><span class="sxs-lookup"><span data-stu-id="26e81-375">pageHandlesAllApplicationActivations</span></span>
<span data-ttu-id="26e81-376">すべてのアクティブ化イベント (ie) の前に、開始パス (ページの読み込み) が更新されないようにするために使います (通知またはピン留めされたタイルをクリックします)。</span><span class="sxs-lookup"><span data-stu-id="26e81-376">Used to avoid a refresh of the start path (page reload) before every activate event (ie. clicking a notification or a pinned tile).</span></span> 

#### <span data-ttu-id="26e81-377">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-377">Parameters</span></span>

|<span data-ttu-id="26e81-378">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-378">Type</span></span> | <span data-ttu-id="26e81-379">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-379">Description</span></span> |
|:---- |:--- |
<span data-ttu-id="26e81-380">ブール値</span><span class="sxs-lookup"><span data-stu-id="26e81-380">Boolean</span></span> | <span data-ttu-id="26e81-381">`MSApp.pageHandlesAllApplicationActivations(true)`開始パス (ページの再読み込み) の更新を常にスキップして、アクティブ化されたイベントを発生させるには直接ジャンプし `WebUIApplication` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-381">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span> <span data-ttu-id="26e81-382">すべてのページで、アクティブ化イベントを個別に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26e81-382">Requires that all pages handle activation events separately.</span></span> <span data-ttu-id="26e81-383">このメソッドをとして定義することによって `true` 、アクティブ化されたイベント (notificaiton など) をクリックしても、ページの読み込みを回避する単一ページアプリにとって重要な再読み込みはトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="26e81-383">By defining this method as `true`, clicking an activated event (like a notificaiton) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>

#### <span data-ttu-id="26e81-384">例</span><span class="sxs-lookup"><span data-stu-id="26e81-384">Example</span></span> 

```javascript
// Without this, the app will first refresh to the start path before every activate event
window.MSApp.pageHandlesAllApplicationActivations(true); 

// This must not be deffered so that it can receive the initial `activated` event in time
window.Windows.UI.WebUI.WebUIApplication.addEventListener(
    `activated`,
    e =>
        microsoftInterface.handleActivatedEvent(e);
    }),
    false
);
```

### <span data-ttu-id="26e81-385">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="26e81-385">suppressSubdownloadCredentialPrompts</span></span> 
<span data-ttu-id="26e81-386">アプリで、リソースのダウンロード中に認証プロンプトが表示されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="26e81-386">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>

```javascript
MSApp.suppressSubdownloadCredentialPrompts(suppress); 
```

#### <span data-ttu-id="26e81-387">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-387">Parameters</span></span>
`suppress` <span data-ttu-id="26e81-388">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-388">[in]</span></span>

|<span data-ttu-id="26e81-389">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-389">Type</span></span> | <span data-ttu-id="26e81-390">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-390">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-391">ブール値</span><span class="sxs-lookup"><span data-stu-id="26e81-391">Boolean</span></span> | <span data-ttu-id="26e81-392">値が true の場合、認証のためのプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="26e81-392">A value of true suppresses potential authentication prompts.</span></span> <span data-ttu-id="26e81-393">値が false の場合、ユーザーからの認証を求めるメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="26e81-393">A value of false does not suppress any potential authentication prompts from the user.</span></span>

#### <span data-ttu-id="26e81-394">Returan 値</span><span class="sxs-lookup"><span data-stu-id="26e81-394">Returan value</span></span>
<span data-ttu-id="26e81-395">なし。</span><span class="sxs-lookup"><span data-stu-id="26e81-395">None.</span></span>

#### <span data-ttu-id="26e81-396">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-396">Remarks</span></span>
<span data-ttu-id="26e81-397">この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中に、アプリで認証プロンプトが表示されないようにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="26e81-397">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span> <span data-ttu-id="26e81-398">既定の動作では、資格情報の入力は抑制されません。</span><span class="sxs-lookup"><span data-stu-id="26e81-398">The default behavior is to not suppress credential prompts.</span></span>

`suppressSubdownloadCredentialPrompts` <span data-ttu-id="26e81-399">メールアプリなど、認証が必要な大量のリソースを読み込む可能性があるアプリ (各画像には、認証が必要な数の画像を含むニュースレターが含まれている場合があります) を使うことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="26e81-399">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app (which could contain a newsletter containing a number of images where each image requires authentication).</span></span>

<span data-ttu-id="26e81-400">資格情報の入力を求めるメッセージは、認証を必要とするリソースにアクセスするときに、サーバーに対して認証するためのダイアログを表示せず、リソースはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="26e81-400">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span> <span data-ttu-id="26e81-401">`suppressSubdownloadCredentialPrompts`プロキシ認証やクライアント証明要求のダイアログなどの他の確認できるプロンプトや、XHR への影響はありませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-401">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>

<span data-ttu-id="26e81-402">`suppressSubdownloadCredentialPrompts`要素でホストされているコンテンツを含む、アプリケーション内のすべてのコンテンツに影響を与えることに注意 `webview` してください。</span><span class="sxs-lookup"><span data-stu-id="26e81-402">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>
 
<span data-ttu-id="26e81-403">**重要:** 資格情報の確認の判断がキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="26e81-403">**Important:**  Credential prompt decisions are cached.</span></span> <span data-ttu-id="26e81-404">そのため、資格情報を抑制するためのプロンプトはすぐに有効になります。これを抑制した後で資格情報のプロンプトが表示されるようにするには、ドキュメントの再読み込みが必要な場合があります</span><span class="sxs-lookup"><span data-stu-id="26e81-404">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>

#### <span data-ttu-id="26e81-405">例</span><span class="sxs-lookup"><span data-stu-id="26e81-405">Example</span></span>

```javascript
/ Set to true to suppress potenial credential prompts:
MSApp.suppressSubdownloadCredentialPrompts(true); 
// Now one can load content or navigate iframe/webview to some other site.
```

### <span data-ttu-id="26e81-406">terminateApp</span><span class="sxs-lookup"><span data-stu-id="26e81-406">terminateApp</span></span>
<span data-ttu-id="26e81-407">現在のアプリケーションを終了し、エラーレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="26e81-407">Terminates the current application and generates a failure report.</span></span> 

```javascript
MSApp.terminateApp(error); 
```

#### <span data-ttu-id="26e81-408">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-408">Parameters</span></span>
`error` <span data-ttu-id="26e81-409">チェックイン</span><span class="sxs-lookup"><span data-stu-id="26e81-409">[in]</span></span>

<span data-ttu-id="26e81-410">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-410">Type</span></span> | <span data-ttu-id="26e81-411">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-411">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-412">エラー</span><span class="sxs-lookup"><span data-stu-id="26e81-412">Error</span></span> | <span data-ttu-id="26e81-413">`Error`終了をトリガーしたエラーを説明するために使うことができるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="26e81-413">An `Error` object that you can use to describe the error that triggered the termination.</span></span> <span data-ttu-id="26e81-414">このオブジェクトには、 `Error` 数値、説明、スタックの各プロパティが含まれている必要があります。これらのプロパティがオブジェクトに含まれていない場合、エラーレポートは生成されません。</span><span class="sxs-lookup"><span data-stu-id="26e81-414">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>

#### <span data-ttu-id="26e81-415">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-415">Return value</span></span>
<span data-ttu-id="26e81-416">なし。</span><span class="sxs-lookup"><span data-stu-id="26e81-416">None.</span></span>

#### <span data-ttu-id="26e81-417">注釈</span><span class="sxs-lookup"><span data-stu-id="26e81-417">Remarks</span></span>
<span data-ttu-id="26e81-418">この問題が報告された場合は、 `terminateApp` アプリの上位5つの問題のいずれかになります。アプリの [品質] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-418">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>

#### <span data-ttu-id="26e81-419">例</span><span class="sxs-lookup"><span data-stu-id="26e81-419">Example</span></span>
<span data-ttu-id="26e81-420">次の例 `terminateApp` は、例外が発生したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="26e81-420">This example calls `terminateApp` when an exception is encountered.</span></span> <span data-ttu-id="26e81-421">`Error`例外をキャッチするときに指定されたオブジェクトを使います。</span><span class="sxs-lookup"><span data-stu-id="26e81-421">It uses the `Error` object provided when you catch an exception.</span></span> 

```javascript
try {  
        var obj2 = null;  
        obj2.val = 5;  
    }  
    catch(e) {  
        window.MSApp.terminateApp(e);  
    }  
```

### <span data-ttu-id="26e81-422">MSApp の定数</span><span class="sxs-lookup"><span data-stu-id="26e81-422">MSApp Constants</span></span>
<span data-ttu-id="26e81-423">`execAsyncAtPriority`、、 `execAtPriority` `getCurrentPriority` 、およびに関連付けられた優先順位の値 `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="26e81-423">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>

#### <span data-ttu-id="26e81-424">現在の顧客</span><span class="sxs-lookup"><span data-stu-id="26e81-424">Current</span></span>
`current`

|<span data-ttu-id="26e81-425">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-425">Type</span></span> | <span data-ttu-id="26e81-426">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-426">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-427">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-427">DOMString</span></span> | <span data-ttu-id="26e81-428">`current`適切なメソッド (「セクション」も参照) では、要求された操作を実行するときに、現在のコンテキストの優先度を使用します。</span><span class="sxs-lookup"><span data-stu-id="26e81-428">When `current` is used with the appropriate method (See also section), the method will use the current contextual priority when executing the requested operation.</span></span>

#### <span data-ttu-id="26e81-429">高</span><span class="sxs-lookup"><span data-stu-id="26e81-429">High</span></span>
`high`

|<span data-ttu-id="26e81-430">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-430">Type</span></span> | <span data-ttu-id="26e81-431">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-431">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-432">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-432">DOMString</span></span> | <span data-ttu-id="26e81-433">`high`適切なメソッド (「セクション」も参照) では、要求された操作を実行するときに、メソッドは通常の優先度よりも使用されます。また、既存の通常の優先順位の作業の前に操作がディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="26e81-433">When `high` is used with the appropriate method (See also section), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>

#### <span data-ttu-id="26e81-434">アイドル</span><span class="sxs-lookup"><span data-stu-id="26e81-434">Idle</span></span>
`idle`

|<span data-ttu-id="26e81-435">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-435">Type</span></span> | <span data-ttu-id="26e81-436">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-436">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-437">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-437">DOMString</span></span> | <span data-ttu-id="26e81-438">`ideal`適切なメソッド (「セクション」も参照) で使用すると、要求された操作を実行するときに、メソッドは通常の優先度よりも低い優先度を使用し、既存の通常の優先度作業の後に操作をディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="26e81-438">When `ideal` is used with the appropriate method (See also section), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>

#### <span data-ttu-id="26e81-439">通常</span><span class="sxs-lookup"><span data-stu-id="26e81-439">Normal</span></span>
`normal`

|<span data-ttu-id="26e81-440">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-440">Type</span></span> | <span data-ttu-id="26e81-441">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-441">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-442">DOMString</span><span class="sxs-lookup"><span data-stu-id="26e81-442">DOMString</span></span> | <span data-ttu-id="26e81-443">`normal`適切なメソッド (「セクション」も参照) で使用すると、要求された操作を実行するときに、メソッドは既存の標準優先度を使います。</span><span class="sxs-lookup"><span data-stu-id="26e81-443">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>

#### <span data-ttu-id="26e81-444">例</span><span class="sxs-lookup"><span data-stu-id="26e81-444">Example</span></span>

```javascript
if (window.MSApp.CURRENT) {
  document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
}
```

#### <span data-ttu-id="26e81-445">要件</span><span class="sxs-lookup"><span data-stu-id="26e81-445">Requirements</span></span>
|<span data-ttu-id="26e81-446">.IDL</span><span class="sxs-lookup"><span data-stu-id="26e81-446">IDL</span></span> | <span data-ttu-id="26e81-447">Mshtml.dll</span><span class="sxs-lookup"><span data-stu-id="26e81-447">Mshtml.idl</span></span> |
|:---- |:--- |

## <span data-ttu-id="26e81-448">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="26e81-448">MSAppAsyncOperation</span></span>

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```

### <span data-ttu-id="26e81-449">start</span><span class="sxs-lookup"><span data-stu-id="26e81-449">start</span></span>
<span data-ttu-id="26e81-450">を起動 `MSAppAsyncOperation` します。</span><span class="sxs-lookup"><span data-stu-id="26e81-450">Starts the `MSAppAsyncOperation`.</span></span>

```javascript
var retval = MSAppAsyncOperation.start();
```

#### <span data-ttu-id="26e81-451">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e81-451">Parameters</span></span>
<span data-ttu-id="26e81-452">ありません。</span><span class="sxs-lookup"><span data-stu-id="26e81-452">None.</span></span>

#### <span data-ttu-id="26e81-453">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e81-453">Return value</span></span>
<span data-ttu-id="26e81-454">なし。</span><span class="sxs-lookup"><span data-stu-id="26e81-454">None.</span></span>

#### <span data-ttu-id="26e81-455">プロパティ</span><span class="sxs-lookup"><span data-stu-id="26e81-455">Properties</span></span>
`error` <span data-ttu-id="26e81-456">プロパティー</span><span class="sxs-lookup"><span data-stu-id="26e81-456">property</span></span>

|<span data-ttu-id="26e81-457">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-457">Type</span></span> | <span data-ttu-id="26e81-458">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-458">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-459">DOMError</span><span class="sxs-lookup"><span data-stu-id="26e81-459">DOMError</span></span> | <span data-ttu-id="26e81-460">のエラーを表し `MSAppAsyncOperation` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-460">Represents an error in `MSAppAsyncOperation`.</span></span>

```javascript
p = object.error
```

`oncomplete` <span data-ttu-id="26e81-461">プロパティー</span><span class="sxs-lookup"><span data-stu-id="26e81-461">property</span></span>

|<span data-ttu-id="26e81-462">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-462">Type</span></span> | <span data-ttu-id="26e81-463">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-463">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-464">EventHandler</span><span class="sxs-lookup"><span data-stu-id="26e81-464">EventHandler</span></span> | <span data-ttu-id="26e81-465">イベントハンドラーを完了時に設定するためのプロパティ `MSAppAsyncOperation` です。</span><span class="sxs-lookup"><span data-stu-id="26e81-465">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>

```javascript
p = object.oncomplete
```

`onerror` <span data-ttu-id="26e81-466">プロパティー</span><span class="sxs-lookup"><span data-stu-id="26e81-466">property</span></span>

|<span data-ttu-id="26e81-467">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-467">Type</span></span> | <span data-ttu-id="26e81-468">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-468">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-469">EventHandler</span><span class="sxs-lookup"><span data-stu-id="26e81-469">EventHandler</span></span> | <span data-ttu-id="26e81-470">中にエラーが発生したときにイベントハンドラーを設定するプロパティ `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="26e81-470">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>

```javascript
p = object.onerror
```

`readyState` <span data-ttu-id="26e81-471">プロパティー</span><span class="sxs-lookup"><span data-stu-id="26e81-471">property</span></span>

|<span data-ttu-id="26e81-472">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-472">Type</span></span> | <span data-ttu-id="26e81-473">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-473">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-474">Number</span><span class="sxs-lookup"><span data-stu-id="26e81-474">Number</span></span> | <span data-ttu-id="26e81-475">JavaScript を使った Windows アプリ内の非同期操作の状態を表します。</span><span class="sxs-lookup"><span data-stu-id="26e81-475">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span> <span data-ttu-id="26e81-476">値は次のとおりです。開始 [0]、完了 [1]、エラー [2]。</span><span class="sxs-lookup"><span data-stu-id="26e81-476">Values include: Started[0], Completed[1], Error[2].</span></span>

```javascript
p = object.readyState
```

`result` <span data-ttu-id="26e81-477">プロパティー</span><span class="sxs-lookup"><span data-stu-id="26e81-477">property</span></span>

|<span data-ttu-id="26e81-478">種類</span><span class="sxs-lookup"><span data-stu-id="26e81-478">Type</span></span> | <span data-ttu-id="26e81-479">説明</span><span class="sxs-lookup"><span data-stu-id="26e81-479">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="26e81-480">任意</span><span class="sxs-lookup"><span data-stu-id="26e81-480">Any</span></span> |<span data-ttu-id="26e81-481">の結果を表し `MSAppAsyncOperation` ます。</span><span class="sxs-lookup"><span data-stu-id="26e81-481">Represents the result of `MSAppAsyncOperation`.</span></span>

```javascript
p = object.result
```
