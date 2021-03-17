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
# <a name="msapp"></a>MSApp  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API 機能にアクセスする PWA を含む)を使用する Windows アプリでのみサポートされます。  MSApp オブジェクトは、ms-appx URI スキームを介して読み込まれた Windows アプリ内の HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (したがって、そのメソッドとプロパティは使用できません)。  

Blob オブジェクトと MSStream オブジェクトを作成できる[ヘルパー](https://developer.mozilla.org/docs/Web/API/Blob)[関数を提供](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)します。  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [メソッド](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      [clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPri](#getcurrentpriority) [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [定数](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      [current](#current), [high](#high), [idle](#idle), [normal](#normal).  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [MSAppAsyncOperation インターフェイス](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [start](#start)  
   :::column-end:::
:::row-end:::  

## <a name="msapp-methods"></a>MSApp メソッド  

### <a name="cleartemporarywebdataasync"></a>clearTemporaryWebDataAsync  

:::row:::
   :::column span="":::
      アプリまたは WebView のキャッシュとインデックス付きDB データを [クリアします](../../hosting/webview/index.md)。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      このメソッドにはパラメーターはありません。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      型: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)  
      
      非同期アクションを表します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **解説**  
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createblobfromrandomaccessstream"></a>createBlobFromRandomAccessStream  

