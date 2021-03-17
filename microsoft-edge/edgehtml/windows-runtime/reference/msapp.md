---
title: MSApp API リファレンス
description: Blob オブジェクトと MSStream オブジェクトを作成できるヘルパー関数を提供します。  JavaScript を使用する Windows アプリでは、MSApp オブジェクトとメンバーがサポートされています。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp、PWA、ファイルアップロード、ブログ、MSStream、Windows 10 アプリ、UWP、エッジ
ms.date: 03/16/2021
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0607929971b1dd2956571304230f69f756497e32
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439725"
---
# <a name="msapp"></a><span data-ttu-id="1e365-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="1e365-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="1e365-106">MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API 機能にアクセスする PWA を含む)を使用する Windows アプリでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1e365-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="1e365-107">MSApp オブジェクトは、ms-appx URI スキームを介して読み込まれた Windows アプリ内の HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (したがって、そのメソッドとプロパティは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="1e365-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="1e365-108">Blob オブジェクトと MSStream オブジェクトを作成できる[ヘルパー](https://developer.mozilla.org/docs/Web/API/Blob)[関数を提供](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="1e365-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="1e365-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e365-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1e365-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPri](#getcurrentpriority) [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span><span class="sxs-lookup"><span data-stu-id="1e365-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1e365-111">定数</span><span class="sxs-lookup"><span data-stu-id="1e365-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1e365-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span><span class="sxs-lookup"><span data-stu-id="1e365-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1e365-113">MSAppAsyncOperation インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e365-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="1e365-114">start</span><span class="sxs-lookup"><span data-stu-id="1e365-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <a name="msapp-methods"></a><span data-ttu-id="1e365-115">MSApp メソッド</span><span class="sxs-lookup"><span data-stu-id="1e365-115">MSApp methods</span></span>  

