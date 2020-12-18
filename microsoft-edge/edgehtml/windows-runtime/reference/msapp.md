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
# MSApp  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API 機能にアクセスする PAS を含む) を使用する Windows アプリでのみサポートされます。  MSApp オブジェクトは、ms-appx URI スキームによって読み込まれた Windows アプリの HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (したがって、オブジェクトのメソッドとプロパティはいずれも使用できません)。  

Blob オブジェクトと MSStream オブジェクトを[作成できるヘルパー](https://developer.mozilla.org/docs/Web/API/Blob)[関数を提供](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)します。  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [メソッド](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      [clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage , createDataPackageFromSelection](#createdatapackage), [createFileFromStorageFile](#createfilefromstoragefile), [](#createdatapackagefromselection) [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).  
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

## MSApp メソッド  

### clearTemporaryWebDataAsync  

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

### createBlobFromRandomAccessStream  

:::row:::
   :::column span="":::
      [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)オブジェクトから[BLOB](https://developer.mozilla.org/docs/Web/API/Blob)を作成します。  このメソッドは、ストリームから W3C ベースのオブジェクトを作成するために、アプリでオブジェクトを処理するときに `IRandomAccessStream` 使用する必要があります。  作成された BLOB は [、FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、および](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest で使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。  
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
      | String | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクション 3.7 で定義されているメディアタイプ トークンで指定された形式である必要があります。  |  
      
      `stream` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | [BLOB に格納される IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Blob | ストリームを含む新しい BLOB オブジェクト。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      | 例外 | 状況 |  
      |:---- |:--- |  
      | TypeMismatchError | ノードの種類は、想定されるパラメーターの種類と互換性がありません。  Internet Explorer 10 より前のTYPE_MISMATCH_ERRが返されます。  |  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      Windows ランタイム型から、ウィンドウ オブジェクトの MSApp 名前空間を介して BLOB を作成します。  このメソッドは、基本的に、提供された [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクトのライト ラッパーである BLOB を作成します。  BLOB はこのストリームの有効期間を所有し、BLOB が破棄されるとストリームは閉じられます。  
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

### createDataPackage  

:::row:::
   :::column span="":::
      ユーザーまたはアプリケーションの指定範囲を、共有可能な HTML フラグメントに変換します。  
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
      | 任意 | この範囲は、選択オブジェクト (例: または手動) `window.selection.getRangeAt(0)` から作成できます。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | 指定した範囲の HTML マークアップが含まれます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは [、TextRange ではなく、ドキュメント オブジェクト モデル (DOM) の](https://developer.mozilla.org/docs/Web/API/Range)範囲のみを [サポートしています](/uwp/api/windows.ui.xaml.documents.textrange)。  指定した範囲に返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。  
      
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

### createDataPackageFromSelection  

:::row:::
   :::column span="":::
      ユーザーまたはアプリケーションの選択内容を、共有可能な HTML フラグメントに変換します。  
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
      | 任意 | 指定した範囲の HTML マークアップが含まれます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      選択範囲に返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれます。  アプリケーションの UI 内にユーザーの選択がない場合は、値が `createDataPackageFromSelection` 返されます `null` 。  
      
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
 
### createFileFromStorageFile  

:::row:::
   :::column span="":::
      [WinRT StorageFile を標準](/uwp/api/)[の](/uwp/api/windows.storage.storagefile)W3C File オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。  
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
      | 任意 | ストレージ ファイルが保存されています。  |  
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
      | TypeMismatchError | 指定された W3C ファイル参照が無効です。  Internet Explorer 10 より前のバージョン `TYPE_MISMATCH_ERR` の場合は、返されます。  |  
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

### createStreamFromInputStream  

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
      | DOMString | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクション 3.7 で定義されているメディアタイプ トークンで指定された形式である必要があります。  \([MIME タイプを参照]]( https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) (例: `text/plain` , `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` など\)  
      
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
      
      このメソッドは、コンテンツ タイプと参照を受け取 `IInputStream` います。  メソッドは、渡されたストリーム参照が型のインスタンスであり、ない場合はスロー `IInputStream` を検証します `DOMException TYPE_MISMATCH_ERR` 。  エラーが発生しない場合は `createStreamFromInputStream` `MSStream` 、\(入力\ から) を作成します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      An `IInputStream` を使用して作成できます `MSStream` 。  本質的に 1 回限り使用されるオブジェクトと同様に、イメージ要素によって初めて解決されると、作成された URL はすべて `MSStreams` `URL.createObjectURL` 取り消されます。  さらに、ストリームの使用後にこのオブジェクトの 2 番目の URL を要求すると失敗します。  
      
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

### execAsyncAtPriority  

:::row:::
   :::column span="":::
      指定された優先順位に従って、後で実行されるコールバックをスケジュールします。  
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
      | DOMString | asynchronousCallback コールバックが実行されるコンテキスト優先順位の値。  [MSApp 定数を参照してください](#msapp-constants)。  |  
      
      `args` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |   
      | 任意 | 同期Callback コールバック関数 \(パラメーター 1 など\ として渡される、オプションの一連の引数)。  |  
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
      
      指定された `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。  `asynchronousCallback` は、指定された優先度に従ってディスパッチされます。  通常の優先度は、既存の [setImmediate メソッドと同](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) じです。  コールバックを実行すると、現在のコンテキストの優先度は、コールバックの実行中に指定された優先度パラメーター値に設定されます。  
      
      コールバック `asynchronousCallback` パラメーターには、任意の関数を指定できます。  パラメーターの後に引数を指定 `priority` すると、引数はすべてコールバック関数に渡されます。  
      
      異 `execAtPriority` なり、コールバック関数によって返されるオブジェクト `asynchronousCallback` は無視され\(\経由では返 `execAsyncAtPriority` されません)。  
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

### execAtPriority  

:::row:::
   :::column span="":::
      指定されたコンテキスト優先順位で指定されたコールバック関数を実行します。  
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
      | 機能 | 指定された優先順位のコンテキスト優先順位で同期的に実行するコールバック関数。  |  
      
      `priority` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | コールバック関数の実行中に現在のコンテキスト優先順位の値が設定される、指定された優先度 `synchronousCallback` の値。  [MSApp 定数を参照してください](#msapp-constants)。  |  
      
      `args` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバック関数 \(パラメーター 1 など\ として) に渡される、オプションの一連 `synchronousCallback` の引数。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバック \(該当する場合 `synchronousCallback` \) の戻り値を返します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      指定された `synchronousCallback` コールバック メソッドは同期的に実行されます。  現在のコンテキスト優先度は、指定されたコールバック関数の間、指定された優先度の値 (引数 priority で指定) に変更されます。  コールバック関数の実行が終了すると、呼び出しの前に優先度が以前の値に返 `execAtPriority` されます。  戻り値は `execAtPriority` 、コールバック メソッド \(提供されている\) の戻り値です。  
      
      コールバック `synchronousCallback` パラメーターには、任意の関数を指定できます。  priority パラメーターの後に引数が指定されている場合は、指定されたコールバック メソッドに渡されます。  コールバック パラメーターが値を返す場合、この値も戻り `execAtPriority` 値になります。  
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

### getCurrentPriority  

:::row:::
   :::column span="":::
      現在のコンテキストの優先度を返します。  

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
      | DOMString | 戻り値は、文字列 、または `MSApp.HIGH` `MSApp.NORMAL` `MSApp.IDLE` .  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、現在のコンテキスト優先度 [\(MSApp Constants](#msapp-constants)\を参照) を返します。これは、次の方法で変更 `execAtPriority` できます `execAsyncAtPriority` 。  
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

### getHtmlPrintDocumentSource  

廃止された同期 API。  Windows 10 については、以下を参照してください `getHtmlPrintDocumentSourceAsync` 。  For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).  

### getHtmlPrintDocumentSourceAsync  

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
      | Document | 印刷する HTML ドキュメントを指定します。  ルート ドキュメント、iframe 内のドキュメント、ドキュメント フラグメント、SVG ドキュメントなどです。  htmlDoc は要素ではなくドキュメントである必要があります。  |  
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

### getViewId  

:::row:::
   :::column span="":::
      複数のウィンドウのサポート。  
      
      > [!NOTE] 
      > Win8.1 の JavaScript UWP アプリでは、MSApp DOM API を使用する複数のウィンドウがサポートされました。この API は、現在は使用されていません。  Windows 10 では、新 `window.open` しい `window` . `MSApp.getViewId`  
      
      | 説明 |Windows 10 | Windows 8.1 |  
      |:---- |:---- |:--- |  
      | 新しいウィンドウを作成する | [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) | [MSApp.createNewView](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |新しいウィンドウ オブジェクト | [ウィンドウ](https://developer.mozilla.org/docs/Web/API/Window) |[MSAppView](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
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
      
      [window.open と](https://developer.mozilla.org/docs/Web/API/Window/open) [window](https://developer.mozilla.org/docs/Web/API/Window)を使用して新しいウィンドウを作成しますが、WinRT API を操作するには API を追加 `MSApp.getViewId` します。  オブジェクトをパラメーターとして受け取り、 `window` さまざまな `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。  
      
      *   可視性の遅延  
          
          WinRT のビューは通常非表示で開始され、完全に準備が完了すると、エンド開発者はビューを表示する方法 `TryShowAsStandaloneAsync` を使用します。  Web ワールドでは、ウィンドウがすぐに表示され、エンド ユーザーはコンテンツの読み込みとレンダリング `window.open` を監視できます。  新しいウィンドウが WinRT のビューのように機能し、すぐに表示されない場合は、オプションを追加 `window.open` しました。  次に、例を示します。  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   プライマリ ウィンドウの相違点  
          
          OS によって最初に開いたプライマリ ウィンドウの動作は、開いたセカンダリ ウィンドウとは異なります。  
          
          | 説明 | プライマリ | セカンダリ |  
          |:---- |:--- |:--- |  
          | window.open | 許可されます | Disallowed |  
          | window.close | アプリを閉じる | ウィンドウを閉じる |  
          | ナビゲーションの制限 | ACUR のみ | 制限なし |  
          
          セカンダリ ウィンドウを開くことを許可しない制限は、フィードバックに応じて今後変更される可能性 [があります](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。  
      
      *   同一発生元の通信制限  
          
          技術的に困難な問題が発生し、同期呼び出し、同一元呼び出し、クロス ウィンドウ、スクリプト呼び出しの適切なサポートを妨げている。  同じオリジンのウィンドウを開いた場合、あるウィンドウのスクリプトは他のウィンドウの関数を直接呼び出し、一部の呼び出しは失敗します。  `postMessage` 呼び出しは問題ありませんが、可能であれば実行する方法をお勧めします。  この問題の改善作業が進行中です。  
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
    
### isTaskScheduledAtPriorityOrHigher  

:::row:::
   :::column span="":::
      指定された優先度レベル以上の保留中の作業が存在するかどうかを示すブール値を返します。  
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
      | DOMString | 優先度レベル以上を指定する優先度値 [\(MSApp Constants](#msapp-constants)\を参照) を指定して、キューに入った未処理の作業を照会します。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | ブール値 | 指定した優先度レベル以上のキューに入った作業がある場合は、それ以外の場合 `true` に `false` 返します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、呼び出し元の JavaScript コードが優先度の高い作業を得る目的で、さまざまな優先度レベル \(または上記\) で保留中の作業が見られるかどうかを JavaScript コードが判断する手段を提供します。 `isTaskScheduledAtPriorityOrHigher`  
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

### pageHandlesAllApplicationActivations  

:::row:::
   :::column span="":::
      すべてのアクティブ化イベント \(通知やピン留めされたタイルのクリックなど) の前に、開始パスの更新 (ページの再読み込み) を回避するために使用されます。  
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
      | ブール値 | 常に開始パスの更新 (ページの再読み込み) をスキップし、代わりにアクティブ化されたイベントの発生 `MSApp.pageHandlesAllApplicationActivations(true)` に直接 `WebUIApplication` ジャンプするために使用します。  すべてのページでアクティブ化イベントを個別に処理する必要があります。  このメソッドを定義することで、アクティブ化されたイベント `true` \(通知\など) をクリックすると、再読み込みはトリガーされません。これは、ページの再読み込みを回避する単一ページ アプリにとって不可欠です。  |  
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

### suppressSubdownloadCredentialPrompts  

:::row:::
   :::column span="":::
      リソースのダウンロード中に、アプリが認証プロンプトを抑制するかどうかを制御します。  
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
      | ブール値 | true に設定すると、認証プロンプトが表示される可能性が抑制されます。  値 false は、ユーザーからの潜在的な認証プロンプトを抑制する必要があります。  |  
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
      
      この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中にアプリが潜在的な認証プロンプトを抑制するかどうかを制御します。  既定の動作では、資格情報の入力を抑制しません。  
      
      `suppressSubdownloadCredentialPrompts` は、メール アプリ \(各画像が認証を必要とする多数の画像を含むニュースレターを含む可能性がある) など、認証を必要とするリソースが過剰に読み込まれる可能性があるアプリで使用することを目的としています。  
      
      資格情報の入力を求めるメッセージを表示しない場合、認証を必要とするリソースにアクセスするときにサーバーに認証するためのダイアログは表示されません。また、リソースはダウンロードされません。  プロキシ認証やクライアント認定要求ダイアログなどの他のプロンプトに影響を与えるのではなく `suppressSubdownloadCredentialPrompts` 、XHR にも影響を与える点に注意してください。  
      
      要素でホスト `suppressSubdownloadCredentialPrompts` されているコンテンツを含め、アプリケーションのすべてのコンテンツに影響を与える点に注意 `webview` してください。  
      
      > [!IMPORTANT]
      > 資格情報プロンプトの決定はキャッシュされます。  したがって、資格情報のプロンプトを抑制するとすぐに有効になりますが、表示を抑制した後で資格情報のプロンプトを有効にする場合は、ドキュメントの再読み込みを有効にする必要があります。  
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

### terminateApp  


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
      | エラー | 終了 `Error` をトリガーしたエラーを記述するために使用できるオブジェクト。  オブジェクトには、番号、説明、およびスタックプロパティが含まれている必要があります。オブジェクトにこれらのプロパティが含まれている場合、エラー レポート `Error` は生成されません。  |  
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
      
      報告された問題がアプリの上位 5 つの問題の 1 つになると、アプリの [品質] ページ `terminateApp` に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      この例では、 `terminateApp` 例外が発生した場合に呼び出します。  例外をキャッチ `Error` するときに指定されたオブジェクトを使用します。  
      
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

### MSApp 定数  

:::row:::
   :::column span="":::
      、、、に関連付けられている許可 `execAsyncAtPriority` `execAtPriority` された優先度 `getCurrentPriority` の値 `isTaskScheduldAtPriorityOrHigher` 。  
   :::column-end:::
   :::column span="":::
      #### 現在の顧客  
      
      `current`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切なメソッド \(See also section\) と一緒に使用すると、メソッドは要求された操作を実行するときに現在のコンテキスト優先順位 `current` を使用します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 高  
      
      `high`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切 `high` なメソッド \(See also section\) と一緒に使用する場合、メソッドは要求された操作を実行するときに通常より高い優先度を使用し、既存の通常の優先度が動作する前に操作をディスパッチします。  |  
   :::column-end:::
   :::column span="":::
      #### アイドル  
      
      `idle`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切 `ideal` なメソッド \(See also section\) と一緒に使用する場合、メソッドは要求された操作を実行するときに通常より低い優先度を使用し、既存の通常の優先度の処理の後に操作をディスパッチします。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 通常  
      
      `normal`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切なメソッド (「関連」セクションを参照) と一緒に使用すると、要求された操作を実行するときに、メソッドは通常の既存の優先度 `normal` を使用します。  |  
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

## MSAppAsyncOperation  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### start  

:::row:::
   :::column span="":::
      を起動 `MSAppAsyncOperation` します。  
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
      
      `error` property  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMError | のエラーを表します `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` property  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | 完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` property  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | 中にエラーが発生した場合にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` です。  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` property  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Number | JavaScript を使用して Windows アプリ内の非同期操作の状態を表します。  値は次のとおりです。 `Started[0]` `Completed[1]` , , `Error[2]` .  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` property  
      
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
