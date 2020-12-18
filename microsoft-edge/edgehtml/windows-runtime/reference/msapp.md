---
title: MSApp API リファレンス
description: Blob オブジェクトと MSStream オブジェクトを作成できるヘルパー関数を提供します。  MSApp オブジェクトとメンバーは、JavaScript を使用する Windows アプリでサポートされています。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp、PWA、ファイルのアップロード、ブログ、MSStream、Windows 10 アプリ、UWP、Edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a3ad670f61bfafa4480c538dd8f28c7013b7d7f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234646"
---
# <span data-ttu-id="1248d-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="1248d-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="1248d-106">MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API 機能にアクセスする PAS を含む) を使用する Windows アプリでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1248d-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="1248d-107">MSApp オブジェクトは、ms-appx URI スキームによって読み込まれた Windows アプリの HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (したがって、オブジェクトのメソッドとプロパティはいずれも使用できません)。</span><span class="sxs-lookup"><span data-stu-id="1248d-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="1248d-108">Blob オブジェクトと MSStream オブジェクトを[作成できるヘルパー](https://developer.mozilla.org/docs/Web/API/Blob)[関数を提供](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="1248d-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="1248d-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="1248d-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1248d-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage , createDataPackageFromSelection](#createdatapackage), [createFileFromStorageFile](#createfilefromstoragefile), [](#createdatapackagefromselection) [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span><span class="sxs-lookup"><span data-stu-id="1248d-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1248d-111">定数</span><span class="sxs-lookup"><span data-stu-id="1248d-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1248d-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span><span class="sxs-lookup"><span data-stu-id="1248d-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1248d-113">MSAppAsyncOperation インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1248d-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="1248d-114">start</span><span class="sxs-lookup"><span data-stu-id="1248d-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="1248d-115">MSApp メソッド</span><span class="sxs-lookup"><span data-stu-id="1248d-115">MSApp methods</span></span>  

