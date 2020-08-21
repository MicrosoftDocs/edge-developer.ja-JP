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
# MSApp  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

MSApp オブジェクトとそのメンバーは、JavaScript \(Windows API へのアクセスを含む) を使用する Windows アプリでのみサポートされます。  MSApp オブジェクトは、ms-appx URI スキームを使用して読み込む Windows アプリの HTML ドキュメントのローカル コンテキストにのみ存在します。それ以外の場合、オブジェクトが存在しない (メソッドとプロパティは使用できません)。  

[BLOB](https://developer.mozilla.org/docs/Web/API/Blob)オブジェクトと MSStream オブジェクトを作成できる、ヘルプア[ーカー関数を](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)提供します。  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [メソッド](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      clearTemporaryWebDataAsync、createBlobFromRandomAccessSream、createDataPackage、createDataPackageFromSelection、createFileFromStorageFile、createStreamFromInputStream、execAsyncAtPriority、execAtPriority、getCurrentP [createDataPackage](#createdatapackage) [riority,](#getcurrentpriority) [createDataPackageFromSelection](#createdatapackagefromselection) [getHtmlPrintDocumentSource,](#gethtmlprintdocumentsource)[getHtmlPrintDocumentSourceAsynce,](#gethtmlprintdocumentsourceasync) [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream) [getViewId,](#getviewid) [createFileFromStorageFile](#createfilefromstoragefile) [isTaskScheduledAtPriorityOrHigher,](#istaskscheduledatpriorityorhigher) [pageHandlesAllApplicationActivations,](#pagehandlesallapplicationactivations) [suppressSubdownloadCredentialPrompts,](#suppresssubdownloadcredentialprompts) [terminateApp.](#terminateapp) [clearTemporaryWebDataAsync](#cleartemporarywebdataasync) [createStreamFromInputStream](#createstreamfrominputstream) [execAsyncAtPriority](#execasyncatpriority) [execAtPriority](#execatpriority)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [定数](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      [現在](#current)、 [高](#high), [アイドル](#idle), [通常](#normal)。  
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

## MSApp のメソッド  

### clearTemporaryWebDataAsync  

:::row:::
   :::column span="":::
      アプリまたは WebView のキャッシュおよびインデックス付きDB データ [をクリアします](../../webview.md)。  
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
      
      非同期操作を表します。  
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
      [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)オブジェクトから[Blob](https://developer.mozilla.org/docs/Web/API/Blob)を作成します。  ストリームから W3C ベースのオブジェクトを作成するために、アプリ内の `IRandomAccessStream` オブジェクトを操作するときに使用する必要があります。  BLOB が作成されると、そのブローバは[FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API、XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/URL)[と一で使用できます](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。  
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
      | String | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクションで定義されるメディア タイプ トークンで指定された形式にする必要があります。  |  
      
      `stream` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | [Blob に保存する IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Blob | ストリームが含まれる新しい BLOB オブジェクト。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      | 例外 | 状況 |  
      |:---- |:--- |  
      | TypeMismatchError | ノードの種類は、パラメーターの種類と互換性がない。  10 より前のバージョン Internet Explorerでは、TYPE_MISMATCH_ERRが返されます。  |  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      ウィンドウ オブジェクトの MSApp 名前空間を使用して、Windows ランタイム タイプから Blob を作成します。  このメソッドにより、提供される [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) オブジェクト上に照明したビット ラッパーであるブローバが作成されます。  BLOB はこのストリームの有効期限を所有し、BLOB がストリーミングされるとストリームが閉じられます。  
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
      ユーザーまたはアプリケーションの指定された範囲を HTML フラグメントに変換し、共有できます。  
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
      | 任意 | この範囲は、選択オブジェクトから作成できます (例: `window.selection.getRangeAt(0)` または手動で作成することもできます)。  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | 指定した範囲の HTML マークアップを含みます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは[、ドキュメント オブジェクト モデル (DOM) 範囲のみをサポートし、テキスト範囲](https://developer.mozilla.org/docs/Web/API/Range)[にはサポートされません](/uwp/api/windows.ui.xaml.documents.textrange)。  指定した範囲における返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれている必要があります。  
      
      返されるデータ パッケージに利用できるプロパティがありません。  
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
      ユーザーまたはアプリケーションの選択範囲を共有できる HTML フラグメントに変換します。  
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
      | 任意 | 指定した範囲の HTML マークアップを含みます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      選択範囲の返されるデータ パッケージには、クリップボード形式の HTML マークアップが含まれている。  アプリケーションの UI 内の任意の場所にユーザー選択がない場合は、 `createDataPackageFromSelection` 戻されます `null` 。  
      
      返されるデータ パッケージに利用できるプロパティがありません。  
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
      [WinRT](/uwp/api/)ストレージ[ファイルを標準](/uwp/api/windows.storage.storagefile)の W3C ファイル オブジェクトに[変換](https://developer.mozilla.org/docs/Web/API/File)します。  
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
      | 任意 | ストレージ ファイルが格納されます。  |  
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
      | TypeMismatchError | 指定された W3C ファイル参照が無効です。  Internet Explorer 10 より前のバージョンの場合は `TYPE_MISMATCH_ERR` 、戻されます。  |  
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
      | DOMString | データのコンテンツ タイプ。  この文字列は、RFC 2616 のセクションで定義されるメディア タイプ トークンで指定された形式にする必要があります。  \([MIME の種類を参照]、次のようになります。"、"、"、"、"、"、以下の場合 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` ")  
      
      `inputStream` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | 格納[する IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`  |  
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
      
      このメソッドでは、コンテンツ タイプと参照が使用 `IInputStream` されます。  その後、メソッドは、種類のインスタンスであり、スローしている `IInputStream` 場合はスローが行われます `DOMException TYPE_MISMATCH_ERR` 。  エラーがない場合 `createStreamFromInputStream` は `MSStream` 、\(入力から) \を作成します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      作成 `IInputStream` に使用できます `MSStream` 。  一時使用オブジェクトは、イメージ要素によって解決されると、その一度に作成されたすべての URI が `MSStreams` `URL.createObjectURL` 消消されます。  さらに、ストリームの使用後に、このオブジェクトに対する 2 番目の URL の要求が失敗します。  
      
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
      指定した優先度に従って後で実行されるコールバックをスケジュールします。  
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
      | 機能 | 非同期で実行するコールバック関数。指定の優先度でディスパッチされます。  |  
      
      `priority` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 非同期呼び出しコールバックが実行されるコンテキスト優先順値。  [MSApp 定数を参照してください](#msapp-constants)。  |  
      
      `args` [in]
      
      | 型 | 説明 |  
      |:---- |:--- |   
      | 任意 | 同期の Callback コールバック関数 \(パラメーター 1 など) にパラメーター 1 と合わされる、省略可能な一列の引数です。  |  
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
      
      提供された `asynchronousCallback` コールバック関数は非同期的に実行されます。  `asynchronousCallback` 指定された優先度に従ってディスパッチされます。  通常の優先度は既存の設定方法と [同等です](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 。  コールバックが実行されると、コールバックの実行中に現在のコンテキスト 優先度が指定された優先度パラメーター値に設定されます。  
      
      コール `asynchronousCallback` バック パラメーターには、任意の関数を指定できます。  パラメーター後に引数を指定した場合、それらの引数はすべてコールバック `priority` 関数に合わされます。  
      
      とは異なり、コールバック関数によって返されるオブジェクトは `execAtPriority` `asynchronousCallback` \(および返されるもの `execAsyncAtPriority` ではない)。  
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
      指定されたコンテキスト優先度で、指定されたコールバック関数を実行します。  
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
      | 機能 | 指定した優先度のコンテキスト 優先度で同期的に実行するコールバック関数。  |  
      
      `priority` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | コールバック関数の実行時に現在のコンテキスト優先度値が設定される指定した `synchronousCallback` 優先度値。  [MSApp 定数を参照してください](#msapp-constants)。  |  
      
      `args` [in]  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバック関数 \(パラメーター 1 など) にパラメーター 1 と計算される省略 `synchronousCallback` 可能な引数のシリーズ。  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 | コールバックの戻り `synchronousCallback` 値を返します (省可能な場合\)。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      提供されたコールバック メソッドは `synchronousCallback` 、同期的に実行されます。  現在のコンテキスト優先度は、提供されたコールバック関数の期間における指定された優先度の値 (優先度引数によって指定される) に変更されます。  コールバック関数の実行が完了すると、呼び出し前の前の値に優先度が返 `execAtPriority` されます。  戻り値はコールバック メソッド `execAtPriority` \(提供された\) の戻り値です。  
      
      コール `synchronousCallback` バック パラメーターには、任意の関数を指定できます。  優先度パラメーター後に引数が指定される場合、引数は指定されたコールバックメソッドに合格されます。  コールバック パラメーターが値を返すと、この値も戻り値 `execAtPriority` となります。  
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
      現在のコンテキスト 優先度を返します。  

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
      | DOMString | 戻り値は文字列の 1 つ `MSApp.HIGH` 、ついずれ `MSApp.NORMAL` かの文字列、つながりです `MSApp.IDLE` 。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      このメソッドは、現在のコンテキスト 優先度 [\(MSApp 定数](#msapp-constants)\を参照) を返します。これは、この値は 、または指定して変更 `execAtPriority` できます `execAsyncAtPriority` 。  
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

廃止された同期 API。  Windows 10 の場合は、参照してください `getHtmlPrintDocumentSourceAsync` 。  たとえばWindows 8 8.1 アプリの場合は [、getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。  

### getHtmlPrintDocumentSourceAsync  

:::row:::
   :::column span="":::
      印刷されるソース コンテンツを返します。  
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
      | Document | 印刷する HTML ドキュメント。  これは、ルート ドキュメント、iframe 内のドキュメント、ドキュメントのフラグメント、または SVG ドキュメントになります。  htmlDoc は要素でなくドキュメントである必要があることにごご確認ください。  |  
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
      > Win8.1 JavaScript UWP アプリでは、MSApp DOM API を使用して複数のウィンドウがサポートされています。これは、詳細になりました。  Windows 10 の場合は、使用 `window.open` `window` 、新しいバージョンを使用します `MSApp.getViewId` 。  
      
      | 説明 |Windows 10 | Windows 8.1 |  
      |:---- |:---- |:--- |  
      | [新しいウィンドウの作成] | [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) | [MSApp.createNewView](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
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
      | Number | [さまざまな Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API と共に使用できます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      [window.open](https://developer.mozilla.org/docs/Web/API/Window/open)と[ウィンドウを使用](https://developer.mozilla.org/docs/Web/API/Window)して新しいウィンドウを作成しますが、WinRT API を操作するには `MSApp.getViewId` 、API を追加します。  オブジェクトをパラ `window` メーターとして受け返し、 `viewId` さまざまな [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API で使用できる数値を返します。  
      
      *   [Visibility] (Visibility)  
          
          WinRT でのビューは通常どおり非表示に開始され、エンドデベロッパーは何かを使用してビューを完全に準備したとき `TryShowAsStandaloneAsync` などを使用します。  Web のワールドでは、ウィンドウがすぐに表示され、コンテンツが読み込みおよびレンダリングされるとエンド ユーザー `window.open` が見ることができます。  新しいウィンドウが WinRT のビューのような機能に機能し、直ちに表示されないようにするには、次のオプションが追加 `window.open` されています。  次に、例を示します。  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   プライマリ ウィンドウの違い  
          
          OS でまず開かれるプライマリ ウィンドウは、第 2 のウィンドウとは異なります。  
          
          | 説明 | プライマリ | セカンダリ |  
          |:---- |:--- |:--- |  
          | window.open | 許可されます | Disallowed |  
          | window.close | アプリを閉じる | ウィンドウを閉じる |  
          | ナビゲーションの制限 | ACUR のみ | 制限なし |  
          
          セカンダリ ウィンドウを開くことを許可しない制限は、フィードバックに応じて、以降で変わる [可能性があります](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。  
      
      *   同じ Origin Communication の制限  
          
          同期、同じ場所、クロスクリプト通話に関して、同期に問題がある可能性のあるテクニカルサポートが発生します。  同じ発信先のウィンドウを開くと、一度のウィンドウでスクリプトを使用すると、他のウィンドウで関数を直接呼び出すことができます。それらの呼び出しの一部は失敗します。  `postMessage` 通話は最も有効であり、可能な場合に推奨される方法です。  この問題を改善する作業は進行中です。  
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
      指定した優先度レベルまたはそれ以降に保留中の作業があるかどうかを示すブール値を返します。  
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
      | DOMString | 優先度レベルおよび上位レベルと上位のキューに対するクエリをクエリする優先度の値 [\(MSApp 定](#msapp-constants)数 \)  |  
   :::column-end:::
   :::column span="":::
      **戻り値**  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | ブール値 | 指定された優先度レベルまたは上のキューに入れた作業があるかどうか `true` を `false` 返します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例外**  
      
      なし。  
   :::column-end:::
   :::column span="":::
      **注釈**  
      
      この `isTaskScheduledAtPriorityOrHigher` メソッドは、JavaScript コードの呼び出しにおけるさまざまな優先度レベル \(または上\) で作業が保留中であるかどうかを判定するためのメーリングを提供します。これにより、JavaScript コードを呼び出す可能性があるため、より優先度の高い作業に対して黄色の作業を決定できます。  
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
      アクティブなイベント \(通知をクリックしたり、ピンンなタイルをクリックするなど) の前にスタート パス (ページの再読み込み) を回避するために使用します。  
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
      | ブール値 | 常に開始パス (ページの再読み込み) をスキップし、代わりにそのジャンプしてアクティブなイベントを `MSApp.pageHandlesAllApplicationActivations(true)` `WebUIApplication` 実行するのに使用します。  すべてのページでライセンス認証イベントを個別にハンドルする必要があります。  この方法を定義することで、アクティブなイベント \(notification\など) をクリックしても再読み込みがトリロードされることはありません。ページの再読み込みを回避するため、単一ページアプリに対して必要 `true` なものは発生しません。  |  
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
      リソースのダウンロード中に考えられる認証プロンプトがアプリで表示されるかどうかを制御します。  
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
      | ブール値 | true の値が表示を指定すると、認証のプロンプトが表示されません。  False の値は、ユーザーからの認証プロンプトを表示しません。  |  
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
      
      このメソッドは、リソースのダウンロード時に認証プロンプトが表示を表示するかどうか `suppressSubdownloadCredentialPrompts` を制御します。  既定の動作では、資格情報のプロンプトを表示しないことです。  
      
      `suppressSubdownloadCredentialPrompts` は、アプリによって使用を行う場合の目的で、認証が必要な多数のリソース (メール アプリ \(この中にそれぞれ認証が必要な多数の画像を含むニュースレターが含まれている可能性があります)。  
      
      資格情報の確認を表示しないと、認証が必要なリソースにアクセスするときにサーバーに認証するためのダイアログが表示されず、リソースはダウンロードされません。  プロキシ認証やクライアントサーティフェイス要求のダイアログなど、考えられる他のプロンプトには影響しません `suppressSubdownloadCredentialPrompts` 。また、XHR に影響を受けません。  
      
      要素でホストされているコンテンツを含め、アプリケーションの `suppressSubdownloadCredentialPrompts` すべてのコンテンツに影響することにおおよできません `webview` 。  
      
      > [!IMPORTANT]
      > 資格情報プロンプトの決定がキャッシュされます。  そのため、資格情報プロンプトをいつでもたちに有効にし、そのまま使用するには、ドキュメントの再読み込みが必要になる場合があります。  
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
      | エラー | 終了したエラーを説明するの `Error` に使用できるオブジェクト。  オブジェクトには、数値、説明、およびスタック プロパティを含める必要があります。エラー レポートは、オブジェクトにこれらのプロパティが含まれていない場合 `Error` は生きません。  |  
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
      
      アプリの品質が上位 5 の問題の 1 つになった場合は、アプリの品質 `terminateApp` ページに表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **例**  
      
      この例では、 `terminateApp` 例外が発生した場合の呼び出しです。  例外 `Error` をキャッチすると、指定したオブジェクトが使用されます。  
      
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
      ユーザー、および関連付けられている `execAsyncAtPriority` 優先度 `execAtPriority` の値 `getCurrentPriority` 。 `isTaskScheduldAtPriorityOrHigher`  
   :::column-end:::
   :::column span="":::
      #### 現在の顧客  
      
      `current`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切な方法 \(セクション\) と一時に使用するとき、要求された操作を実行するときに、そのメソッドは現在のコンテキスト優先度 `current` を使用します。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 高  
      
      `high`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切な方法 \(セクション\) と一時に使用するとき、要求された操作を実行するときにこのメソッドは通常よりも高い優先度を使用し、既存の通常の優先度の処理が発生する前に操作を `high` ディスパッチします。  |  
   :::column-end:::
   :::column span="":::
      #### アイドル  
      
      `idle`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切な方法 \(Section\) と一時に使用するとき、要求された操作を実行するときにメソッドは通常よりも低いものを使用し、既存の通常の優先度の作業が完了した後、操作はディスパッ `ideal` チされます。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 通常  
      
      `normal`  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | DOMString | 適切な方法 (セクションを参照) と一時的に使用するとき、要求された操作を実行するときに、このメソッドは通常の優先度 `normal` を使用します。  |  
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
      開始します `MSAppAsyncOperation` 。  
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
      | DOMError | エラーを表します `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | 完了時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | EventHandler | エラー時にイベント ハンドラーを設定するプロパティ `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | Number | JavaScript を使用する Windows アプリでの非同期操作の状態を表します。  値には `Started[0]` 、、, `Completed[1]` , `Error[2]` .  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` プロパティ  
      
      | 型 | 説明 |  
      |:---- |:--- |  
      | 任意 |結果を表します `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