:::row:::
   :::column span="":::
      [IRandomAccessStream オブジェクトから BLOB を作成](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)します。 [](https://developer.mozilla.org/docs/Web/API/Blob)  このメソッドは、ストリームから W3C ベースのオブジェクトを作成するために、アプリ内のオブジェクトを処理 `IRandomAccessStream` するときに使用する必要があります。  BLOB が作成されると [、FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、および](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest と一緒に使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `type` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | String | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクション 3.7 で定義されているメディア型トークンで指定された形式である必要があります。  |  
      
      `stream` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | [BLOB に格納する IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | BLOB | ストリームを含む新しい BLOB オブジェクト。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      | 例外 | 状況 |  
      |:---- |:--- |  
      | TypeMismatchError | ノードの種類は、予期されるパラメーターの種類と互換性がありません。  10 より前のInternet Explorerでは、TYPE_MISMATCH_ERRが返されます。  |  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      Windows ランタイムの型から、ウィンドウ オブジェクトの MSApp 名前空間を介して BLOB を作成します。  このメソッドは、基本的に、提供された [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクトの光ラッパーである BLOB を作成します。  BLOB はこのストリームの有効期間を所有し、BLOB が破棄されるとストリームは閉じられます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="createdatapackage"></a>createDataPackage  

:::row:::
   :::column span="":::
      ユーザーまたはアプリケーションの指定した範囲を、共有できる HTML フラグメントに変換します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `object` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | この範囲は、選択オブジェクト (たとえば、手動) `window.selection.getRangeAt(0)` から作成できます。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | 指定した範囲の HTML マークアップを格納します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは[、TextRange ではなく、Document オブジェクト モデル (DOM) 範囲](https://developer.mozilla.org/docs/Web/API/Range)[のみをサポートします](/uwp/api/windows.ui.xaml.documents.textrange)。  指定した範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。  
      
      返されるデータ パッケージに使用可能なプロパティはありません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createdatapackagefromselection"></a>createDataPackageFromSelection  

:::row:::
   :::column span="":::
      ユーザーまたはアプリケーションの選択を、共有できる HTML フラグメントに変換します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      このメソッドにはパラメーターはありません。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | 指定した範囲の HTML マークアップを格納します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      選択範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。  アプリケーションの UI 内の任意の場所にユーザーの選択がない場合は、 を `createDataPackageFromSelection` 返します `null` 。  
      
      返されるデータ パッケージに使用可能なプロパティはありません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <a name="createfilefromstoragefile"></a>createFileFromStorageFile  

:::row:::
   :::column span="":::
      [WinRT StorageFile を](/uwp/api/)[標準の](/uwp/api/windows.storage.storagefile)W3C File オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `storageFile` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | ストレージ ファイルが含まれる。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      | 例外 | 状況 |  
      |:---- |:--- |  
      | TypeMismatchError | 指定した W3C ファイル参照が無効です。  10 より前のInternet Explorerの場合 `TYPE_MISMATCH_ERR` は、返されます。  |  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createstreamfrominputstream"></a>createStreamFromInputStream  

:::row:::
   :::column span="":::
      InputStream [から MSStream](https://msdn.microsoft.com/library/hh772328) を [作成します](https://msdn.microsoft.com/library/hh772327)。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `type` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクション 3.7 で定義されているメディア型トークンで指定された形式である必要があります。  \([MIME の種類を参照してください https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` ]、、など `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` \)。  
      
      `inputStream` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | に[格納する IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`  |  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、コンテンツ タイプと参照を受け取 `IInputStream` る。  次に、メソッドは、渡されたストリーム参照が型のインスタンスであり、それではない場合は、 `IInputStream` をスローします `DOMException TYPE_MISMATCH_ERR` 。  エラーが発生しない場合は `createStreamFromInputStream` `MSStream` 、\(その入力\から) を作成します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      An `IInputStream` を使用して、 を作成できます `MSStream` 。  本質的に 1 回限り使用されるオブジェクトと同様に、image 要素によって最初に解決されると、作成された URL はすべて `MSStreams` `URL.createObjectURL` 取り消されます。  さらに、ストリームの使用後にこのオブジェクトの 2 番目の URL の要求は失敗します。  
      
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

### <a name="execasyncatpriority"></a>execAsyncAtPriority  

:::row:::
   :::column span="":::
      指定された優先度に従って、後で実行されるコールバックをスケジュールします。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `asynchronousCallback` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 機能 | 指定された優先度でディスパッチされた非同期的に実行するコールバック関数。  |  
      
      `priority` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 非同期Callback コールバックが実行されるコンテキスト優先度の値。  [「MSApp 定数」を参照してください](#msapp-constants)。  |  
      
      `args` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |   
      | 任意 | 同期呼び出しコールバック関数 \(パラメーター 1 など on\) に渡される、オプションの一連の引数です。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      このメソッドに戻り値はありません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      指定された `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。  `asynchronousCallback` は、指定された優先度に従ってディスパッチされます。  通常の優先度は、既存の [setImmediate メソッドと同](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) じです。  コールバックを実行すると、現在のコンテキスト優先度は、コールバックの実行期間中に指定された優先度パラメーター値に設定されます。  
      
      callback `asynchronousCallback` パラメーターには、任意の関数を指定できます。  引数がパラメーターの後に指定 `priority` されている場合、引数はすべてコールバック関数に渡されます。  
      
      異 `execAtPriority` なり、コールバック関数によって返されるオブジェクト `asynchronousCallback` は無視されます \(and not returned `execAsyncAtPriority` via \).  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="execatpriority"></a>execAtPriority  

:::row:::
   :::column span="":::
      指定されたコンテキスト優先度で指定されたコールバック関数を実行します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `synchronousCallback` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 機能 | 指定された優先度のコンテキスト優先度で同期的に実行するコールバック関数。  |  
      
      `priority` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | コールバック関数の実行中に現在のコンテキスト優先度の値が設定される、指定された優先度 `synchronousCallback` の値。  [「MSApp 定数」を参照してください](#msapp-constants)。  |  
      
      `args` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバック関数 \(パラメーター 1 などとして on\) に渡される、オプションの一連 `synchronousCallback` の引数です。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバック `synchronousCallback` \(適用可能な\) の戻り値を返します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      指定された `synchronousCallback` コールバック メソッドは同期的に実行されます。  現在のコンテキスト優先度は、指定されたコールバック関数の期間中、指定された優先度の値 (priority 引数によって指定) に変更されます。  コールバック関数の実行が終了すると、呼び出しの前に前の値に優先度が返 `execAtPriority` されます。  戻り値は `execAtPriority` 、コールバック メソッド \(提供\) の戻り値です。  
      
      callback `synchronousCallback` パラメーターには、任意の関数を指定できます。  priority パラメーターの後に引数が指定されている場合は、指定されたコールバック メソッドに渡されます。  callback パラメーターが値を返す場合、この値も戻り値 `execAtPriority` になります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="getcurrentpriority"></a>getCurrentPriority  

:::row:::
   :::column span="":::
      現在のコンテキスト優先度を返します。  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      ありません。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 戻り値は、文字列 、、または `MSApp.HIGH` `MSApp.NORMAL` の 1 つ `MSApp.IDLE` です。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、現在のコンテキスト優先度 [\(MSApp Constants](#msapp-constants)\を参照) を返します。これは、 を使用して変更 `execAtPriority` できます `execAsyncAtPriority` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="gethtmlprintdocumentsource"></a>getHtmlPrintDocumentSource  

非推奨になった同期 API。  Windows 10 の場合は、を参照してください `getHtmlPrintDocumentSourceAsync` 。  アプリWindows 8 8.1 アプリについては [、getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。  

### <a name="gethtmlprintdocumentsourceasync"></a>getHtmlPrintDocumentSourceAsync  

:::row:::
   :::column span="":::
      印刷するソース コンテンツを返します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `htmlDoc` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Document | 印刷する HTML ドキュメント。  ルート ドキュメント、iframe 内のドキュメント、ドキュメント フラグメント、SVG ドキュメントを指定できます。  htmlDoc は、要素ではなくドキュメントである必要があります。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **解説**  
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例 1**  
      
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
      **例 2**  
      
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

### <a name="getviewid"></a>getViewId  

:::row:::
   :::column span="":::
      複数のウィンドウのサポート。  
      
      > [!NOTE] 
      > Win8.1 では、JavaScript UWP アプリは MSApp DOM API を使用して複数のウィンドウをサポートし、現在は削除されています。  Windows 10 の場合は、 `window.open` を使用 `window` し、新しい `MSApp.getViewId` .  
      
      | 説明 |Windows 10 | Windows 8.1 |  
      |:---- |:---- |:--- |  
      | 新しいウィンドウの作成 | [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) | [MSApp.createNewView](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |新しい window オブジェクト | [ウィンドウ](https://developer.mozilla.org/docs/Web/API/Window) |[MSAppView](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `window`
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | DOM ドキュメントを含むウィンドウを表すオブジェクト。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      `viewId`
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Number | さまざまな [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      [window.open と window](https://developer.mozilla.org/docs/Web/API/Window/open)[を使用](https://developer.mozilla.org/docs/Web/API/Window)して新しいウィンドウを作成しますが、WinRT API を操作するには、API を追加 `MSApp.getViewId` します。  オブジェクトをパラメーターとして受け取り、 `window` さまざまな `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。  
      
      *   可視性の遅延  
          
          WinRT のビューは通常は非表示で開始され、エンド開発者は、完全に準備が整った後にビューを表示する方法 `TryShowAsStandaloneAsync` を使用します。  Web の世界では、ウィンドウがすぐに表示され、コンテンツが読み込まれレンダリングされるのをエンド ユーザー `window.open` が確認できます。  新しいウィンドウが WinRT のビューのように機能し、すぐに表示されない場合は、オプションを追加 `window.open` しました。  次に、例を示します。  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   プライマリ ウィンドウの違い  
          
          OS によって最初に開いたプライマリ ウィンドウは、開くセカンダリ ウィンドウとは異なる動作をします。  
          
          | 説明 | プライマリ | セカンダリ |  
          |:---- |:--- |:--- |  
          | window.open | 許可されます | Disallowed |  
          | window.close | アプリを閉じる | ウィンドウを閉じる |  
          | ナビゲーションの制限 | ACUR のみ | 制限なし |  
          
         <!-- The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).  -->  
      
      *   同じ Origin 通信の制限  
          
          同期、同一発生元、クロスウィンドウ、スクリプト呼び出しの適切なサポートを妨げている技術的な問題があります。  同じ原点のウィンドウを開いた場合、あるウィンドウ内のスクリプトは他のウィンドウの関数を直接呼び出すのを許可され、これらの呼び出しの一部は失敗します。  `postMessage` 呼び出しはうまく動作し、可能であれば実行する推奨される方法です。  この問題を改善するための作業が進行中です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <a name="istaskscheduledatpriorityorhigher"></a>isTaskScheduledAtPriorityOrHigher  

:::row:::
   :::column span="":::
      指定された優先度レベル以上で保留中の作業が存在するかどうかを示すブール型 (Boolean) の値を返します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `priority` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 未処理のキューに入った作業を照会する優先度レベル以上を指定する優先度値 [\(MSApp Constants](#msapp-constants)\を参照)。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | ブール値 | 指定された優先度レベル以上でキューに入った作業がある場合、それ以外の場合 `true` は `false` 返します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、呼び出し元の JavaScript コードが優先度の高い作業に向かうという意図を持つ、さまざまな優先度レベル \(または上記\) で保留中の作業が実行されるかどうかを判断する JavaScript コードの手段を提供します。 `isTaskScheduledAtPriorityOrHigher`  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="pagehandlesallapplicationactivations"></a>pageHandlesAllApplicationActivations  

:::row:::
   :::column span="":::
      すべてのアクティブ化イベント \(通知やピン留めされたタイル\のクリックなど) の前に開始パス (ページの再読み込み) が更新されるのを避けるために使用されます。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | ブール値 | スタート パスの更新 (ページの再読み込み) を常にスキップし、代わりにアクティブ化されたイベントの発生 `MSApp.pageHandlesAllApplicationActivations(true)` に直進 `WebUIApplication` するために使用します。  すべてのページでライセンス認証イベントを個別に処理する必要があります。  このメソッドを次のように定義すると、アクティブ化されたイベント `true` \(notification\など) をクリックすると、再読み込みはトリガーされません。ページの再読み込みを回避する単一ページ アプリにとって不可欠です。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **解説**  
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="suppresssubdownloadcredentialprompts"></a>suppressSubdownloadCredentialPrompts  

:::row:::
   :::column span="":::
      リソースのダウンロード中にアプリが認証プロンプトを表示するかどうかを制御します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
     
      `suppress` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | ブール値 | true の値を指定すると、潜在的な認証プロンプトが抑制されます。  false の値を指定しても、ユーザーからの潜在的な認証プロンプトは抑制されない。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中にアプリが潜在的な認証プロンプトを抑制するかどうかを制御します。  既定の動作では、資格情報のプロンプトを抑制しません。  
      
      `suppressSubdownloadCredentialPrompts` これは、メール アプリ \(各画像が認証を必要とする多数の画像を含むニュースレターを含む可能性がある)など、認証を必要とするリソースが過剰に読み込まれる可能性があるアプリで使用することを目的としています。  
      
      資格情報のプロンプトを表示しない場合、認証が必要なリソースにアクセスするときにサーバーに対する認証のダイアログは表示されません。リソースはダウンロードされません。  プロキシ認証やクライアント認定要求ダイアログなどの他の可能なプロンプトには影響を与え `suppressSubdownloadCredentialPrompts` 、XHR には影響を与えもしない点に注意してください。  
      
      要素でホスト `suppressSubdownloadCredentialPrompts` されるコンテンツを含め、アプリケーション内のすべてのコンテンツに影響を与える点に注意 `webview` してください。  
      
      > [!IMPORTANT]
      > 資格情報プロンプトの決定はキャッシュされます。  したがって、資格情報のプロンプトを抑制するとすぐに有効になりますが、資格情報を抑制した後に資格情報のプロンプトを有効にするには、ドキュメントの再読み込みが必要な場合があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
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

### <a name="terminateapp"></a>terminateApp  


:::row:::
   :::column span="":::
      現在のアプリケーションを終了し、エラー レポートを生成します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      `error` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | エラー | 終了 `Error` をトリガーしたエラーを記述するために使用できるオブジェクト。  オブジェクトには、数値、説明、およびスタック プロパティが含まれている必要があります。オブジェクトにこれらのプロパティが含まれている場合、エラー レポート `Error` は生成されません。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      報告された問題がアプリの上位 5 つの問題の 1 つになった場合は、アプリの [品質] ページ `terminateApp` に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      次の使用例は `terminateApp` 、例外が発生した場合に呼び出します。  例外をキャッチ `Error` するときに指定されたオブジェクトを使用します。  
      
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

### <a name="msapp-constants"></a>MSApp 定数  

:::row:::
   :::column span="":::
      、、、に関連付けられた許可 `execAsyncAtPriority` `execAtPriority` された優先度 `getCurrentPriority` の値 `isTaskScheduldAtPriorityOrHigher` 。  
   :::column-end:::
   :::column span="":::
      #### <a name="current"></a>現在の顧客  
      
      `current`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切なメソッド \(see also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは現在のコンテキスト優先度 `current` を使用します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="high"></a>高  
      
      `high`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | `high`適切なメソッド \(See also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の優先度よりも高い値を使用し、既存の通常の優先度の作業の前に操作をディスパッチします。  |  
   :::column-end:::
   :::column span="":::
      #### <a name="idle"></a>アイドル  
      
      `idle`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | `ideal`適切なメソッド \(See also section\) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の優先度より低い値を使用し、既存の通常の優先度の作業の後に操作をディスパッチします。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="normal"></a>通常  
      
      `normal`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切 `normal` なメソッドと一緒に使用する場合 (「また」セクションを参照)、要求された操作を実行するときに、メソッドは通常の既存の優先度を使用します。  |  
   :::column-end:::
   :::column span="":::
      **例**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **要件**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | IDL | Mshtml.idl |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <a name="msappasyncoperation"></a>MSAppAsyncOperation  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <a name="start"></a>start  

:::row:::
   :::column span="":::
      を開始 `MSAppAsyncOperation` します。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **パラメーター**  
      
      ありません。  
   :::column-end:::
   :::column span="":::
      **戻り値**
      
      なし。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **プロパティ**  
      
      `error` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMError | でエラーを表します `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | の完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | エラー時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Number | JavaScript を使用して Windows アプリ内の非同期操作の状態を表します。  値には `Started[0]` 、、 `Completed[1]` 、 が含 `Error[2]` まれます。  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 |の結果を表します `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
