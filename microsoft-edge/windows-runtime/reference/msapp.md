---
title: MSApp API リファレンス
description: BLOB オブジェクトと MSStream オブジェクトを作成できる、ヘルプアシャー関数を提供します。  MSApp オブジェクトとメンバーは、JavaScript を使用する Windows アプリでサポートされます。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/29/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: マスター、PWA、ファイル アップロード、ブログ、MSStream、Windows 10 アプリ、uwp、Edge
ms.openlocfilehash: 4966f6afbe4e971d6a366de7e9b4f5a6cd2305e0
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942166"
---
# <span data-ttu-id="c0b34-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="c0b34-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="c0b34-106">MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API へのアクセスを含む) を使用する Windows アプリでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="c0b34-107">MSApp オブジェクトは、ms-appx URI スキームを使用して読み込む Windows アプリの HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトが存在しない (メソッドとプロパティは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="c0b34-108">[BLOB](https://developer.mozilla.org/docs/Web/API/Blob)オブジェクトと MSStream オブジェクトを作成できる、ヘルプア[ーカー関数を](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)提供します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="c0b34-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0b34-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c0b34-110">clearTemporaryWebDataAsync、createBlobFromRandomAccessSream、createDataPackage、createDataPackageFromSelection、createFileFromStorageFile、createStreamFromInputStream、execAsyncAtPriority、execAtPriority、getCurrentP [createDataPackage](#createdatapackage) [riority,](#getcurrentpriority) [createDataPackageFromSelection](#createdatapackagefromselection) [getHtmlPrintDocumentSource,](#gethtmlprintdocumentsource)[getHtmlPrintDocumentSourceAsynce,](#gethtmlprintdocumentsourceasync) [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream) [getViewId,](#getviewid) [createFileFromStorageFile](#createfilefromstoragefile) [isTaskScheduledAtPriorityOrHigher,](#istaskscheduledatpriorityorhigher) [pageHandlesAllApplicationActivations,](#pagehandlesallapplicationactivations) [suppressSubdownloadCredentialPrompts,](#suppresssubdownloadcredentialprompts) [terminateApp.](#terminateapp) [clearTemporaryWebDataAsync](#cleartemporarywebdataasync) [createStreamFromInputStream](#createstreamfrominputstream) [execAsyncAtPriority](#execasyncatpriority) [execAtPriority](#execatpriority)</span><span class="sxs-lookup"><span data-stu-id="c0b34-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c0b34-111">定数</span><span class="sxs-lookup"><span data-stu-id="c0b34-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c0b34-112">[現在](#current)、 [高](#high), [アイドル](#idle), [通常](#normal)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c0b34-113">MSAppAsyncOperation インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0b34-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="c0b34-114">start</span><span class="sxs-lookup"><span data-stu-id="c0b34-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="c0b34-115">MSApp のメソッド</span><span class="sxs-lookup"><span data-stu-id="c0b34-115">MSApp methods</span></span>  