### <span data-ttu-id="1248d-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="1248d-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-117">アプリまたは WebView のキャッシュとインデックス付きDB データを [クリアします](../../hosting/webview/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1248d-117">Clears cache and indexedDB data for the app or [WebView](../../hosting/webview/index.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-118">Parameters</span></span>**  
      
      <span data-ttu-id="1248d-119">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-120">Return value</span></span>**  
      
      <span data-ttu-id="1248d-121">型: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="1248d-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="1248d-122">非同期アクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1248d-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-123">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-123">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-124">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-125">解説</span><span class="sxs-lookup"><span data-stu-id="1248d-125">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-126">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-127">例</span><span class="sxs-lookup"><span data-stu-id="1248d-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="1248d-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-129">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)オブジェクトから[BLOB](https://developer.mozilla.org/docs/Web/API/Blob)を作成します。</span><span class="sxs-lookup"><span data-stu-id="1248d-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="1248d-130">このメソッドは、ストリームから W3C ベースのオブジェクトを作成するために、アプリでオブジェクトを処理するときに `IRandomAccessStream` 使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="1248d-131">作成された BLOB は [、FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、および](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest で使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="1248d-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="1248d-133">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-133">[in]</span></span>  
      
      | <span data-ttu-id="1248d-134">型</span><span class="sxs-lookup"><span data-stu-id="1248d-134">Type</span></span> | <span data-ttu-id="1248d-135">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-136">String</span><span class="sxs-lookup"><span data-stu-id="1248d-136">String</span></span> | <span data-ttu-id="1248d-137">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="1248d-137">Content type of the data.</span></span>  <span data-ttu-id="1248d-138">この文字列は、RFC 2616 のセクション 3.7 で定義されているメディアタイプ トークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="1248d-139">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-139">[in]</span></span>  
      
      | <span data-ttu-id="1248d-140">型</span><span class="sxs-lookup"><span data-stu-id="1248d-140">Type</span></span> | <span data-ttu-id="1248d-141">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-142">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-142">Any</span></span> | <span data-ttu-id="1248d-143">[BLOB に格納される IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="1248d-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-144">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-144">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-145">型</span><span class="sxs-lookup"><span data-stu-id="1248d-145">Type</span></span> | <span data-ttu-id="1248d-146">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-147">Blob</span><span class="sxs-lookup"><span data-stu-id="1248d-147">Blob</span></span> | <span data-ttu-id="1248d-148">ストリームを含む新しい BLOB オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1248d-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-149">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="1248d-150">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-150">Exception</span></span> | <span data-ttu-id="1248d-151">状況</span><span class="sxs-lookup"><span data-stu-id="1248d-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="1248d-152">TypeMismatchError</span></span> | <span data-ttu-id="1248d-153">ノードの種類は、想定されるパラメーターの種類と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="1248d-154">Internet Explorer 10 より前のTYPE_MISMATCH_ERRが返されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-155">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-155">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-156">Windows ランタイム型から、ウィンドウ オブジェクトの MSApp 名前空間を介して BLOB を作成します。</span><span class="sxs-lookup"><span data-stu-id="1248d-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="1248d-157">このメソッドは、基本的に、提供された [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクトのライト ラッパーである BLOB を作成します。</span><span class="sxs-lookup"><span data-stu-id="1248d-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="1248d-158">BLOB はこのストリームの有効期間を所有し、BLOB が破棄されるとストリームは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="1248d-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-159">例</span><span class="sxs-lookup"><span data-stu-id="1248d-159">Example</span></span>**  
      
      ```javascript
      var randomAccessStream = dataPackage.GetData("image/bmp");
      var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
      var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});
      
      document.getElementById("imagetag").src = url; 
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="1248d-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-161">ユーザーまたはアプリケーションの指定範囲を、共有可能な HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="1248d-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="1248d-163">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-163">[in]</span></span>  
      
      | <span data-ttu-id="1248d-164">型</span><span class="sxs-lookup"><span data-stu-id="1248d-164">Type</span></span> | <span data-ttu-id="1248d-165">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-166">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-166">Any</span></span> | <span data-ttu-id="1248d-167">この範囲は、選択オブジェクト (例: または手動) `window.selection.getRangeAt(0)` から作成できます。</span><span class="sxs-lookup"><span data-stu-id="1248d-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-168">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-168">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-169">型</span><span class="sxs-lookup"><span data-stu-id="1248d-169">Type</span></span> | <span data-ttu-id="1248d-170">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-171">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-171">Any</span></span> | <span data-ttu-id="1248d-172">指定した範囲の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1248d-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-173">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-173">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-174">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-175">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-175">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-176">このメソッドは [、TextRange ではなく、ドキュメント オブジェクト モデル (DOM) の](https://developer.mozilla.org/docs/Web/API/Range)範囲のみを [サポートしています](/uwp/api/windows.ui.xaml.documents.textrange)。</span><span class="sxs-lookup"><span data-stu-id="1248d-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="1248d-177">指定した範囲に返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1248d-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="1248d-178">返されるデータ パッケージに使用可能なプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-179">例</span><span class="sxs-lookup"><span data-stu-id="1248d-179">Example</span></span>**  
      
      <span data-ttu-id="1248d-180">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="1248d-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-182">ユーザーまたはアプリケーションの選択内容を、共有可能な HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="1248d-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-183">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-183">Parameters</span></span>**  
      
      <span data-ttu-id="1248d-184">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-185">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-185">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-186">型</span><span class="sxs-lookup"><span data-stu-id="1248d-186">Type</span></span> | <span data-ttu-id="1248d-187">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-188">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-188">Any</span></span> | <span data-ttu-id="1248d-189">指定した範囲の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1248d-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-190">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-190">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-191">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-192">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-192">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-193">選択範囲に返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1248d-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="1248d-194">アプリケーションの UI 内にユーザーの選択がない場合は、値が `createDataPackageFromSelection` 返されます `null` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="1248d-195">返されるデータ パッケージに使用可能なプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-196">例</span><span class="sxs-lookup"><span data-stu-id="1248d-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <span data-ttu-id="1248d-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="1248d-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-198">[WinRT StorageFile を標準](/uwp/api/)[の](/uwp/api/windows.storage.storagefile)W3C File オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。</span><span class="sxs-lookup"><span data-stu-id="1248d-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-199">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="1248d-200">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-200">[in]</span></span>
      
      | <span data-ttu-id="1248d-201">型</span><span class="sxs-lookup"><span data-stu-id="1248d-201">Type</span></span> | <span data-ttu-id="1248d-202">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-203">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-203">Any</span></span> | <span data-ttu-id="1248d-204">ストレージ ファイルが保存されています。</span><span class="sxs-lookup"><span data-stu-id="1248d-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-205">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-205">Return value</span></span>**
      
      <span data-ttu-id="1248d-206">なし</span><span class="sxs-lookup"><span data-stu-id="1248d-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-207">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="1248d-208">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-208">Exception</span></span> | <span data-ttu-id="1248d-209">状況</span><span class="sxs-lookup"><span data-stu-id="1248d-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="1248d-210">TypeMismatchError</span></span> | <span data-ttu-id="1248d-211">指定された W3C ファイル参照が無効です。</span><span class="sxs-lookup"><span data-stu-id="1248d-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="1248d-212">Internet Explorer 10 より前のバージョン `TYPE_MISMATCH_ERR` の場合は、返されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-213">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-213">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-214">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-215">例</span><span class="sxs-lookup"><span data-stu-id="1248d-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="1248d-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-217">InputStream [から MSStream](https://msdn.microsoft.com/library/hh772328) を [作成します](https://msdn.microsoft.com/library/hh772327)。</span><span class="sxs-lookup"><span data-stu-id="1248d-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="1248d-219">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-219">[in]</span></span>
      
      | <span data-ttu-id="1248d-220">型</span><span class="sxs-lookup"><span data-stu-id="1248d-220">Type</span></span> | <span data-ttu-id="1248d-221">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-222">DOMString</span></span> | <span data-ttu-id="1248d-223">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="1248d-223">Content type of the data.</span></span>  <span data-ttu-id="1248d-224">この文字列は、RFC 2616 のセクション 3.7 で定義されているメディアタイプ トークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="1248d-225">\([MIME タイプを参照]]( https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) (例: `text/plain` , `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` など\)</span><span class="sxs-lookup"><span data-stu-id="1248d-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="1248d-226">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-226">[in]</span></span>
      
      | <span data-ttu-id="1248d-227">型</span><span class="sxs-lookup"><span data-stu-id="1248d-227">Type</span></span> | <span data-ttu-id="1248d-228">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-229">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-229">Any</span></span> | <span data-ttu-id="1248d-230">に[格納する IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`</span><span class="sxs-lookup"><span data-stu-id="1248d-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-231">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-231">Return value</span></span>**
      
      <span data-ttu-id="1248d-232">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-233">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-233">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-234">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-235">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-235">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-236">このメソッドは、コンテンツ タイプと参照を受け取 `IInputStream` います。</span><span class="sxs-lookup"><span data-stu-id="1248d-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="1248d-237">メソッドは、渡されたストリーム参照が型のインスタンスであり、ない場合はスロー `IInputStream` を検証します `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="1248d-238">エラーが発生しない場合は `createStreamFromInputStream` `MSStream` 、\(入力\ から) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1248d-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-239">例</span><span class="sxs-lookup"><span data-stu-id="1248d-239">Example</span></span>**  
      
      <span data-ttu-id="1248d-240">An `IInputStream` を使用して作成できます `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="1248d-241">本質的に 1 回限り使用されるオブジェクトと同様に、イメージ要素によって初めて解決されると、作成された URL はすべて `MSStreams` `URL.createObjectURL` 取り消されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="1248d-242">さらに、ストリームの使用後にこのオブジェクトの 2 番目の URL を要求すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="1248d-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
      ```javascript
      var inputStream = myInputStream; //get InputStream from socket API, and so on
      var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
      document.getElementById("imagetag").src = URL.createObjectURL(stream); 
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="1248d-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-244">指定された優先順位に従って、後で実行されるコールバックをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="1248d-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="1248d-246">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-246">[in]</span></span>
      
      | <span data-ttu-id="1248d-247">型</span><span class="sxs-lookup"><span data-stu-id="1248d-247">Type</span></span> | <span data-ttu-id="1248d-248">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-249">機能</span><span class="sxs-lookup"><span data-stu-id="1248d-249">Function</span></span> | <span data-ttu-id="1248d-250">指定された優先度でディスパッチされた非同期的に実行するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="1248d-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="1248d-251">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-251">[in]</span></span>
      
      | <span data-ttu-id="1248d-252">型</span><span class="sxs-lookup"><span data-stu-id="1248d-252">Type</span></span> | <span data-ttu-id="1248d-253">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-254">DOMString</span></span> | <span data-ttu-id="1248d-255">asynchronousCallback コールバックが実行されるコンテキスト優先順位の値。</span><span class="sxs-lookup"><span data-stu-id="1248d-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="1248d-256">[MSApp 定数を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="1248d-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="1248d-257">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-257">[in]</span></span>
      
      | <span data-ttu-id="1248d-258">型</span><span class="sxs-lookup"><span data-stu-id="1248d-258">Type</span></span> | <span data-ttu-id="1248d-259">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="1248d-260">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-260">Any</span></span> | <span data-ttu-id="1248d-261">同期Callback コールバック関数 \(パラメーター 1 など\ として渡される、オプションの一連の引数)。</span><span class="sxs-lookup"><span data-stu-id="1248d-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-262">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-262">Return value</span></span>**  
      
      <span data-ttu-id="1248d-263">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-264">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-264">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-265">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-266">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-266">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-267">指定された `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="1248d-268">は、指定された優先度に従ってディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="1248d-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="1248d-269">通常の優先度は、既存の [setImmediate メソッドと同](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) じです。</span><span class="sxs-lookup"><span data-stu-id="1248d-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="1248d-270">コールバックを実行すると、現在のコンテキストの優先度は、コールバックの実行中に指定された優先度パラメーター値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="1248d-271">コールバック `asynchronousCallback` パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1248d-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="1248d-272">パラメーターの後に引数を指定 `priority` すると、引数はすべてコールバック関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="1248d-273">異 `execAtPriority` なり、コールバック関数によって返されるオブジェクト `asynchronousCallback` は無視され\(\経由では返 `execAsyncAtPriority` されません)。</span><span class="sxs-lookup"><span data-stu-id="1248d-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-274">例</span><span class="sxs-lookup"><span data-stu-id="1248d-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="1248d-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-276">指定されたコンテキスト優先順位で指定されたコールバック関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="1248d-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-277">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="1248d-278">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-278">[in]</span></span>  
      
      | <span data-ttu-id="1248d-279">型</span><span class="sxs-lookup"><span data-stu-id="1248d-279">Type</span></span> | <span data-ttu-id="1248d-280">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-281">機能</span><span class="sxs-lookup"><span data-stu-id="1248d-281">Function</span></span> | <span data-ttu-id="1248d-282">指定された優先順位のコンテキスト優先順位で同期的に実行するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="1248d-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="1248d-283">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-283">[in]</span></span>  
      
      | <span data-ttu-id="1248d-284">型</span><span class="sxs-lookup"><span data-stu-id="1248d-284">Type</span></span> | <span data-ttu-id="1248d-285">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-286">DOMString</span></span> | <span data-ttu-id="1248d-287">コールバック関数の実行中に現在のコンテキスト優先順位の値が設定される、指定された優先度 `synchronousCallback` の値。</span><span class="sxs-lookup"><span data-stu-id="1248d-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="1248d-288">[MSApp 定数を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="1248d-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="1248d-289">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-289">[in]</span></span>  
      
      | <span data-ttu-id="1248d-290">型</span><span class="sxs-lookup"><span data-stu-id="1248d-290">Type</span></span> | <span data-ttu-id="1248d-291">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-292">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-292">Any</span></span> | <span data-ttu-id="1248d-293">コールバック関数 \(パラメーター 1 など\ として) に渡される、オプションの一連 `synchronousCallback` の引数。</span><span class="sxs-lookup"><span data-stu-id="1248d-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-294">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-294">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-295">型</span><span class="sxs-lookup"><span data-stu-id="1248d-295">Type</span></span> | <span data-ttu-id="1248d-296">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-297">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-297">Any</span></span> | <span data-ttu-id="1248d-298">コールバック \(該当する場合 `synchronousCallback` \) の戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-299">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-299">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-300">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-301">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-301">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-302">指定された `synchronousCallback` コールバック メソッドは同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="1248d-303">現在のコンテキスト優先度は、指定されたコールバック関数の間、指定された優先度の値 (引数 priority で指定) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="1248d-304">コールバック関数の実行が終了すると、呼び出しの前に優先度が以前の値に返 `execAtPriority` されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="1248d-305">戻り値は `execAtPriority` 、コールバック メソッド \(提供されている\) の戻り値です。</span><span class="sxs-lookup"><span data-stu-id="1248d-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="1248d-306">コールバック `synchronousCallback` パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1248d-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="1248d-307">priority パラメーターの後に引数が指定されている場合は、指定されたコールバック メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="1248d-308">コールバック パラメーターが値を返す場合、この値も戻り `execAtPriority` 値になります。</span><span class="sxs-lookup"><span data-stu-id="1248d-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-309">例</span><span class="sxs-lookup"><span data-stu-id="1248d-309">Example</span></span>**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="1248d-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-311">現在のコンテキストの優先度を返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-312">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-312">Parameters</span></span>**  
      
      <span data-ttu-id="1248d-313">ありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-314">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-314">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-315">型</span><span class="sxs-lookup"><span data-stu-id="1248d-315">Type</span></span> | <span data-ttu-id="1248d-316">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-317">DOMString</span></span> | <span data-ttu-id="1248d-318">戻り値は、文字列 、または `MSApp.HIGH` `MSApp.NORMAL` `MSApp.IDLE` .</span><span class="sxs-lookup"><span data-stu-id="1248d-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-319">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-319">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-320">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-321">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-321">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-322">このメソッドは、現在のコンテキスト優先度 [\(MSApp Constants](#msapp-constants)\を参照) を返します。これは、次の方法で変更 `execAtPriority` できます `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-323">例</span><span class="sxs-lookup"><span data-stu-id="1248d-323">Example</span></span>**  
      
      ```javascript
      if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
          // YOUR CODE HERE
      }
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="1248d-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="1248d-325">廃止された同期 API。</span><span class="sxs-lookup"><span data-stu-id="1248d-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="1248d-326">Windows 10 については、以下を参照してください `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="1248d-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span><span class="sxs-lookup"><span data-stu-id="1248d-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="1248d-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="1248d-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-329">印刷するソース コンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-330">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="1248d-331">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-331">[in]</span></span>  
      
      | <span data-ttu-id="1248d-332">型</span><span class="sxs-lookup"><span data-stu-id="1248d-332">Type</span></span> | <span data-ttu-id="1248d-333">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-334">Document</span><span class="sxs-lookup"><span data-stu-id="1248d-334">Document</span></span> | <span data-ttu-id="1248d-335">印刷する HTML ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1248d-335">The HTML document to be printed.</span></span>  <span data-ttu-id="1248d-336">ルート ドキュメント、iframe 内のドキュメント、ドキュメント フラグメント、SVG ドキュメントなどです。</span><span class="sxs-lookup"><span data-stu-id="1248d-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="1248d-337">htmlDoc は要素ではなくドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-338">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-338">Return value</span></span>**
      
      <span data-ttu-id="1248d-339">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-340">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-340">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-341">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-342">解説</span><span class="sxs-lookup"><span data-stu-id="1248d-342">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-343">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-344">例 1</span><span class="sxs-lookup"><span data-stu-id="1248d-344">Example 1</span></span>**  
      
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
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-345">例 2</span><span class="sxs-lookup"><span data-stu-id="1248d-345">Example 2</span></span>**  
      
      ```javascript
      function registerForPrintContract() {
              var printManager = Windows.Graphics.Printing.PrintManager.getForCurrentView();
              printManager.onprinttaskrequested = onPrintTaskRequested;
              console.log("Print Contract registered.  Use the Print button to print.", "sample", "status");
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
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="1248d-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-347">複数のウィンドウのサポート。</span><span class="sxs-lookup"><span data-stu-id="1248d-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="1248d-348">Win8.1 の JavaScript UWP アプリでは、MSApp DOM API を使用する複数のウィンドウがサポートされました。この API は、現在は使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1248d-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="1248d-349">Windows 10 では、新 `window.open` しい `window` . `MSApp.getViewId`</span><span class="sxs-lookup"><span data-stu-id="1248d-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="1248d-350">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-350">Description</span></span> |<span data-ttu-id="1248d-351">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1248d-351">Windows 10</span></span> | <span data-ttu-id="1248d-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1248d-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="1248d-353">新しいウィンドウを作成する</span><span class="sxs-lookup"><span data-stu-id="1248d-353">Create new window</span></span> | [<span data-ttu-id="1248d-354">window.open</span><span class="sxs-lookup"><span data-stu-id="1248d-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="1248d-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="1248d-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="1248d-356">新しいウィンドウ オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1248d-356">New window object</span></span> | [<span data-ttu-id="1248d-357">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1248d-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="1248d-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="1248d-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-359">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="1248d-360">型</span><span class="sxs-lookup"><span data-stu-id="1248d-360">Type</span></span> | <span data-ttu-id="1248d-361">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-362">DOMString</span></span> | <span data-ttu-id="1248d-363">DOM ドキュメントを含むウィンドウを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1248d-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-364">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="1248d-365">型</span><span class="sxs-lookup"><span data-stu-id="1248d-365">Type</span></span> | <span data-ttu-id="1248d-366">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-367">Number</span><span class="sxs-lookup"><span data-stu-id="1248d-367">Number</span></span> | <span data-ttu-id="1248d-368">さまざまな [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1248d-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-369">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-369">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-370">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-371">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-371">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-372">[window.open と](https://developer.mozilla.org/docs/Web/API/Window/open) [window](https://developer.mozilla.org/docs/Web/API/Window)を使用して新しいウィンドウを作成しますが、WinRT API を操作するには API を追加 `MSApp.getViewId` します。</span><span class="sxs-lookup"><span data-stu-id="1248d-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="1248d-373">オブジェクトをパラメーターとして受け取り、 `window` さまざまな `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="1248d-374">可視性の遅延</span><span class="sxs-lookup"><span data-stu-id="1248d-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="1248d-375">WinRT のビューは通常非表示で開始され、完全に準備が完了すると、エンド開発者はビューを表示する方法 `TryShowAsStandaloneAsync` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1248d-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="1248d-376">Web ワールドでは、ウィンドウがすぐに表示され、エンド ユーザーはコンテンツの読み込みとレンダリング `window.open` を監視できます。</span><span class="sxs-lookup"><span data-stu-id="1248d-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="1248d-377">新しいウィンドウが WinRT のビューのように機能し、すぐに表示されない場合は、オプションを追加 `window.open` しました。</span><span class="sxs-lookup"><span data-stu-id="1248d-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="1248d-378">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="1248d-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="1248d-379">プライマリ ウィンドウの相違点</span><span class="sxs-lookup"><span data-stu-id="1248d-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="1248d-380">OS によって最初に開いたプライマリ ウィンドウの動作は、開いたセカンダリ ウィンドウとは異なります。</span><span class="sxs-lookup"><span data-stu-id="1248d-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="1248d-381">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-381">Description</span></span> | <span data-ttu-id="1248d-382">プライマリ</span><span class="sxs-lookup"><span data-stu-id="1248d-382">Primary</span></span> | <span data-ttu-id="1248d-383">セカンダリ</span><span class="sxs-lookup"><span data-stu-id="1248d-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="1248d-384">window.open</span><span class="sxs-lookup"><span data-stu-id="1248d-384">window.open</span></span> | <span data-ttu-id="1248d-385">許可されます</span><span class="sxs-lookup"><span data-stu-id="1248d-385">Allowed</span></span> | <span data-ttu-id="1248d-386">Disallowed</span><span class="sxs-lookup"><span data-stu-id="1248d-386">Disallowed</span></span> |  
          | <span data-ttu-id="1248d-387">window.close</span><span class="sxs-lookup"><span data-stu-id="1248d-387">window.close</span></span> | <span data-ttu-id="1248d-388">アプリを閉じる</span><span class="sxs-lookup"><span data-stu-id="1248d-388">Close app</span></span> | <span data-ttu-id="1248d-389">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="1248d-389">Close window</span></span> |  
          | <span data-ttu-id="1248d-390">ナビゲーションの制限</span><span class="sxs-lookup"><span data-stu-id="1248d-390">Navigation restrictions</span></span> | <span data-ttu-id="1248d-391">ACUR のみ</span><span class="sxs-lookup"><span data-stu-id="1248d-391">ACUR only</span></span> | <span data-ttu-id="1248d-392">制限なし</span><span class="sxs-lookup"><span data-stu-id="1248d-392">No restrictions</span></span> |  
          
          <span data-ttu-id="1248d-393">セカンダリ ウィンドウを開くことを許可しない制限は、フィードバックに応じて今後変更される可能性 [があります](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。</span><span class="sxs-lookup"><span data-stu-id="1248d-393">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>  
      
      *   <span data-ttu-id="1248d-394">同一発生元の通信制限</span><span class="sxs-lookup"><span data-stu-id="1248d-394">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="1248d-395">技術的に困難な問題が発生し、同期呼び出し、同一元呼び出し、クロス ウィンドウ、スクリプト呼び出しの適切なサポートを妨げている。</span><span class="sxs-lookup"><span data-stu-id="1248d-395">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="1248d-396">同じオリジンのウィンドウを開いた場合、あるウィンドウのスクリプトは他のウィンドウの関数を直接呼び出し、一部の呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1248d-396">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="1248d-397">呼び出しは問題ありませんが、可能であれば実行する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1248d-397">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="1248d-398">この問題の改善作業が進行中です。</span><span class="sxs-lookup"><span data-stu-id="1248d-398">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-399">例</span><span class="sxs-lookup"><span data-stu-id="1248d-399">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <span data-ttu-id="1248d-400">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="1248d-400">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-401">指定された優先度レベル以上の保留中の作業が存在するかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-401">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-402">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-402">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="1248d-403">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-403">[in]</span></span>
      
      | <span data-ttu-id="1248d-404">型</span><span class="sxs-lookup"><span data-stu-id="1248d-404">Type</span></span> | <span data-ttu-id="1248d-405">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-405">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-406">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-406">DOMString</span></span> | <span data-ttu-id="1248d-407">優先度レベル以上を指定する優先度値 [\(MSApp Constants](#msapp-constants)\を参照) を指定して、キューに入った未処理の作業を照会します。</span><span class="sxs-lookup"><span data-stu-id="1248d-407">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-408">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-408">Return value</span></span>**  
      
      | <span data-ttu-id="1248d-409">型</span><span class="sxs-lookup"><span data-stu-id="1248d-409">Type</span></span> | <span data-ttu-id="1248d-410">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-410">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-411">ブール値</span><span class="sxs-lookup"><span data-stu-id="1248d-411">Boolean</span></span> | <span data-ttu-id="1248d-412">指定した優先度レベル以上のキューに入った作業がある場合は、それ以外の場合 `true` に `false` 返します。</span><span class="sxs-lookup"><span data-stu-id="1248d-412">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-413">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-413">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-414">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-414">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-415">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-415">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-416">このメソッドは、呼び出し元の JavaScript コードが優先度の高い作業を得る目的で、さまざまな優先度レベル \(または上記\) で保留中の作業が見られるかどうかを JavaScript コードが判断する手段を提供します。 `isTaskScheduledAtPriorityOrHigher`</span><span class="sxs-lookup"><span data-stu-id="1248d-416">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-417">例</span><span class="sxs-lookup"><span data-stu-id="1248d-417">Example</span></span>**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-418">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="1248d-418">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-419">すべてのアクティブ化イベント \(通知やピン留めされたタイルのクリックなど) の前に、開始パスの更新 (ページの再読み込み) を回避するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-419">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-420">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-420">Parameters</span></span>**  
      
      | <span data-ttu-id="1248d-421">型</span><span class="sxs-lookup"><span data-stu-id="1248d-421">Type</span></span> | <span data-ttu-id="1248d-422">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-422">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-423">ブール値</span><span class="sxs-lookup"><span data-stu-id="1248d-423">Boolean</span></span> | <span data-ttu-id="1248d-424">常に開始パスの更新 (ページの再読み込み) をスキップし、代わりにアクティブ化されたイベントの発生 `MSApp.pageHandlesAllApplicationActivations(true)` に直接 `WebUIApplication` ジャンプするために使用します。</span><span class="sxs-lookup"><span data-stu-id="1248d-424">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="1248d-425">すべてのページでアクティブ化イベントを個別に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-425">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="1248d-426">このメソッドを定義することで、アクティブ化されたイベント `true` \(通知\など) をクリックすると、再読み込みはトリガーされません。これは、ページの再読み込みを回避する単一ページ アプリにとって不可欠です。</span><span class="sxs-lookup"><span data-stu-id="1248d-426">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-427">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-427">Return value</span></span>**
      
      <span data-ttu-id="1248d-428">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-428">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-429">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-429">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-430">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-430">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-431">解説</span><span class="sxs-lookup"><span data-stu-id="1248d-431">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-432">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-432">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-433">例</span><span class="sxs-lookup"><span data-stu-id="1248d-433">Example</span></span>**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-434">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="1248d-434">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-435">リソースのダウンロード中に、アプリが認証プロンプトを抑制するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1248d-435">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-436">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-436">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="1248d-437">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-437">[in]</span></span>
      
      | <span data-ttu-id="1248d-438">型</span><span class="sxs-lookup"><span data-stu-id="1248d-438">Type</span></span> | <span data-ttu-id="1248d-439">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-439">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-440">ブール値</span><span class="sxs-lookup"><span data-stu-id="1248d-440">Boolean</span></span> | <span data-ttu-id="1248d-441">true に設定すると、認証プロンプトが表示される可能性が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-441">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="1248d-442">値 false は、ユーザーからの潜在的な認証プロンプトを抑制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-442">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-443">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-443">Return value</span></span>**  
      
      <span data-ttu-id="1248d-444">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-444">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-445">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-445">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-446">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-446">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-447">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-447">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-448">この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中にアプリが潜在的な認証プロンプトを抑制するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1248d-448">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="1248d-449">既定の動作では、資格情報の入力を抑制しません。</span><span class="sxs-lookup"><span data-stu-id="1248d-449">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="1248d-450">は、メール アプリ \(各画像が認証を必要とする多数の画像を含むニュースレターを含む可能性がある) など、認証を必要とするリソースが過剰に読み込まれる可能性があるアプリで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="1248d-450">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="1248d-451">資格情報の入力を求めるメッセージを表示しない場合、認証を必要とするリソースにアクセスするときにサーバーに認証するためのダイアログは表示されません。また、リソースはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="1248d-451">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="1248d-452">プロキシ認証やクライアント認定要求ダイアログなどの他のプロンプトに影響を与えるのではなく `suppressSubdownloadCredentialPrompts` 、XHR にも影響を与える点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1248d-452">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="1248d-453">要素でホスト `suppressSubdownloadCredentialPrompts` されているコンテンツを含め、アプリケーションのすべてのコンテンツに影響を与える点に注意 `webview` してください。</span><span class="sxs-lookup"><span data-stu-id="1248d-453">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="1248d-454">資格情報プロンプトの決定はキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="1248d-454">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="1248d-455">したがって、資格情報のプロンプトを抑制するとすぐに有効になりますが、表示を抑制した後で資格情報のプロンプトを有効にする場合は、ドキュメントの再読み込みを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1248d-455">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-456">例</span><span class="sxs-lookup"><span data-stu-id="1248d-456">Example</span></span>**  
      
      ```javascript
      // Set to true to suppress potential credential prompts:
      MSApp.suppressSubdownloadCredentialPrompts(true);
      // Now one can load content or navigate iframe/webview to some other site.
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-457">terminateApp</span><span class="sxs-lookup"><span data-stu-id="1248d-457">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-458">現在のアプリケーションを終了し、エラー レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="1248d-458">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-459">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-459">Parameters</span></span>**  
      
      `error` <span data-ttu-id="1248d-460">[in]</span><span class="sxs-lookup"><span data-stu-id="1248d-460">[in]</span></span>
      
      | <span data-ttu-id="1248d-461">型</span><span class="sxs-lookup"><span data-stu-id="1248d-461">Type</span></span> | <span data-ttu-id="1248d-462">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-462">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-463">エラー</span><span class="sxs-lookup"><span data-stu-id="1248d-463">Error</span></span> | <span data-ttu-id="1248d-464">終了 `Error` をトリガーしたエラーを記述するために使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1248d-464">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="1248d-465">オブジェクトには、番号、説明、およびスタックプロパティが含まれている必要があります。オブジェクトにこれらのプロパティが含まれている場合、エラー レポート `Error` は生成されません。</span><span class="sxs-lookup"><span data-stu-id="1248d-465">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-466">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-466">Return value</span></span>**
      
      <span data-ttu-id="1248d-467">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-467">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-468">例外</span><span class="sxs-lookup"><span data-stu-id="1248d-468">Exceptions</span></span>**  
      
      <span data-ttu-id="1248d-469">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-469">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-470">注釈</span><span class="sxs-lookup"><span data-stu-id="1248d-470">Remarks</span></span>**  
      
      <span data-ttu-id="1248d-471">報告された問題がアプリの上位 5 つの問題の 1 つになると、アプリの [品質] ページ `terminateApp` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1248d-471">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-472">例</span><span class="sxs-lookup"><span data-stu-id="1248d-472">Example</span></span>**  
      
      <span data-ttu-id="1248d-473">この例では、 `terminateApp` 例外が発生した場合に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1248d-473">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="1248d-474">例外をキャッチ `Error` するときに指定されたオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="1248d-474">It uses the `Error` object provided when you catch an exception.</span></span>  
      
      ```javascript
      try {  
          var obj2 = null;  
          obj2.val = 5;  
      }  
      catch(e) {  
          window.MSApp.terminateApp(e);  
      }  
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1248d-475">MSApp 定数</span><span class="sxs-lookup"><span data-stu-id="1248d-475">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-476">、、、に関連付けられている許可 `execAsyncAtPriority` `execAtPriority` された優先度 `getCurrentPriority` の値 `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-476">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="1248d-477">現在の顧客</span><span class="sxs-lookup"><span data-stu-id="1248d-477">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="1248d-478">型</span><span class="sxs-lookup"><span data-stu-id="1248d-478">Type</span></span> | <span data-ttu-id="1248d-479">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-479">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-480">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-480">DOMString</span></span> | <span data-ttu-id="1248d-481">適切なメソッド \(See also section\) と一緒に使用すると、メソッドは要求された操作を実行するときに現在のコンテキスト優先順位 `current` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1248d-481">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="1248d-482">高</span><span class="sxs-lookup"><span data-stu-id="1248d-482">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="1248d-483">型</span><span class="sxs-lookup"><span data-stu-id="1248d-483">Type</span></span> | <span data-ttu-id="1248d-484">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-484">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-485">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-485">DOMString</span></span> | <span data-ttu-id="1248d-486">適切 `high` なメソッド \(See also section\) と一緒に使用する場合、メソッドは要求された操作を実行するときに通常より高い優先度を使用し、既存の通常の優先度が動作する前に操作をディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="1248d-486">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="1248d-487">アイドル</span><span class="sxs-lookup"><span data-stu-id="1248d-487">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="1248d-488">型</span><span class="sxs-lookup"><span data-stu-id="1248d-488">Type</span></span> | <span data-ttu-id="1248d-489">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-489">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-490">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-490">DOMString</span></span> | <span data-ttu-id="1248d-491">適切 `ideal` なメソッド \(See also section\) と一緒に使用する場合、メソッドは要求された操作を実行するときに通常より低い優先度を使用し、既存の通常の優先度の処理の後に操作をディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="1248d-491">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="1248d-492">通常</span><span class="sxs-lookup"><span data-stu-id="1248d-492">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="1248d-493">型</span><span class="sxs-lookup"><span data-stu-id="1248d-493">Type</span></span> | <span data-ttu-id="1248d-494">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-494">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-495">DOMString</span><span class="sxs-lookup"><span data-stu-id="1248d-495">DOMString</span></span> | <span data-ttu-id="1248d-496">適切なメソッド (「関連」セクションを参照) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の既存の優先度 `normal` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1248d-496">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-497">例</span><span class="sxs-lookup"><span data-stu-id="1248d-497">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-498">要件</span><span class="sxs-lookup"><span data-stu-id="1248d-498">Requirements</span></span>**  
      
      | <span data-ttu-id="1248d-499">型</span><span class="sxs-lookup"><span data-stu-id="1248d-499">Type</span></span> | <span data-ttu-id="1248d-500">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-500">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-501">IDL</span><span class="sxs-lookup"><span data-stu-id="1248d-501">IDL</span></span> | <span data-ttu-id="1248d-502">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="1248d-502">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="1248d-503">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="1248d-503">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <span data-ttu-id="1248d-504">start</span><span class="sxs-lookup"><span data-stu-id="1248d-504">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1248d-505">を起動 `MSAppAsyncOperation` します。</span><span class="sxs-lookup"><span data-stu-id="1248d-505">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1248d-506">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1248d-506">Parameters</span></span>**  
      
      <span data-ttu-id="1248d-507">ありません。</span><span class="sxs-lookup"><span data-stu-id="1248d-507">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1248d-508">戻り値</span><span class="sxs-lookup"><span data-stu-id="1248d-508">Return value</span></span>**
      
      <span data-ttu-id="1248d-509">なし。</span><span class="sxs-lookup"><span data-stu-id="1248d-509">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="1248d-510">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1248d-510">Properties</span></span>**  
      
      `error` <span data-ttu-id="1248d-511">property</span><span class="sxs-lookup"><span data-stu-id="1248d-511">property</span></span>  
      
      | <span data-ttu-id="1248d-512">型</span><span class="sxs-lookup"><span data-stu-id="1248d-512">Type</span></span> | <span data-ttu-id="1248d-513">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-513">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-514">DOMError</span><span class="sxs-lookup"><span data-stu-id="1248d-514">DOMError</span></span> | <span data-ttu-id="1248d-515">のエラーを表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-515">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="1248d-516">property</span><span class="sxs-lookup"><span data-stu-id="1248d-516">property</span></span>  
      
      | <span data-ttu-id="1248d-517">型</span><span class="sxs-lookup"><span data-stu-id="1248d-517">Type</span></span> | <span data-ttu-id="1248d-518">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-518">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-519">EventHandler</span><span class="sxs-lookup"><span data-stu-id="1248d-519">EventHandler</span></span> | <span data-ttu-id="1248d-520">完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。</span><span class="sxs-lookup"><span data-stu-id="1248d-520">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="1248d-521">property</span><span class="sxs-lookup"><span data-stu-id="1248d-521">property</span></span>  
      
      | <span data-ttu-id="1248d-522">型</span><span class="sxs-lookup"><span data-stu-id="1248d-522">Type</span></span> | <span data-ttu-id="1248d-523">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-523">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-524">EventHandler</span><span class="sxs-lookup"><span data-stu-id="1248d-524">EventHandler</span></span> | <span data-ttu-id="1248d-525">中にエラーが発生した場合にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。</span><span class="sxs-lookup"><span data-stu-id="1248d-525">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="1248d-526">property</span><span class="sxs-lookup"><span data-stu-id="1248d-526">property</span></span>  
      
      | <span data-ttu-id="1248d-527">型</span><span class="sxs-lookup"><span data-stu-id="1248d-527">Type</span></span> | <span data-ttu-id="1248d-528">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-528">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-529">Number</span><span class="sxs-lookup"><span data-stu-id="1248d-529">Number</span></span> | <span data-ttu-id="1248d-530">JavaScript を使用して Windows アプリ内の非同期操作の状態を表します。</span><span class="sxs-lookup"><span data-stu-id="1248d-530">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="1248d-531">値は次のとおりです。 `Started[0]` `Completed[1]` , , `Error[2]` .</span><span class="sxs-lookup"><span data-stu-id="1248d-531">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="1248d-532">property</span><span class="sxs-lookup"><span data-stu-id="1248d-532">property</span></span>  
      
      | <span data-ttu-id="1248d-533">型</span><span class="sxs-lookup"><span data-stu-id="1248d-533">Type</span></span> | <span data-ttu-id="1248d-534">説明</span><span class="sxs-lookup"><span data-stu-id="1248d-534">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1248d-535">任意</span><span class="sxs-lookup"><span data-stu-id="1248d-535">Any</span></span> |<span data-ttu-id="1248d-536">の結果を表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="1248d-536">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