### <a name="cleartemporarywebdataasync"></a><span data-ttu-id="1e365-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="1e365-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-117">アプリまたは WebView のキャッシュとインデックス付きDB データを [クリアします](../../hosting/webview/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1e365-117">Clears cache and indexedDB data for the app or [WebView](../../hosting/webview/index.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-118">Parameters</span></span>**  
      
      <span data-ttu-id="1e365-119">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-120">Return value</span></span>**  
      
      <span data-ttu-id="1e365-121">型: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="1e365-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="1e365-122">非同期アクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1e365-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-123">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-123">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-124">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-125">解説</span><span class="sxs-lookup"><span data-stu-id="1e365-125">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-126">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-127">例</span><span class="sxs-lookup"><span data-stu-id="1e365-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createblobfromrandomaccessstream"></a><span data-ttu-id="1e365-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="1e365-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-129">[IRandomAccessStream オブジェクトから BLOB を作成](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)します。 [](https://developer.mozilla.org/docs/Web/API/Blob)</span><span class="sxs-lookup"><span data-stu-id="1e365-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="1e365-130">このメソッドは、ストリームから W3C ベースのオブジェクトを作成するために、アプリ内のオブジェクトを処理 `IRandomAccessStream` するときに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="1e365-131">BLOB が作成されると [、FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、および](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest と一緒に使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="1e365-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="1e365-133">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-133">[in]</span></span>  
      
      | <span data-ttu-id="1e365-134">型</span><span class="sxs-lookup"><span data-stu-id="1e365-134">Type</span></span> | <span data-ttu-id="1e365-135">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-136">String</span><span class="sxs-lookup"><span data-stu-id="1e365-136">String</span></span> | <span data-ttu-id="1e365-137">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="1e365-137">Content type of the data.</span></span>  <span data-ttu-id="1e365-138">この文字列は、RFC 2616 のセクション 3.7 で定義されているメディア型トークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="1e365-139">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-139">[in]</span></span>  
      
      | <span data-ttu-id="1e365-140">型</span><span class="sxs-lookup"><span data-stu-id="1e365-140">Type</span></span> | <span data-ttu-id="1e365-141">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-142">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-142">Any</span></span> | <span data-ttu-id="1e365-143">[BLOB に格納する IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="1e365-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-144">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-144">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-145">型</span><span class="sxs-lookup"><span data-stu-id="1e365-145">Type</span></span> | <span data-ttu-id="1e365-146">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-147">BLOB</span><span class="sxs-lookup"><span data-stu-id="1e365-147">Blob</span></span> | <span data-ttu-id="1e365-148">ストリームを含む新しい BLOB オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e365-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-149">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="1e365-150">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-150">Exception</span></span> | <span data-ttu-id="1e365-151">状況</span><span class="sxs-lookup"><span data-stu-id="1e365-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="1e365-152">TypeMismatchError</span></span> | <span data-ttu-id="1e365-153">ノードの種類は、予期されるパラメーターの種類と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="1e365-154">10 より前のInternet Explorerでは、TYPE_MISMATCH_ERRが返されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-155">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-155">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-156">Windows ランタイムの型から、ウィンドウ オブジェクトの MSApp 名前空間を介して BLOB を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e365-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="1e365-157">このメソッドは、基本的に、提供された [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクトの光ラッパーである BLOB を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e365-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="1e365-158">BLOB はこのストリームの有効期間を所有し、BLOB が破棄されるとストリームは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="1e365-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-159">例</span><span class="sxs-lookup"><span data-stu-id="1e365-159">Example</span></span>**  
      
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

### <a name="createdatapackage"></a><span data-ttu-id="1e365-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="1e365-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-161">ユーザーまたはアプリケーションの指定した範囲を、共有できる HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="1e365-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="1e365-163">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-163">[in]</span></span>  
      
      | <span data-ttu-id="1e365-164">型</span><span class="sxs-lookup"><span data-stu-id="1e365-164">Type</span></span> | <span data-ttu-id="1e365-165">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-166">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-166">Any</span></span> | <span data-ttu-id="1e365-167">この範囲は、選択オブジェクト (たとえば、手動) `window.selection.getRangeAt(0)` から作成できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-168">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-168">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-169">型</span><span class="sxs-lookup"><span data-stu-id="1e365-169">Type</span></span> | <span data-ttu-id="1e365-170">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-171">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-171">Any</span></span> | <span data-ttu-id="1e365-172">指定した範囲の HTML マークアップを格納します。</span><span class="sxs-lookup"><span data-stu-id="1e365-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-173">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-173">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-174">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-175">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-175">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-176">このメソッドは[、TextRange ではなく、Document オブジェクト モデル (DOM) 範囲](https://developer.mozilla.org/docs/Web/API/Range)[のみをサポートします](/uwp/api/windows.ui.xaml.documents.textrange)。</span><span class="sxs-lookup"><span data-stu-id="1e365-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="1e365-177">指定した範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e365-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="1e365-178">返されるデータ パッケージに使用可能なプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-179">例</span><span class="sxs-lookup"><span data-stu-id="1e365-179">Example</span></span>**  
      
      <span data-ttu-id="1e365-180">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createdatapackagefromselection"></a><span data-ttu-id="1e365-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="1e365-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-182">ユーザーまたはアプリケーションの選択を、共有できる HTML フラグメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="1e365-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-183">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-183">Parameters</span></span>**  
      
      <span data-ttu-id="1e365-184">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-185">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-185">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-186">型</span><span class="sxs-lookup"><span data-stu-id="1e365-186">Type</span></span> | <span data-ttu-id="1e365-187">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-188">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-188">Any</span></span> | <span data-ttu-id="1e365-189">指定した範囲の HTML マークアップを格納します。</span><span class="sxs-lookup"><span data-stu-id="1e365-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-190">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-190">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-191">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-192">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-192">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-193">選択範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e365-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="1e365-194">アプリケーションの UI 内の任意の場所にユーザーの選択がない場合は、 を `createDataPackageFromSelection` 返します `null` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="1e365-195">返されるデータ パッケージに使用可能なプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-196">例</span><span class="sxs-lookup"><span data-stu-id="1e365-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <a name="createfilefromstoragefile"></a><span data-ttu-id="1e365-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="1e365-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-198">[WinRT StorageFile を](/uwp/api/)[標準の](/uwp/api/windows.storage.storagefile)W3C File オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。</span><span class="sxs-lookup"><span data-stu-id="1e365-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-199">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="1e365-200">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-200">[in]</span></span>
      
      | <span data-ttu-id="1e365-201">型</span><span class="sxs-lookup"><span data-stu-id="1e365-201">Type</span></span> | <span data-ttu-id="1e365-202">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-203">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-203">Any</span></span> | <span data-ttu-id="1e365-204">ストレージ ファイルが含まれる。</span><span class="sxs-lookup"><span data-stu-id="1e365-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-205">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-205">Return value</span></span>**
      
      <span data-ttu-id="1e365-206">なし</span><span class="sxs-lookup"><span data-stu-id="1e365-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-207">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="1e365-208">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-208">Exception</span></span> | <span data-ttu-id="1e365-209">状況</span><span class="sxs-lookup"><span data-stu-id="1e365-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="1e365-210">TypeMismatchError</span></span> | <span data-ttu-id="1e365-211">指定した W3C ファイル参照が無効です。</span><span class="sxs-lookup"><span data-stu-id="1e365-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="1e365-212">10 より前のInternet Explorerの場合 `TYPE_MISMATCH_ERR` は、返されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-213">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-213">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-214">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-215">例</span><span class="sxs-lookup"><span data-stu-id="1e365-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createstreamfrominputstream"></a><span data-ttu-id="1e365-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="1e365-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-217">InputStream [から MSStream](https://msdn.microsoft.com/library/hh772328) を [作成します](https://msdn.microsoft.com/library/hh772327)。</span><span class="sxs-lookup"><span data-stu-id="1e365-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="1e365-219">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-219">[in]</span></span>
      
      | <span data-ttu-id="1e365-220">型</span><span class="sxs-lookup"><span data-stu-id="1e365-220">Type</span></span> | <span data-ttu-id="1e365-221">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-222">DOMString</span></span> | <span data-ttu-id="1e365-223">データのコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="1e365-223">Content type of the data.</span></span>  <span data-ttu-id="1e365-224">この文字列は、RFC 2616 のセクション 3.7 で定義されているメディア型トークンで指定された形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="1e365-225">\([MIME の種類を参照してください https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` ]、、など `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` \)。</span><span class="sxs-lookup"><span data-stu-id="1e365-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="1e365-226">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-226">[in]</span></span>
      
      | <span data-ttu-id="1e365-227">型</span><span class="sxs-lookup"><span data-stu-id="1e365-227">Type</span></span> | <span data-ttu-id="1e365-228">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-229">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-229">Any</span></span> | <span data-ttu-id="1e365-230">に[格納する IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`</span><span class="sxs-lookup"><span data-stu-id="1e365-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-231">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-231">Return value</span></span>**
      
      <span data-ttu-id="1e365-232">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-233">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-233">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-234">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-235">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-235">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-236">このメソッドは、コンテンツ タイプと参照を受け取 `IInputStream` る。</span><span class="sxs-lookup"><span data-stu-id="1e365-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="1e365-237">次に、メソッドは、渡されたストリーム参照が型のインスタンスであり、それではない場合は、 `IInputStream` をスローします `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="1e365-238">エラーが発生しない場合は `createStreamFromInputStream` `MSStream` 、\(その入力\から) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1e365-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-239">例</span><span class="sxs-lookup"><span data-stu-id="1e365-239">Example</span></span>**  
      
      <span data-ttu-id="1e365-240">An `IInputStream` を使用して、 を作成できます `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="1e365-241">本質的に 1 回限り使用されるオブジェクトと同様に、image 要素によって最初に解決されると、作成された URL はすべて `MSStreams` `URL.createObjectURL` 取り消されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="1e365-242">さらに、ストリームの使用後にこのオブジェクトの 2 番目の URL の要求は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1e365-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
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

### <a name="execasyncatpriority"></a><span data-ttu-id="1e365-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="1e365-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-244">指定された優先度に従って、後で実行されるコールバックをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="1e365-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-245">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="1e365-246">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-246">[in]</span></span>
      
      | <span data-ttu-id="1e365-247">型</span><span class="sxs-lookup"><span data-stu-id="1e365-247">Type</span></span> | <span data-ttu-id="1e365-248">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-249">機能</span><span class="sxs-lookup"><span data-stu-id="1e365-249">Function</span></span> | <span data-ttu-id="1e365-250">指定された優先度でディスパッチされた非同期的に実行するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="1e365-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="1e365-251">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-251">[in]</span></span>
      
      | <span data-ttu-id="1e365-252">型</span><span class="sxs-lookup"><span data-stu-id="1e365-252">Type</span></span> | <span data-ttu-id="1e365-253">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-254">DOMString</span></span> | <span data-ttu-id="1e365-255">非同期Callback コールバックが実行されるコンテキスト優先度の値。</span><span class="sxs-lookup"><span data-stu-id="1e365-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="1e365-256">[「MSApp 定数」を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="1e365-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="1e365-257">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-257">[in]</span></span>
      
      | <span data-ttu-id="1e365-258">型</span><span class="sxs-lookup"><span data-stu-id="1e365-258">Type</span></span> | <span data-ttu-id="1e365-259">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="1e365-260">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-260">Any</span></span> | <span data-ttu-id="1e365-261">同期呼び出しコールバック関数 \(パラメーター 1 など on\) に渡される、オプションの一連の引数です。</span><span class="sxs-lookup"><span data-stu-id="1e365-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-262">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-262">Return value</span></span>**  
      
      <span data-ttu-id="1e365-263">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-264">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-264">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-265">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-266">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-266">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-267">指定された `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="1e365-268">は、指定された優先度に従ってディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="1e365-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="1e365-269">通常の優先度は、既存の [setImmediate メソッドと同](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) じです。</span><span class="sxs-lookup"><span data-stu-id="1e365-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="1e365-270">コールバックを実行すると、現在のコンテキスト優先度は、コールバックの実行期間中に指定された優先度パラメーター値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="1e365-271">callback `asynchronousCallback` パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="1e365-272">引数がパラメーターの後に指定 `priority` されている場合、引数はすべてコールバック関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="1e365-273">異 `execAtPriority` なり、コールバック関数によって返されるオブジェクト `asynchronousCallback` は無視されます \(and not returned `execAsyncAtPriority` via \).</span><span class="sxs-lookup"><span data-stu-id="1e365-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-274">例</span><span class="sxs-lookup"><span data-stu-id="1e365-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="execatpriority"></a><span data-ttu-id="1e365-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="1e365-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-276">指定されたコンテキスト優先度で指定されたコールバック関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e365-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-277">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="1e365-278">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-278">[in]</span></span>  
      
      | <span data-ttu-id="1e365-279">型</span><span class="sxs-lookup"><span data-stu-id="1e365-279">Type</span></span> | <span data-ttu-id="1e365-280">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-281">機能</span><span class="sxs-lookup"><span data-stu-id="1e365-281">Function</span></span> | <span data-ttu-id="1e365-282">指定された優先度のコンテキスト優先度で同期的に実行するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="1e365-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="1e365-283">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-283">[in]</span></span>  
      
      | <span data-ttu-id="1e365-284">型</span><span class="sxs-lookup"><span data-stu-id="1e365-284">Type</span></span> | <span data-ttu-id="1e365-285">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-286">DOMString</span></span> | <span data-ttu-id="1e365-287">コールバック関数の実行中に現在のコンテキスト優先度の値が設定される、指定された優先度 `synchronousCallback` の値。</span><span class="sxs-lookup"><span data-stu-id="1e365-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="1e365-288">[「MSApp 定数」を参照してください](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="1e365-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="1e365-289">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-289">[in]</span></span>  
      
      | <span data-ttu-id="1e365-290">型</span><span class="sxs-lookup"><span data-stu-id="1e365-290">Type</span></span> | <span data-ttu-id="1e365-291">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-292">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-292">Any</span></span> | <span data-ttu-id="1e365-293">コールバック関数 \(パラメーター 1 などとして on\) に渡される、オプションの一連 `synchronousCallback` の引数です。</span><span class="sxs-lookup"><span data-stu-id="1e365-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-294">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-294">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-295">型</span><span class="sxs-lookup"><span data-stu-id="1e365-295">Type</span></span> | <span data-ttu-id="1e365-296">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-297">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-297">Any</span></span> | <span data-ttu-id="1e365-298">コールバック `synchronousCallback` \(適用可能な\) の戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-299">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-299">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-300">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-301">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-301">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-302">指定された `synchronousCallback` コールバック メソッドは同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="1e365-303">現在のコンテキスト優先度は、指定されたコールバック関数の期間中、指定された優先度の値 (priority 引数によって指定) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="1e365-304">コールバック関数の実行が終了すると、呼び出しの前に前の値に優先度が返 `execAtPriority` されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="1e365-305">戻り値は `execAtPriority` 、コールバック メソッド \(提供\) の戻り値です。</span><span class="sxs-lookup"><span data-stu-id="1e365-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="1e365-306">callback `synchronousCallback` パラメーターには、任意の関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="1e365-307">priority パラメーターの後に引数が指定されている場合は、指定されたコールバック メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="1e365-308">callback パラメーターが値を返す場合、この値も戻り値 `execAtPriority` になります。</span><span class="sxs-lookup"><span data-stu-id="1e365-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-309">例</span><span class="sxs-lookup"><span data-stu-id="1e365-309">Example</span></span>**  
      
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

### <a name="getcurrentpriority"></a><span data-ttu-id="1e365-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="1e365-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-311">現在のコンテキスト優先度を返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-312">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-312">Parameters</span></span>**  
      
      <span data-ttu-id="1e365-313">ありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-314">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-314">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-315">型</span><span class="sxs-lookup"><span data-stu-id="1e365-315">Type</span></span> | <span data-ttu-id="1e365-316">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-317">DOMString</span></span> | <span data-ttu-id="1e365-318">戻り値は、文字列 、、または `MSApp.HIGH` `MSApp.NORMAL` の 1 つ `MSApp.IDLE` です。</span><span class="sxs-lookup"><span data-stu-id="1e365-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-319">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-319">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-320">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-321">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-321">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-322">このメソッドは、現在のコンテキスト優先度 [\(MSApp Constants](#msapp-constants)\を参照) を返します。これは、 を使用して変更 `execAtPriority` できます `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-323">例</span><span class="sxs-lookup"><span data-stu-id="1e365-323">Example</span></span>**  
      
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

### <a name="gethtmlprintdocumentsource"></a><span data-ttu-id="1e365-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="1e365-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="1e365-325">非推奨になった同期 API。</span><span class="sxs-lookup"><span data-stu-id="1e365-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="1e365-326">Windows 10 の場合は、を参照してください `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="1e365-327">アプリWindows 8 8.1 アプリについては [、getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e365-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <a name="gethtmlprintdocumentsourceasync"></a><span data-ttu-id="1e365-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="1e365-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-329">印刷するソース コンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-330">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="1e365-331">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-331">[in]</span></span>  
      
      | <span data-ttu-id="1e365-332">型</span><span class="sxs-lookup"><span data-stu-id="1e365-332">Type</span></span> | <span data-ttu-id="1e365-333">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-334">Document</span><span class="sxs-lookup"><span data-stu-id="1e365-334">Document</span></span> | <span data-ttu-id="1e365-335">印刷する HTML ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="1e365-335">The HTML document to be printed.</span></span>  <span data-ttu-id="1e365-336">ルート ドキュメント、iframe 内のドキュメント、ドキュメント フラグメント、SVG ドキュメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="1e365-337">htmlDoc は、要素ではなくドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-338">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-338">Return value</span></span>**
      
      <span data-ttu-id="1e365-339">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-340">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-340">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-341">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-342">解説</span><span class="sxs-lookup"><span data-stu-id="1e365-342">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-343">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-344">例 1</span><span class="sxs-lookup"><span data-stu-id="1e365-344">Example 1</span></span>**  
      
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
      **<span data-ttu-id="1e365-345">例 2</span><span class="sxs-lookup"><span data-stu-id="1e365-345">Example 2</span></span>**  
      
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

### <a name="getviewid"></a><span data-ttu-id="1e365-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="1e365-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-347">複数のウィンドウのサポート。</span><span class="sxs-lookup"><span data-stu-id="1e365-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="1e365-348">Win8.1 では、JavaScript UWP アプリは MSApp DOM API を使用して複数のウィンドウをサポートし、現在は削除されています。</span><span class="sxs-lookup"><span data-stu-id="1e365-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="1e365-349">Windows 10 の場合は、 `window.open` を使用 `window` し、新しい `MSApp.getViewId` .</span><span class="sxs-lookup"><span data-stu-id="1e365-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="1e365-350">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-350">Description</span></span> |<span data-ttu-id="1e365-351">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1e365-351">Windows 10</span></span> | <span data-ttu-id="1e365-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1e365-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="1e365-353">新しいウィンドウの作成</span><span class="sxs-lookup"><span data-stu-id="1e365-353">Create new window</span></span> | [<span data-ttu-id="1e365-354">window.open</span><span class="sxs-lookup"><span data-stu-id="1e365-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="1e365-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="1e365-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="1e365-356">新しい window オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1e365-356">New window object</span></span> | [<span data-ttu-id="1e365-357">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1e365-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="1e365-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="1e365-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-359">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="1e365-360">型</span><span class="sxs-lookup"><span data-stu-id="1e365-360">Type</span></span> | <span data-ttu-id="1e365-361">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-362">DOMString</span></span> | <span data-ttu-id="1e365-363">DOM ドキュメントを含むウィンドウを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e365-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-364">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="1e365-365">型</span><span class="sxs-lookup"><span data-stu-id="1e365-365">Type</span></span> | <span data-ttu-id="1e365-366">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-367">Number</span><span class="sxs-lookup"><span data-stu-id="1e365-367">Number</span></span> | <span data-ttu-id="1e365-368">さまざまな [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-369">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-369">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-370">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-371">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-371">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-372">[window.open と window](https://developer.mozilla.org/docs/Web/API/Window/open)[を使用](https://developer.mozilla.org/docs/Web/API/Window)して新しいウィンドウを作成しますが、WinRT API を操作するには、API を追加 `MSApp.getViewId` します。</span><span class="sxs-lookup"><span data-stu-id="1e365-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="1e365-373">オブジェクトをパラメーターとして受け取り、 `window` さまざまな `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="1e365-374">可視性の遅延</span><span class="sxs-lookup"><span data-stu-id="1e365-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="1e365-375">WinRT のビューは通常は非表示で開始され、エンド開発者は、完全に準備が整った後にビューを表示する方法 `TryShowAsStandaloneAsync` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e365-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="1e365-376">Web の世界では、ウィンドウがすぐに表示され、コンテンツが読み込まれレンダリングされるのをエンド ユーザー `window.open` が確認できます。</span><span class="sxs-lookup"><span data-stu-id="1e365-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="1e365-377">新しいウィンドウが WinRT のビューのように機能し、すぐに表示されない場合は、オプションを追加 `window.open` しました。</span><span class="sxs-lookup"><span data-stu-id="1e365-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="1e365-378">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="1e365-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="1e365-379">プライマリ ウィンドウの違い</span><span class="sxs-lookup"><span data-stu-id="1e365-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="1e365-380">OS によって最初に開いたプライマリ ウィンドウは、開くセカンダリ ウィンドウとは異なる動作をします。</span><span class="sxs-lookup"><span data-stu-id="1e365-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="1e365-381">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-381">Description</span></span> | <span data-ttu-id="1e365-382">プライマリ</span><span class="sxs-lookup"><span data-stu-id="1e365-382">Primary</span></span> | <span data-ttu-id="1e365-383">セカンダリ</span><span class="sxs-lookup"><span data-stu-id="1e365-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="1e365-384">window.open</span><span class="sxs-lookup"><span data-stu-id="1e365-384">window.open</span></span> | <span data-ttu-id="1e365-385">許可されます</span><span class="sxs-lookup"><span data-stu-id="1e365-385">Allowed</span></span> | <span data-ttu-id="1e365-386">Disallowed</span><span class="sxs-lookup"><span data-stu-id="1e365-386">Disallowed</span></span> |  
          | <span data-ttu-id="1e365-387">window.close</span><span class="sxs-lookup"><span data-stu-id="1e365-387">window.close</span></span> | <span data-ttu-id="1e365-388">アプリを閉じる</span><span class="sxs-lookup"><span data-stu-id="1e365-388">Close app</span></span> | <span data-ttu-id="1e365-389">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="1e365-389">Close window</span></span> |  
          | <span data-ttu-id="1e365-390">ナビゲーションの制限</span><span class="sxs-lookup"><span data-stu-id="1e365-390">Navigation restrictions</span></span> | <span data-ttu-id="1e365-391">ACUR のみ</span><span class="sxs-lookup"><span data-stu-id="1e365-391">ACUR only</span></span> | <span data-ttu-id="1e365-392">制限なし</span><span class="sxs-lookup"><span data-stu-id="1e365-392">No restrictions</span></span> |  
          
         <!-- The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).  -->  
      
      *   <span data-ttu-id="1e365-393">同じ Origin 通信の制限</span><span class="sxs-lookup"><span data-stu-id="1e365-393">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="1e365-394">同期、同一発生元、クロスウィンドウ、スクリプト呼び出しの適切なサポートを妨げている技術的な問題があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-394">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="1e365-395">同じ原点のウィンドウを開いた場合、あるウィンドウ内のスクリプトは他のウィンドウの関数を直接呼び出すのを許可され、これらの呼び出しの一部は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1e365-395">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="1e365-396">呼び出しはうまく動作し、可能であれば実行する推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="1e365-396">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="1e365-397">この問題を改善するための作業が進行中です。</span><span class="sxs-lookup"><span data-stu-id="1e365-397">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-398">例</span><span class="sxs-lookup"><span data-stu-id="1e365-398">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <a name="istaskscheduledatpriorityorhigher"></a><span data-ttu-id="1e365-399">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="1e365-399">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-400">指定された優先度レベル以上で保留中の作業が存在するかどうかを示すブール型 (Boolean) の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-400">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-401">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-401">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="1e365-402">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-402">[in]</span></span>
      
      | <span data-ttu-id="1e365-403">型</span><span class="sxs-lookup"><span data-stu-id="1e365-403">Type</span></span> | <span data-ttu-id="1e365-404">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-404">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-405">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-405">DOMString</span></span> | <span data-ttu-id="1e365-406">未処理のキューに入った作業を照会する優先度レベル以上を指定する優先度値 [\(MSApp Constants](#msapp-constants)\を参照)。</span><span class="sxs-lookup"><span data-stu-id="1e365-406">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-407">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-407">Return value</span></span>**  
      
      | <span data-ttu-id="1e365-408">型</span><span class="sxs-lookup"><span data-stu-id="1e365-408">Type</span></span> | <span data-ttu-id="1e365-409">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-409">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-410">ブール値</span><span class="sxs-lookup"><span data-stu-id="1e365-410">Boolean</span></span> | <span data-ttu-id="1e365-411">指定された優先度レベル以上でキューに入った作業がある場合、それ以外の場合 `true` は `false` 返します。</span><span class="sxs-lookup"><span data-stu-id="1e365-411">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-412">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-412">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-413">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-413">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-414">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-414">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-415">このメソッドは、呼び出し元の JavaScript コードが優先度の高い作業に向かうという意図を持つ、さまざまな優先度レベル \(または上記\) で保留中の作業が実行されるかどうかを判断する JavaScript コードの手段を提供します。 `isTaskScheduledAtPriorityOrHigher`</span><span class="sxs-lookup"><span data-stu-id="1e365-415">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-416">例</span><span class="sxs-lookup"><span data-stu-id="1e365-416">Example</span></span>**  
      
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

### <a name="pagehandlesallapplicationactivations"></a><span data-ttu-id="1e365-417">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="1e365-417">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-418">すべてのアクティブ化イベント \(通知やピン留めされたタイル\のクリックなど) の前に開始パス (ページの再読み込み) が更新されるのを避けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-418">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-419">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-419">Parameters</span></span>**  
      
      | <span data-ttu-id="1e365-420">型</span><span class="sxs-lookup"><span data-stu-id="1e365-420">Type</span></span> | <span data-ttu-id="1e365-421">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-421">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-422">ブール値</span><span class="sxs-lookup"><span data-stu-id="1e365-422">Boolean</span></span> | <span data-ttu-id="1e365-423">スタート パスの更新 (ページの再読み込み) を常にスキップし、代わりにアクティブ化されたイベントの発生 `MSApp.pageHandlesAllApplicationActivations(true)` に直進 `WebUIApplication` するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1e365-423">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="1e365-424">すべてのページでライセンス認証イベントを個別に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-424">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="1e365-425">このメソッドを次のように定義すると、アクティブ化されたイベント `true` \(notification\など) をクリックすると、再読み込みはトリガーされません。ページの再読み込みを回避する単一ページ アプリにとって不可欠です。</span><span class="sxs-lookup"><span data-stu-id="1e365-425">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-426">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-426">Return value</span></span>**
      
      <span data-ttu-id="1e365-427">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-427">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-428">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-428">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-429">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-429">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-430">解説</span><span class="sxs-lookup"><span data-stu-id="1e365-430">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-431">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-431">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-432">例</span><span class="sxs-lookup"><span data-stu-id="1e365-432">Example</span></span>**  
      
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

### <a name="suppresssubdownloadcredentialprompts"></a><span data-ttu-id="1e365-433">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="1e365-433">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-434">リソースのダウンロード中にアプリが認証プロンプトを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1e365-434">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-435">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-435">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="1e365-436">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-436">[in]</span></span>
      
      | <span data-ttu-id="1e365-437">型</span><span class="sxs-lookup"><span data-stu-id="1e365-437">Type</span></span> | <span data-ttu-id="1e365-438">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-438">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-439">ブール値</span><span class="sxs-lookup"><span data-stu-id="1e365-439">Boolean</span></span> | <span data-ttu-id="1e365-440">true の値を指定すると、潜在的な認証プロンプトが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-440">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="1e365-441">false の値を指定しても、ユーザーからの潜在的な認証プロンプトは抑制されない。</span><span class="sxs-lookup"><span data-stu-id="1e365-441">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-442">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-442">Return value</span></span>**  
      
      <span data-ttu-id="1e365-443">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-443">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-444">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-444">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-445">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-445">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-446">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-446">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-447">この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中にアプリが潜在的な認証プロンプトを抑制するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1e365-447">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="1e365-448">既定の動作では、資格情報のプロンプトを抑制しません。</span><span class="sxs-lookup"><span data-stu-id="1e365-448">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="1e365-449">これは、メール アプリ \(各画像が認証を必要とする多数の画像を含むニュースレターを含む可能性がある)など、認証を必要とするリソースが過剰に読み込まれる可能性があるアプリで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="1e365-449">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="1e365-450">資格情報のプロンプトを表示しない場合、認証が必要なリソースにアクセスするときにサーバーに対する認証のダイアログは表示されません。リソースはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="1e365-450">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="1e365-451">プロキシ認証やクライアント認定要求ダイアログなどの他の可能なプロンプトには影響を与え `suppressSubdownloadCredentialPrompts` 、XHR には影響を与えもしない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1e365-451">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="1e365-452">要素でホスト `suppressSubdownloadCredentialPrompts` されるコンテンツを含め、アプリケーション内のすべてのコンテンツに影響を与える点に注意 `webview` してください。</span><span class="sxs-lookup"><span data-stu-id="1e365-452">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="1e365-453">資格情報プロンプトの決定はキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="1e365-453">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="1e365-454">したがって、資格情報のプロンプトを抑制するとすぐに有効になりますが、資格情報を抑制した後に資格情報のプロンプトを有効にするには、ドキュメントの再読み込みが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e365-454">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-455">例</span><span class="sxs-lookup"><span data-stu-id="1e365-455">Example</span></span>**  
      
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

### <a name="terminateapp"></a><span data-ttu-id="1e365-456">terminateApp</span><span class="sxs-lookup"><span data-stu-id="1e365-456">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-457">現在のアプリケーションを終了し、エラー レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e365-457">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-458">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-458">Parameters</span></span>**  
      
      `error` <span data-ttu-id="1e365-459">[in]</span><span class="sxs-lookup"><span data-stu-id="1e365-459">[in]</span></span>
      
      | <span data-ttu-id="1e365-460">型</span><span class="sxs-lookup"><span data-stu-id="1e365-460">Type</span></span> | <span data-ttu-id="1e365-461">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-461">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-462">エラー</span><span class="sxs-lookup"><span data-stu-id="1e365-462">Error</span></span> | <span data-ttu-id="1e365-463">終了 `Error` をトリガーしたエラーを記述するために使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e365-463">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="1e365-464">オブジェクトには、数値、説明、およびスタック プロパティが含まれている必要があります。オブジェクトにこれらのプロパティが含まれている場合、エラー レポート `Error` は生成されません。</span><span class="sxs-lookup"><span data-stu-id="1e365-464">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-465">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-465">Return value</span></span>**
      
      <span data-ttu-id="1e365-466">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-466">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-467">例外</span><span class="sxs-lookup"><span data-stu-id="1e365-467">Exceptions</span></span>**  
      
      <span data-ttu-id="1e365-468">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-468">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-469">注釈</span><span class="sxs-lookup"><span data-stu-id="1e365-469">Remarks</span></span>**  
      
      <span data-ttu-id="1e365-470">報告された問題がアプリの上位 5 つの問題の 1 つになった場合は、アプリの [品質] ページ `terminateApp` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e365-470">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-471">例</span><span class="sxs-lookup"><span data-stu-id="1e365-471">Example</span></span>**  
      
      <span data-ttu-id="1e365-472">次の使用例は `terminateApp` 、例外が発生した場合に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1e365-472">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="1e365-473">例外をキャッチ `Error` するときに指定されたオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e365-473">It uses the `Error` object provided when you catch an exception.</span></span>  
      
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

### <a name="msapp-constants"></a><span data-ttu-id="1e365-474">MSApp 定数</span><span class="sxs-lookup"><span data-stu-id="1e365-474">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-475">、、、に関連付けられた許可 `execAsyncAtPriority` `execAtPriority` された優先度 `getCurrentPriority` の値 `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-475">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <a name="current"></a><span data-ttu-id="1e365-476">現在の顧客</span><span class="sxs-lookup"><span data-stu-id="1e365-476">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="1e365-477">型</span><span class="sxs-lookup"><span data-stu-id="1e365-477">Type</span></span> | <span data-ttu-id="1e365-478">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-478">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-479">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-479">DOMString</span></span> | <span data-ttu-id="1e365-480">適切なメソッド \(see also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは現在のコンテキスト優先度 `current` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e365-480">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="high"></a><span data-ttu-id="1e365-481">高</span><span class="sxs-lookup"><span data-stu-id="1e365-481">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="1e365-482">型</span><span class="sxs-lookup"><span data-stu-id="1e365-482">Type</span></span> | <span data-ttu-id="1e365-483">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-483">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-484">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-484">DOMString</span></span> | <span data-ttu-id="1e365-485">`high`適切なメソッド \(See also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の優先度よりも高い値を使用し、既存の通常の優先度の作業の前に操作をディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="1e365-485">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <a name="idle"></a><span data-ttu-id="1e365-486">アイドル</span><span class="sxs-lookup"><span data-stu-id="1e365-486">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="1e365-487">型</span><span class="sxs-lookup"><span data-stu-id="1e365-487">Type</span></span> | <span data-ttu-id="1e365-488">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-488">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-489">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-489">DOMString</span></span> | <span data-ttu-id="1e365-490">`ideal`適切なメソッド \(See also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の優先度より低い値を使用し、既存の通常の優先度の作業の後に操作をディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="1e365-490">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="normal"></a><span data-ttu-id="1e365-491">通常</span><span class="sxs-lookup"><span data-stu-id="1e365-491">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="1e365-492">型</span><span class="sxs-lookup"><span data-stu-id="1e365-492">Type</span></span> | <span data-ttu-id="1e365-493">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-493">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-494">DOMString</span><span class="sxs-lookup"><span data-stu-id="1e365-494">DOMString</span></span> | <span data-ttu-id="1e365-495">適切 `normal` なメソッドと一緒に使用する場合 (「また」セクションを参照)、要求された操作を実行するときに、メソッドは通常の既存の優先度を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e365-495">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-496">例</span><span class="sxs-lookup"><span data-stu-id="1e365-496">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-497">要件</span><span class="sxs-lookup"><span data-stu-id="1e365-497">Requirements</span></span>**  
      
      | <span data-ttu-id="1e365-498">型</span><span class="sxs-lookup"><span data-stu-id="1e365-498">Type</span></span> | <span data-ttu-id="1e365-499">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-499">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-500">IDL</span><span class="sxs-lookup"><span data-stu-id="1e365-500">IDL</span></span> | <span data-ttu-id="1e365-501">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="1e365-501">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <a name="msappasyncoperation"></a><span data-ttu-id="1e365-502">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="1e365-502">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <a name="start"></a><span data-ttu-id="1e365-503">start</span><span class="sxs-lookup"><span data-stu-id="1e365-503">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1e365-504">を開始 `MSAppAsyncOperation` します。</span><span class="sxs-lookup"><span data-stu-id="1e365-504">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="1e365-505">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e365-505">Parameters</span></span>**  
      
      <span data-ttu-id="1e365-506">ありません。</span><span class="sxs-lookup"><span data-stu-id="1e365-506">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="1e365-507">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e365-507">Return value</span></span>**
      
      <span data-ttu-id="1e365-508">なし。</span><span class="sxs-lookup"><span data-stu-id="1e365-508">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="1e365-509">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-509">Properties</span></span>**  
      
      `error` <span data-ttu-id="1e365-510">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-510">property</span></span>  
      
      | <span data-ttu-id="1e365-511">型</span><span class="sxs-lookup"><span data-stu-id="1e365-511">Type</span></span> | <span data-ttu-id="1e365-512">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-512">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-513">DOMError</span><span class="sxs-lookup"><span data-stu-id="1e365-513">DOMError</span></span> | <span data-ttu-id="1e365-514">でエラーを表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-514">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="1e365-515">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-515">property</span></span>  
      
      | <span data-ttu-id="1e365-516">型</span><span class="sxs-lookup"><span data-stu-id="1e365-516">Type</span></span> | <span data-ttu-id="1e365-517">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-517">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-518">EventHandler</span><span class="sxs-lookup"><span data-stu-id="1e365-518">EventHandler</span></span> | <span data-ttu-id="1e365-519">の完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-519">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="1e365-520">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-520">property</span></span>  
      
      | <span data-ttu-id="1e365-521">型</span><span class="sxs-lookup"><span data-stu-id="1e365-521">Type</span></span> | <span data-ttu-id="1e365-522">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-522">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-523">EventHandler</span><span class="sxs-lookup"><span data-stu-id="1e365-523">EventHandler</span></span> | <span data-ttu-id="1e365-524">エラー時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。</span><span class="sxs-lookup"><span data-stu-id="1e365-524">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="1e365-525">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-525">property</span></span>  
      
      | <span data-ttu-id="1e365-526">型</span><span class="sxs-lookup"><span data-stu-id="1e365-526">Type</span></span> | <span data-ttu-id="1e365-527">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-527">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-528">Number</span><span class="sxs-lookup"><span data-stu-id="1e365-528">Number</span></span> | <span data-ttu-id="1e365-529">JavaScript を使用して Windows アプリ内の非同期操作の状態を表します。</span><span class="sxs-lookup"><span data-stu-id="1e365-529">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="1e365-530">値には `Started[0]` 、、 `Completed[1]` 、 が含 `Error[2]` まれます。</span><span class="sxs-lookup"><span data-stu-id="1e365-530">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="1e365-531">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e365-531">property</span></span>  
      
      | <span data-ttu-id="1e365-532">型</span><span class="sxs-lookup"><span data-stu-id="1e365-532">Type</span></span> | <span data-ttu-id="1e365-533">説明</span><span class="sxs-lookup"><span data-stu-id="1e365-533">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="1e365-534">任意</span><span class="sxs-lookup"><span data-stu-id="1e365-534">Any</span></span> |<span data-ttu-id="1e365-535">の結果を表します `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="1e365-535">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