### <span data-ttu-id="c0b34-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="c0b34-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-117">アプリまたは WebView のキャッシュおよびインデックス付きDB データ [をクリアします](../../webview.md)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-117">Clears cache and indexedDB data for the app or [WebView](../../webview.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-118">Parameters</span></span>**  
      
      <span data-ttu-id="c0b34-119">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-120">Return value</span></span>**  
      
      <span data-ttu-id="c0b34-121">型: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="c0b34-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="c0b34-122">非同期操作を表します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-123">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-123">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-124">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-125">解説</span><span class="sxs-lookup"><span data-stu-id="c0b34-125">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-126">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-127">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="c0b34-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="c0b34-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-129">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)オブジェクトから[Blob](https://developer.mozilla.org/docs/Web/API/Blob)を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="c0b34-130">ストリームから W3C ベースのオブジェクトを作成するために、アプリ内の `IRandomAccessStream` オブジェクトを操作するときに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="c0b34-131">BLOB が作成されると、そのブローバは[FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/URL)[と一で使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="c0b34-133">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-133">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-134">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-134">Type</span></span> | <span data-ttu-id="c0b34-135">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-136">String</span><span class="sxs-lookup"><span data-stu-id="c0b34-136">String</span></span> | <span data-ttu-id="c0b34-137">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="c0b34-137">Content type of the data.</span></span>  <span data-ttu-id="c0b34-138">この文字列は、RFC 2616 のセクションで定義されるメディア タイプ トークンで指定された形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="c0b34-139">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-139">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-140">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-140">Type</span></span> | <span data-ttu-id="c0b34-141">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-142">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-142">Any</span></span> | <span data-ttu-id="c0b34-143">[Blob に保存する IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="c0b34-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-144">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-144">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-145">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-145">Type</span></span> | <span data-ttu-id="c0b34-146">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-147">Blob</span><span class="sxs-lookup"><span data-stu-id="c0b34-147">Blob</span></span> | <span data-ttu-id="c0b34-148">ストリームが含まれる新しい BLOB オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c0b34-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-149">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="c0b34-150">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-150">Exception</span></span> | <span data-ttu-id="c0b34-151">状況</span><span class="sxs-lookup"><span data-stu-id="c0b34-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="c0b34-152">TypeMismatchError</span></span> | <span data-ttu-id="c0b34-153">ノードの種類は、パラメーターの種類と互換性がない。</span><span class="sxs-lookup"><span data-stu-id="c0b34-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="c0b34-154">10 より前のバージョン Internet Explorerでは、TYPE_MISMATCH_ERRが返されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-155">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-155">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-156">ウィンドウ オブジェクトの MSApp 名前空間を使用して、Windows ランタイム タイプから Blob を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="c0b34-157">このメソッドにより、提供される [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクト上に照明したビット ラッパーであるブローバが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="c0b34-158">BLOB はこのストリームの有効期限を所有し、BLOB がストリーミングされるとストリームが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-159">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-159">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="c0b34-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-161">ユーザーまたはアプリケーションの指定された範囲を HTML フラグメントに変換し、共有できます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="c0b34-163">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-163">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-164">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-164">Type</span></span> | <span data-ttu-id="c0b34-165">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-166">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-166">Any</span></span> | <span data-ttu-id="c0b34-167">この範囲は、選択オブジェクトから作成できます (例: `window.selection.getRangeAt(0)` または手動で作成することもできます)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-168">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-168">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-169">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-169">Type</span></span> | <span data-ttu-id="c0b34-170">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-171">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-171">Any</span></span> | <span data-ttu-id="c0b34-172">指定した範囲の HTML マークアップを含みます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-173">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-173">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-174">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-175">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-175">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-176">このメソッドは[、ドキュメント オブジェクト モデル (DOM) 範囲のみをサポートし、テキスト範囲](https://developer.mozilla.org/docs/Web/API/Range)[にはサポートされません](/uwp/api/windows.ui.xaml.documents.textrange)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="c0b34-177">指定した範囲における返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="c0b34-178">返されるデータ パッケージに利用できるプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-179">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-179">Example</span></span>**  
      
      <span data-ttu-id="c0b34-180">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="c0b34-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="c0b34-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-182">ユーザーまたはアプリケーションの選択範囲を共有できる HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-183">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-183">Parameters</span></span>**  
      
      <span data-ttu-id="c0b34-184">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-185">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-185">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-186">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-186">Type</span></span> | <span data-ttu-id="c0b34-187">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-188">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-188">Any</span></span> | <span data-ttu-id="c0b34-189">指定した範囲の HTML マークアップを含みます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-190">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-190">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-191">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-192">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-192">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-193">選択範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれている。</span><span class="sxs-lookup"><span data-stu-id="c0b34-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="c0b34-194">アプリケーションの UI 内の任意の場所にユーザー選択がない場合は、 `createDataPackageFromSelection` 戻されます `null` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="c0b34-195">返されるデータ パッケージに利用できるプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-196">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <span data-ttu-id="c0b34-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="c0b34-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-198">[WinRT](/uwp/api/)ストレージ[ファイルを標準](/uwp/api/windows.storage.storagefile)の W3C ファイル オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-199">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="c0b34-200">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-200">[in]</span></span>
      
      | <span data-ttu-id="c0b34-201">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-201">Type</span></span> | <span data-ttu-id="c0b34-202">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-203">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-203">Any</span></span> | <span data-ttu-id="c0b34-204">ストレージ ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-205">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-205">Return value</span></span>**
      
      <span data-ttu-id="c0b34-206">なし</span><span class="sxs-lookup"><span data-stu-id="c0b34-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-207">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="c0b34-208">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-208">Exception</span></span> | <span data-ttu-id="c0b34-209">状況</span><span class="sxs-lookup"><span data-stu-id="c0b34-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="c0b34-210">TypeMismatchError</span></span> | <span data-ttu-id="c0b34-211">指定された W3C ファイル参照が無効です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="c0b34-212">Internet Explorer 10 より前のバージョンの場合は `TYPE_MISMATCH_ERR` 、戻されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-213">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-213">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-214">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-215">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="c0b34-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="c0b34-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-217">InputStream [から MSStream](https://msdn.microsoft.com/library/hh772328) を [作成します](https://msdn.microsoft.com/library/hh772327)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="c0b34-219">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-219">[in]</span></span>
      
      | <span data-ttu-id="c0b34-220">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-220">Type</span></span> | <span data-ttu-id="c0b34-221">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-222">DOMString</span></span> | <span data-ttu-id="c0b34-223">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="c0b34-223">Content type of the data.</span></span>  <span data-ttu-id="c0b34-224">この文字列は、RFC 2616 のセクションで定義されるメディア タイプ トークンで指定された形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="c0b34-225">\([MIME の種類を参照]、次のようになります。"、"、"、"、"、"、以下の場合 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` ")</span><span class="sxs-lookup"><span data-stu-id="c0b34-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="c0b34-226">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-226">[in]</span></span>
      
      | <span data-ttu-id="c0b34-227">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-227">Type</span></span> | <span data-ttu-id="c0b34-228">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-229">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-229">Any</span></span> | <span data-ttu-id="c0b34-230">格納[する IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`</span><span class="sxs-lookup"><span data-stu-id="c0b34-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-231">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-231">Return value</span></span>**
      
      <span data-ttu-id="c0b34-232">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-233">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-233">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-234">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-235">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-235">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-236">このメソッドでは、コンテンツ タイプと参照が使用 `IInputStream` されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="c0b34-237">その後、メソッドは、種類のインスタンスであり、スローしている `IInputStream` 場合はスローが行われます `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="c0b34-238">エラーがない場合 `createStreamFromInputStream` は `MSStream` 、\(入力から) \を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-239">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-239">Example</span></span>**  
      
      <span data-ttu-id="c0b34-240">作成 `IInputStream` に使用できます `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="c0b34-241">一時使用オブジェクトは、イメージ要素によって解決されると、その一度に作成されたすべての URI が `MSStreams` `URL.createObjectURL` 消消されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="c0b34-242">さらに、ストリームの使用後に、このオブジェクトに対する 2 番目の URL の要求が失敗します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
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

### <span data-ttu-id="c0b34-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="c0b34-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-244">指定した優先度に従って後で実行されるコールバックをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="c0b34-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="c0b34-246">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-246">[in]</span></span>
      
      | <span data-ttu-id="c0b34-247">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-247">Type</span></span> | <span data-ttu-id="c0b34-248">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-249">機能</span><span class="sxs-lookup"><span data-stu-id="c0b34-249">Function</span></span> | <span data-ttu-id="c0b34-250">非同期で実行するコールバック関数。指定の優先度でディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="c0b34-251">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-251">[in]</span></span>
      
      | <span data-ttu-id="c0b34-252">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-252">Type</span></span> | <span data-ttu-id="c0b34-253">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-254">DOMString</span></span> | <span data-ttu-id="c0b34-255">非同期呼び出しコールバックが実行されるコンテキスト優先順値。</span><span class="sxs-lookup"><span data-stu-id="c0b34-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="c0b34-256">[MSApp 定数を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="c0b34-257">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-257">[in]</span></span>
      
      | <span data-ttu-id="c0b34-258">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-258">Type</span></span> | <span data-ttu-id="c0b34-259">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="c0b34-260">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-260">Any</span></span> | <span data-ttu-id="c0b34-261">同期の Callback コールバック関数 \(パラメーター 1 など) にパラメーター 1 と合わされる、省略可能な一列の引数です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-262">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-262">Return value</span></span>**  
      
      <span data-ttu-id="c0b34-263">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-264">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-264">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-265">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-266">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-266">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-267">提供された `asynchronousCallback` コールバック関数は非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="c0b34-268">指定された優先度に従ってディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="c0b34-269">通常の優先度は既存の設定方法と [同等です](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="c0b34-270">コールバックが実行されると、コールバックの実行中に現在のコンテキスト 優先度が指定された優先度パラメーター値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="c0b34-271">コール `asynchronousCallback` バック パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="c0b34-272">パラメーター後に引数を指定した場合、それらの引数はすべてコールバック `priority` 関数に合わされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="c0b34-273">とは異なり、コールバック関数によって返されるオブジェクトは `execAtPriority` `asynchronousCallback` \(および返されるもの `execAsyncAtPriority` ではない)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-274">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="c0b34-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="c0b34-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-276">指定されたコンテキスト優先度で、指定されたコールバック関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-277">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="c0b34-278">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-278">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-279">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-279">Type</span></span> | <span data-ttu-id="c0b34-280">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-281">機能</span><span class="sxs-lookup"><span data-stu-id="c0b34-281">Function</span></span> | <span data-ttu-id="c0b34-282">指定した優先度のコンテキスト 優先度で同期的に実行するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="c0b34-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="c0b34-283">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-283">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-284">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-284">Type</span></span> | <span data-ttu-id="c0b34-285">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-286">DOMString</span></span> | <span data-ttu-id="c0b34-287">コールバック関数の実行時に現在のコンテキスト優先度値が設定される指定した `synchronousCallback` 優先度値。</span><span class="sxs-lookup"><span data-stu-id="c0b34-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="c0b34-288">[MSApp 定数を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="c0b34-289">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-289">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-290">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-290">Type</span></span> | <span data-ttu-id="c0b34-291">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-292">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-292">Any</span></span> | <span data-ttu-id="c0b34-293">コールバック関数 \(パラメーター 1 など) にパラメーター 1 と計算される省略 `synchronousCallback` 可能な引数のシリーズ。</span><span class="sxs-lookup"><span data-stu-id="c0b34-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-294">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-294">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-295">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-295">Type</span></span> | <span data-ttu-id="c0b34-296">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-297">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-297">Any</span></span> | <span data-ttu-id="c0b34-298">コールバックの戻り `synchronousCallback` 値を返します (省可能な場合\)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-299">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-299">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-300">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-301">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-301">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-302">提供されたコールバック メソッドは `synchronousCallback` 、同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="c0b34-303">現在のコンテキスト優先度は、提供されたコールバック関数の期間における指定された優先度の値 (優先度引数によって指定される) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="c0b34-304">コールバック関数の実行が完了すると、呼び出し前の前の値に優先度が返 `execAtPriority` されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="c0b34-305">戻り値はコールバック メソッド `execAtPriority` \(提供された\) の戻り値です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="c0b34-306">コール `synchronousCallback` バック パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="c0b34-307">優先度パラメーター後に引数が指定される場合、引数は指定されたコールバックメソッドに合格されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="c0b34-308">コールバック パラメーターが値を返すと、この値も戻り値 `execAtPriority` となります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-309">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-309">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="c0b34-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-311">現在のコンテキスト 優先度を返します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-312">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-312">Parameters</span></span>**  
      
      <span data-ttu-id="c0b34-313">ありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-314">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-314">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-315">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-315">Type</span></span> | <span data-ttu-id="c0b34-316">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-317">DOMString</span></span> | <span data-ttu-id="c0b34-318">戻り値は文字列の 1 つ `MSApp.HIGH` 、ついずれ `MSApp.NORMAL` かの文字列、つながりです `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-319">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-319">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-320">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-321">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-321">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-322">このメソッドは、現在のコンテキスト 優先度 [\(MSApp 定数](#msapp-constants)\を参照) を返します。これは、この値は 、または指定して変更 `execAtPriority` できます `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-323">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-323">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="c0b34-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="c0b34-325">廃止された同期 API。</span><span class="sxs-lookup"><span data-stu-id="c0b34-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="c0b34-326">Windows 10 の場合は、参照してください `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="c0b34-327">たとえばWindows 8 8.1 アプリの場合は [、getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b34-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="c0b34-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="c0b34-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-329">印刷されるソース コンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-330">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="c0b34-331">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-331">[in]</span></span>  
      
      | <span data-ttu-id="c0b34-332">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-332">Type</span></span> | <span data-ttu-id="c0b34-333">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-334">Document</span><span class="sxs-lookup"><span data-stu-id="c0b34-334">Document</span></span> | <span data-ttu-id="c0b34-335">印刷する HTML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="c0b34-335">The HTML document to be printed.</span></span>  <span data-ttu-id="c0b34-336">これは、ルート ドキュメント、iframe 内のドキュメント、ドキュメントのフラグメント、または SVG ドキュメントになります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="c0b34-337">htmlDoc は要素でなくドキュメントである必要があることにごご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c0b34-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-338">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-338">Return value</span></span>**
      
      <span data-ttu-id="c0b34-339">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-340">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-340">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-341">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-342">解説</span><span class="sxs-lookup"><span data-stu-id="c0b34-342">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-343">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-344">例 1</span><span class="sxs-lookup"><span data-stu-id="c0b34-344">Example 1</span></span>**  
      
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
      **<span data-ttu-id="c0b34-345">例 2</span><span class="sxs-lookup"><span data-stu-id="c0b34-345">Example 2</span></span>**  
      
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

### <span data-ttu-id="c0b34-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="c0b34-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-347">複数のウィンドウのサポート。</span><span class="sxs-lookup"><span data-stu-id="c0b34-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="c0b34-348">Win8.1 JavaScript UWP アプリでは、MSApp DOM API を使用して複数のウィンドウがサポートされています。これは、詳細になりました。</span><span class="sxs-lookup"><span data-stu-id="c0b34-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="c0b34-349">Windows 10 の場合は、使用 `window.open` `window` 、新しいバージョンを使用します `MSApp.getViewId` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="c0b34-350">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-350">Description</span></span> |<span data-ttu-id="c0b34-351">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c0b34-351">Windows 10</span></span> | <span data-ttu-id="c0b34-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c0b34-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="c0b34-353">[新しいウィンドウの作成]</span><span class="sxs-lookup"><span data-stu-id="c0b34-353">Create new window</span></span> | [<span data-ttu-id="c0b34-354">window.open</span><span class="sxs-lookup"><span data-stu-id="c0b34-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="c0b34-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="c0b34-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="c0b34-356">新しいウィンドウ オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c0b34-356">New window object</span></span> | [<span data-ttu-id="c0b34-357">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c0b34-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="c0b34-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="c0b34-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-359">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="c0b34-360">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-360">Type</span></span> | <span data-ttu-id="c0b34-361">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-362">DOMString</span></span> | <span data-ttu-id="c0b34-363">DOM ドキュメントを含むウィンドウを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c0b34-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-364">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="c0b34-365">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-365">Type</span></span> | <span data-ttu-id="c0b34-366">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-367">Number</span><span class="sxs-lookup"><span data-stu-id="c0b34-367">Number</span></span> | <span data-ttu-id="c0b34-368">[さまざまな Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-369">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-369">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-370">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-371">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-371">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-372">[window.open](https://developer.mozilla.org/docs/Web/API/Window/open)と[ウィンドウを使用](https://developer.mozilla.org/docs/Web/API/Window)して新しいウィンドウを作成しますが、WinRT API を操作するには `MSApp.getViewId` 、API を追加します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="c0b34-373">オブジェクトをパラ `window` メーターとして受け返し、 `viewId` さまざまな [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="c0b34-374">[Visibility] (Visibility)</span><span class="sxs-lookup"><span data-stu-id="c0b34-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="c0b34-375">WinRT でのビューは通常どおり非表示に開始され、エンドデベロッパーは何かを使用してビューを完全に準備したとき `TryShowAsStandaloneAsync` などを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="c0b34-376">Web のワールドでは、ウィンドウがすぐに表示され、コンテンツが読み込みおよびレンダリングされるとエンド ユーザー `window.open` が見ることができます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="c0b34-377">新しいウィンドウが WinRT のビューのような機能に機能し、直ちに表示されないようにするには、次のオプションが追加 `window.open` されています。</span><span class="sxs-lookup"><span data-stu-id="c0b34-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="c0b34-378">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="c0b34-379">プライマリ ウィンドウの違い</span><span class="sxs-lookup"><span data-stu-id="c0b34-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="c0b34-380">OS でまず開かれるプライマリ ウィンドウは、第 2 のウィンドウとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="c0b34-381">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-381">Description</span></span> | <span data-ttu-id="c0b34-382">プライマリ</span><span class="sxs-lookup"><span data-stu-id="c0b34-382">Primary</span></span> | <span data-ttu-id="c0b34-383">セカンダリ</span><span class="sxs-lookup"><span data-stu-id="c0b34-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="c0b34-384">window.open</span><span class="sxs-lookup"><span data-stu-id="c0b34-384">window.open</span></span> | <span data-ttu-id="c0b34-385">許可されます</span><span class="sxs-lookup"><span data-stu-id="c0b34-385">Allowed</span></span> | <span data-ttu-id="c0b34-386">Disallowed</span><span class="sxs-lookup"><span data-stu-id="c0b34-386">Disallowed</span></span> |  
          | <span data-ttu-id="c0b34-387">window.close</span><span class="sxs-lookup"><span data-stu-id="c0b34-387">window.close</span></span> | <span data-ttu-id="c0b34-388">アプリを閉じる</span><span class="sxs-lookup"><span data-stu-id="c0b34-388">Close app</span></span> | <span data-ttu-id="c0b34-389">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="c0b34-389">Close window</span></span> |  
          | <span data-ttu-id="c0b34-390">ナビゲーションの制限</span><span class="sxs-lookup"><span data-stu-id="c0b34-390">Navigation restrictions</span></span> | <span data-ttu-id="c0b34-391">ACUR のみ</span><span class="sxs-lookup"><span data-stu-id="c0b34-391">ACUR only</span></span> | <span data-ttu-id="c0b34-392">制限なし</span><span class="sxs-lookup"><span data-stu-id="c0b34-392">No restrictions</span></span> |  
          
          <span data-ttu-id="c0b34-393">セカンダリ ウィンドウを開くことを許可しない制限は、フィードバックに応じて、以降で変わる [可能性があります](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-393">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>  
      
      *   <span data-ttu-id="c0b34-394">同じ Origin Communication の制限</span><span class="sxs-lookup"><span data-stu-id="c0b34-394">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="c0b34-395">同期、同じ場所、クロスクリプト通話に関して、同期に問題がある可能性のあるテクニカルサポートが発生します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-395">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="c0b34-396">同じ発信先のウィンドウを開くと、一度のウィンドウでスクリプトを使用すると、他のウィンドウで関数を直接呼び出すことができます。それらの呼び出しの一部は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-396">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="c0b34-397">通話は最も有効であり、可能な場合に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-397">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="c0b34-398">この問題を改善する作業は進行中です。</span><span class="sxs-lookup"><span data-stu-id="c0b34-398">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-399">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-399">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <span data-ttu-id="c0b34-400">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="c0b34-400">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-401">指定した優先度レベルまたはそれ以降に保留中の作業があるかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-401">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-402">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-402">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="c0b34-403">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-403">[in]</span></span>
      
      | <span data-ttu-id="c0b34-404">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-404">Type</span></span> | <span data-ttu-id="c0b34-405">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-405">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-406">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-406">DOMString</span></span> | <span data-ttu-id="c0b34-407">優先度レベルおよび上位レベルと上位のキューに対するクエリをクエリする優先度の値 [\(MSApp 定](#msapp-constants)数 \)</span><span class="sxs-lookup"><span data-stu-id="c0b34-407">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-408">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-408">Return value</span></span>**  
      
      | <span data-ttu-id="c0b34-409">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-409">Type</span></span> | <span data-ttu-id="c0b34-410">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-410">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-411">ブール値</span><span class="sxs-lookup"><span data-stu-id="c0b34-411">Boolean</span></span> | <span data-ttu-id="c0b34-412">指定された優先度レベルまたは上のキューに入れた作業があるかどうか `true` を `false` 返します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-412">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-413">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-413">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-414">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-414">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-415">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-415">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-416">この `isTaskScheduledAtPriorityOrHigher` メソッドは、JavaScript コードの呼び出しにおけるさまざまな優先度レベル \(または上\) で作業が保留中であるかどうかを判定するためのメーリングを提供します。これにより、JavaScript コードを呼び出す可能性があるため、より優先度の高い作業に対して黄色の作業を決定できます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-416">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-417">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-417">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-418">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="c0b34-418">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-419">アクティブなイベント \(通知をクリックしたり、ピンンなタイルをクリックするなど) の前にスタート パス (ページの再読み込み) を回避するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-419">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-420">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-420">Parameters</span></span>**  
      
      | <span data-ttu-id="c0b34-421">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-421">Type</span></span> | <span data-ttu-id="c0b34-422">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-422">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-423">ブール値</span><span class="sxs-lookup"><span data-stu-id="c0b34-423">Boolean</span></span> | <span data-ttu-id="c0b34-424">常に開始パス (ページの再読み込み) をスキップし、代わりにそのジャンプしてアクティブなイベントを `MSApp.pageHandlesAllApplicationActivations(true)` `WebUIApplication` 実行するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-424">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="c0b34-425">すべてのページでライセンス認証イベントを個別にハンドルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-425">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="c0b34-426">この方法を定義することで、アクティブなイベント \(notification\など) をクリックしても再読み込みがトリロードされることはありません。ページの再読み込みを回避するため、単一ページアプリに対して必要 `true` なものは発生しません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-426">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-427">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-427">Return value</span></span>**
      
      <span data-ttu-id="c0b34-428">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-428">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-429">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-429">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-430">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-430">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-431">解説</span><span class="sxs-lookup"><span data-stu-id="c0b34-431">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-432">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-432">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-433">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-433">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-434">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="c0b34-434">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-435">リソースのダウンロード中に考えられる認証プロンプトがアプリで表示されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-435">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-436">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-436">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="c0b34-437">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-437">[in]</span></span>
      
      | <span data-ttu-id="c0b34-438">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-438">Type</span></span> | <span data-ttu-id="c0b34-439">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-439">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-440">ブール値</span><span class="sxs-lookup"><span data-stu-id="c0b34-440">Boolean</span></span> | <span data-ttu-id="c0b34-441">true の値が表示を指定すると、認証のプロンプトが表示されません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-441">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="c0b34-442">False の値は、ユーザーからの認証プロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-442">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-443">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-443">Return value</span></span>**  
      
      <span data-ttu-id="c0b34-444">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-444">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-445">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-445">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-446">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-446">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-447">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-447">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-448">このメソッドは、リソースのダウンロード時に認証プロンプトが表示を表示するかどうか `suppressSubdownloadCredentialPrompts` を制御します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-448">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="c0b34-449">既定の動作では、資格情報のプロンプトを表示しないことです。</span><span class="sxs-lookup"><span data-stu-id="c0b34-449">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="c0b34-450">は、アプリによって使用を行う場合の目的で、認証が必要な多数のリソース (メール アプリ \(この中にそれぞれ認証が必要な多数の画像を含むニュースレターが含まれている可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c0b34-450">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="c0b34-451">資格情報の確認を表示しないと、認証が必要なリソースにアクセスするときにサーバーに認証するためのダイアログが表示されず、リソースはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-451">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="c0b34-452">プロキシ認証やクライアントサーティフェイス要求のダイアログなど、考えられる他のプロンプトには影響しません `suppressSubdownloadCredentialPrompts` 。また、XHR に影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-452">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="c0b34-453">要素でホストされているコンテンツを含め、アプリケーションの `suppressSubdownloadCredentialPrompts` すべてのコンテンツに影響することにおおよできません `webview` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-453">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="c0b34-454">資格情報プロンプトの決定がキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-454">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="c0b34-455">そのため、資格情報プロンプトをいつでもたちに有効にし、そのまま使用するには、ドキュメントの再読み込みが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0b34-455">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-456">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-456">Example</span></span>**  
      
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

### <span data-ttu-id="c0b34-457">terminateApp</span><span class="sxs-lookup"><span data-stu-id="c0b34-457">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-458">現在のアプリケーションを終了し、エラー レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-458">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-459">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-459">Parameters</span></span>**  
      
      `error` <span data-ttu-id="c0b34-460">[in]</span><span class="sxs-lookup"><span data-stu-id="c0b34-460">[in]</span></span>
      
      | <span data-ttu-id="c0b34-461">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-461">Type</span></span> | <span data-ttu-id="c0b34-462">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-462">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-463">エラー</span><span class="sxs-lookup"><span data-stu-id="c0b34-463">Error</span></span> | <span data-ttu-id="c0b34-464">終了したエラーを説明するの `Error` に使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c0b34-464">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="c0b34-465">オブジェクトには、数値、説明、およびスタック プロパティを含める必要があります。エラー レポートは、オブジェクトにこれらのプロパティが含まれていない場合 `Error` は生きません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-465">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-466">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-466">Return value</span></span>**
      
      <span data-ttu-id="c0b34-467">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-467">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-468">例外</span><span class="sxs-lookup"><span data-stu-id="c0b34-468">Exceptions</span></span>**  
      
      <span data-ttu-id="c0b34-469">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-469">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-470">注釈</span><span class="sxs-lookup"><span data-stu-id="c0b34-470">Remarks</span></span>**  
      
      <span data-ttu-id="c0b34-471">アプリの品質が上位 5 の問題の 1 つになった場合は、アプリの品質 `terminateApp` ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-471">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-472">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-472">Example</span></span>**  
      
      <span data-ttu-id="c0b34-473">この例では、 `terminateApp` 例外が発生した場合の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="c0b34-473">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="c0b34-474">例外 `Error` をキャッチすると、指定したオブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-474">It uses the `Error` object provided when you catch an exception.</span></span>  
      
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

### <span data-ttu-id="c0b34-475">MSApp 定数</span><span class="sxs-lookup"><span data-stu-id="c0b34-475">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-476">ユーザー、および関連付けられている `execAsyncAtPriority` 優先度 `execAtPriority` の値 `getCurrentPriority` 。 `isTaskScheduldAtPriorityOrHigher`</span><span class="sxs-lookup"><span data-stu-id="c0b34-476">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="c0b34-477">現在の顧客</span><span class="sxs-lookup"><span data-stu-id="c0b34-477">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="c0b34-478">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-478">Type</span></span> | <span data-ttu-id="c0b34-479">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-479">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-480">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-480">DOMString</span></span> | <span data-ttu-id="c0b34-481">適切な方法 \(セクション\) と一時に使用するとき、要求された操作を実行するときに、そのメソッドは現在のコンテキスト優先度 `current` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-481">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="c0b34-482">高</span><span class="sxs-lookup"><span data-stu-id="c0b34-482">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="c0b34-483">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-483">Type</span></span> | <span data-ttu-id="c0b34-484">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-484">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-485">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-485">DOMString</span></span> | <span data-ttu-id="c0b34-486">適切な方法 \(セクション\) と一時に使用するとき、要求された操作を実行するときにこのメソッドは通常よりも高い優先度を使用し、既存の通常の優先度の処理が発生する前に操作を `high` ディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="c0b34-486">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="c0b34-487">アイドル</span><span class="sxs-lookup"><span data-stu-id="c0b34-487">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="c0b34-488">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-488">Type</span></span> | <span data-ttu-id="c0b34-489">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-489">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-490">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-490">DOMString</span></span> | <span data-ttu-id="c0b34-491">適切な方法 \(Section\) と一時に使用するとき、要求された操作を実行するときにメソッドは通常よりも低いものを使用し、既存の通常の優先度の作業が完了した後、操作はディスパッ `ideal` チされます。</span><span class="sxs-lookup"><span data-stu-id="c0b34-491">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="c0b34-492">通常</span><span class="sxs-lookup"><span data-stu-id="c0b34-492">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="c0b34-493">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-493">Type</span></span> | <span data-ttu-id="c0b34-494">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-494">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-495">DOMString</span><span class="sxs-lookup"><span data-stu-id="c0b34-495">DOMString</span></span> | <span data-ttu-id="c0b34-496">適切な方法 (セクションを参照) と一時的に使用するとき、要求された操作を実行するときに、このメソッドは通常の優先度 `normal` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-496">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-497">例</span><span class="sxs-lookup"><span data-stu-id="c0b34-497">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-498">要件</span><span class="sxs-lookup"><span data-stu-id="c0b34-498">Requirements</span></span>**  
      
      | <span data-ttu-id="c0b34-499">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-499">Type</span></span> | <span data-ttu-id="c0b34-500">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-500">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-501">IDL</span><span class="sxs-lookup"><span data-stu-id="c0b34-501">IDL</span></span> | <span data-ttu-id="c0b34-502">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="c0b34-502">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="c0b34-503">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="c0b34-503">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <span data-ttu-id="c0b34-504">start</span><span class="sxs-lookup"><span data-stu-id="c0b34-504">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0b34-505">開始します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-505">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="c0b34-506">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0b34-506">Parameters</span></span>**  
      
      <span data-ttu-id="c0b34-507">ありません。</span><span class="sxs-lookup"><span data-stu-id="c0b34-507">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="c0b34-508">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0b34-508">Return value</span></span>**
      
      <span data-ttu-id="c0b34-509">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b34-509">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="c0b34-510">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-510">Properties</span></span>**  
      
      `error` <span data-ttu-id="c0b34-511">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-511">property</span></span>  
      
      | <span data-ttu-id="c0b34-512">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-512">Type</span></span> | <span data-ttu-id="c0b34-513">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-513">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-514">DOMError</span><span class="sxs-lookup"><span data-stu-id="c0b34-514">DOMError</span></span> | <span data-ttu-id="c0b34-515">エラーを表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-515">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="c0b34-516">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-516">property</span></span>  
      
      | <span data-ttu-id="c0b34-517">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-517">Type</span></span> | <span data-ttu-id="c0b34-518">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-518">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-519">EventHandler</span><span class="sxs-lookup"><span data-stu-id="c0b34-519">EventHandler</span></span> | <span data-ttu-id="c0b34-520">完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-520">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="c0b34-521">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-521">property</span></span>  
      
      | <span data-ttu-id="c0b34-522">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-522">Type</span></span> | <span data-ttu-id="c0b34-523">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-523">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-524">EventHandler</span><span class="sxs-lookup"><span data-stu-id="c0b34-524">EventHandler</span></span> | <span data-ttu-id="c0b34-525">エラー時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-525">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="c0b34-526">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-526">property</span></span>  
      
      | <span data-ttu-id="c0b34-527">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-527">Type</span></span> | <span data-ttu-id="c0b34-528">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-528">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-529">Number</span><span class="sxs-lookup"><span data-stu-id="c0b34-529">Number</span></span> | <span data-ttu-id="c0b34-530">JavaScript を使用する Windows アプリでの非同期操作の状態を表します。</span><span class="sxs-lookup"><span data-stu-id="c0b34-530">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="c0b34-531">値には `Started[0]` 、、, `Completed[1]` , `Error[2]` .</span><span class="sxs-lookup"><span data-stu-id="c0b34-531">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="c0b34-532">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c0b34-532">property</span></span>  
      
      | <span data-ttu-id="c0b34-533">型</span><span class="sxs-lookup"><span data-stu-id="c0b34-533">Type</span></span> | <span data-ttu-id="c0b34-534">説明</span><span class="sxs-lookup"><span data-stu-id="c0b34-534">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="c0b34-535">任意</span><span class="sxs-lookup"><span data-stu-id="c0b34-535">Any</span></span> |<span data-ttu-id="c0b34-536">結果を表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="c0b34-536">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
