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
# MSApp

MSApp オブジェクトとそのメンバーは、JavaScript を使った Windows アプリでのみサポートされます (PWAs を含む Windows API 機能へのアクセスなど)。 MSApp オブジェクトは、ms appx URI スキームを使って読み込まれた Windows アプリの HTML ドキュメントのローカルコンテキストにのみ存在します。それ以外の場合、オブジェクトは存在しません (そのため、そのメソッドとプロパティはありません)。

[Blob](https://developer.mozilla.org/docs/Web/API/Blob)と[msstream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)オブジェクトを作成するためのヘルパー関数を提供します。

```javascript
var result = MSApp.method;
```

| | |
| :--- | :--- |
| [**メソッド**](#msapp-methods) | [Cleartemporarywebdataasync](#cleartemporarywebdataasync)、 [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)、 [createDataPackage](#createdatapackage)、 [createDataPackageFromSelection](#createdatapackagefromselection)、 [createFileFromStorageFile](#createfilefromstoragefile)、 [createstreamfrominputstream](#createstreamfrominputstream)、 [execAsyncAtPriority](#execasyncatpriority)、 [execatpriority](#execatpriority)、 [getcurrentpriority](#getcurrentpriority)、 [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)、[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)、 [getViewId](#getviewid)、 [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher)、 [pagehandlesallapplicationactivations アクティブ](#pagehandlesallapplicationactivations)化、 [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts)、 [terminateApp](#terminateapp)。 |

| | |
| :--- | :--- |
| [**定数**](#msapp-constants) | [current](#current)、 [high](#high)、 [idle](#idle)、 [normal](#normal)。|

| | |
| :--- | :--- |
| [**MSAppAsyncOperation**インターフェイス](#msappasyncoperation) | [start](#start) |

## MSApp のメソッド

### clearTemporaryWebDataAsync 
アプリまたは[WebView](../../webview.md)のキャッシュと indexedDB データをクリアします。

```javascript
var retval = MSApp.clearTemporaryWebDataAsync(#); 
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
種類[`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)

非同期操作を表します。

### createBlobFromRandomAccessStream
オブジェクトから[Blob](https://developer.mozilla.org/docs/Web/API/Blob)を作成 [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) します。 このメソッドは、アプリ内のオブジェクトを処理するときに使用 `IRandomAccessStream` し、ストリームから W3C ベースのオブジェクトを作成するために使います。 Blob を作成したら、 [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader)、 [URL api](https://developer.mozilla.org/docs/Web/API/URL)、 [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)と共に使うことができます。 

```javascript
var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
```

#### パラメーター

`type` チェックイン

|種類 | 説明 |
|:---- |:--- |
|String | データのコンテンツタイプ。 この文字列は、RFC 2616 のセクション3.7 で定義されているメディアタイプトークンで指定された形式である必要があります。

`stream` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)が Blob に格納されます。

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|ラージ | ストリームを含む新しい blob オブジェクト。

#### 例外
|エラー | 状況 |
|:---- |:--- |
|TypeMismatchError | ノードの型は、予期されるパラメーターの型と互換性がありません。 Internet Explorer 10 より前のバージョンの場合は、TYPE_MISMATCH_ERR が返されます。

#### 注釈
Window オブジェクトの MSApp 名前空間を使って、Windows ランタイム型から Blob を作成します。 このメソッドは、実質的には、指定されたオブジェクトに対するライトラッパーである blob を作成 [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) します。 Blob はこのストリームの有効期間を所有しており、blob が破棄されるとストリームは閉じられます。 

#### 例

```javascript
var randomAccessStream = dataPackage.GetData("image/bmp");
var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});

document.getElementById("imagetag").src = url; 
```

### createDataPackage
ユーザーまたはアプリケーションが指定した範囲を、共有可能な HTML フラグメントに変換します。

```javascript
var retVal = MSApp.createDataPackage(object); 
```

#### パラメーター
`object` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | この範囲は、選択オブジェクトから、または手動で作成することができ `window.selection.getRangeAt(0)` ます。

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|任意 | 指定した範囲の HTML マークアップが含まれています。

#### 注釈
このメソッドは、 [TextRange](/uwp/api/windows.ui.xaml.documents.textrange)ではなく、[ドキュメントオブジェクトモデル (DOM) 範囲](https://developer.mozilla.org/docs/Web/API/Range)のみをサポートしています。 指定した範囲の返されるデータパッケージには、クリップボード形式の HTML マークアップが含まれています。

返されるデータパッケージに使用できるプロパティはありません。

### createDataPackageFromSelection 
ユーザーまたはアプリケーションの選択範囲を、共有可能な HTML フラグメントに変換します。

```javascript
var retVal = MSApp.createDataPackageFromSelection(); 
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|任意 | 指定した範囲の HTML マークアップが含まれています。

#### 注釈
選択されたデータパッケージには、クリップボード形式の HTML マークアップが含まれています。 アプリケーションの UI 内の任意の場所でユーザーが選択されていない場合、は `createDataPackageFromSelection` null を返します。

返されるデータパッケージに使用できるプロパティはありません。
 
### createFileFromStorageFile 
WinRT を[WinRT](/uwp/api/) [`StorageFile`](/uwp/api/windows.storage.storagefile) 標準の W3C オブジェクトに変換 [`File`](https://developer.mozilla.org/docs/Web/API/File) します。

```javascript
var retVal = MSApp.createFileFromStorageFile(storageFile); 
```

#### パラメーター
`storageFile` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | ストレージファイルが格納されます。

#### 例外
|エラー | 状況 |
|:---- |:--- |
|TypeMismatchError | 指定された W3C ファイル参照は無効です。 Internet Explorer 10 より前のバージョンの場合は、TYPE_MISMATCH_ERR が返されます。

### createStreamFromInputStream  

からを作成 [`MSStream`](https://msdn.microsoft.com/library/hh772328) [`InputStream`](https://msdn.microsoft.com/library/hh772327) します。  


```javascript
var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
```

#### パラメーター
`type` チェックイン

|種類 | 説明 |
|:---- |:--- |
|DOMString | データのコンテンツタイプ。 この文字列は、RFC 2616 のセクション3.7 で定義されているメディアタイプトークンで指定された形式である必要があります。 ([「MIME の種類、](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types) ie、テキスト/プレーン、テキスト/html、画像/jpeg、画像/ogg、音声/mpeg、オーディオ/ビデオ、音声/ビデオ、音声/、audio/*、video/mp4 など)」を参照してください。 

`inputStream` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | は [`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream) 、に保存され `MSStream` ます。

#### 注釈
このメソッドは、コンテンツの種類と参照を受け取り `IInputStream` ます。 次に、メソッドは、渡された stream 参照が型のインスタンスであり、存在しない場合は、スローされたことを確認し `IInputStream` `DOMException TYPE_MISMATCH_ERR` ます。 エラーが発生しない場合は、 `createStreamFromInputStream` `MSStream` (入力から) を作成します。

#### 例
を `IInputStream` 使用してを作成でき `MSStream` ます。 `MSStreams`本来は1回限りのオブジェクトであるため、で作成されたすべての url は、 `URL.createObjectURL` イメージ要素によって最初に解決された時点で失効されます。 さらに、ストリームを使用した後、このオブジェクトの2番目の URL への要求は失敗します。

```javascript
var inputStream = myInputStream; //get InputStream from socket API, etc.
var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
document.getElementById("imagetag").src = URL.createObjectURL(stream); 
```

### execAsyncAtPriority 
指定した優先度に従って、後で実行されるようにコールバックをスケジュールします。 

```javascript
MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
```

#### パラメーター
`asynchronousCallback` チェックイン

|種類 | 説明 |
|:---- |:--- |
|機能 | 非同期的に実行されるコールバック関数。指定した優先度の優先順位でディスパッチされます。

`priority` チェックイン

|種類 | 説明 |
|:---- |:--- |
|DOMString | AsynchronousCallback コールバックが実行されるコンテキストの優先度の値。 [Msapp の定数](#msapp-constants)を参照してください。

`args` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | SynchronousCallback callback 関数 (パラメーター1およびオン) に渡されるオプションの連続する引数。

#### 戻り値
このメソッドに戻り値はありません。

#### 注釈
指定した `asynchronousCallback` コールバック関数は、後で非同期的に実行されます。 `asynchronousCallback` 指定した優先順位に従ってディスパッチされます。 通常の優先度は、既存のメソッドと同じです [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 。 コールバックが実行されると、コールバックの実行中に、現在のコンテキスト優先順位が、指定された priority パラメーター値に設定されます。

Callback パラメーターには、 `asynchronousCallback` 任意の関数を指定できます。 パラメーターの後に引数が指定された場合は、 `priority` すべてコールバック関数に渡されます。

このように `execAtPriority` 、callback 関数によって返されるオブジェクト `asynchronousCallback` は無視されます (これによって返されることはありません `execAsyncAtPriority` )。

### Exec優先度 
指定したコンテキスト優先順位で、指定したコールバック関数を実行します。

```javascript
var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
```

#### パラメーター
`synchronousCallback` チェックイン

|種類 | 説明 |
|:---- |:--- |
|機能 | 指定した優先度のコンテキストの優先順位で、同期的に実行されるコールバック関数。

`priority` チェックイン

|種類 | 説明 |
|:---- |:--- |
|DOMString | コールバック関数の実行時に現在のコンテキスト優先順位値が設定される、指定された優先度の値 `synchronousCallback` 。 [Msapp の定数](#msapp-constants)を参照してください。

`args` チェックイン

|種類 | 説明 |
|:---- |:--- |
|任意 | コールバック関数に渡されるオプションの連続する引数 `synchronousCallback` (パラメーター1と on)。

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|任意 | コールバックの戻り値 (該当する場合) を返し `synchronousCallback` ます。

#### 注釈
指定した `synchronousCallback` コールバックメソッドは、同期的に実行されます。 指定したコールバック関数の期間について、現在のコンテキストの優先度が、指定された priority 値 (priority 引数で指定) に変更されます。 コールバック関数の実行が終了すると、呼び出しの前の値が優先され `execAtPriority` ます。 戻り値は、 `execAtPriority` (指定されているように) コールバックメソッドの戻り値です。
 
Callback パラメーターには、 `synchronousCallback` 任意の関数を指定できます。 Priority パラメーターの後に引数を指定すると、指定したコールバックメソッドに渡されます。 Callback パラメーターが値を返す場合、この値も戻り値になり `execAtPriority` ます。

#### 例

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

### getCurrentPriority 
現在のコンテキストの優先度を返します。

```javascript
var retval = MSApp.getCurrentPriority();
```

#### パラメーター
ありません。 

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|DOMString | 戻り値は、、またはのいずれかの文字列です `MSApp.HIGH` `MSApp.NORMAL` `MSApp.IDLE` 。

#### 注釈
このメソッドは現在のコンテキスト優先度 ( [`MSApp Constants`](#msapp-constants) を参照) を返します。これは、およびとの間で変更することができ `execAtPriority` `execAsyncAtPriority` ます。

#### 例

```javascript
if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
  // YOUR CODE HERE
}
```

### getHtmlPrintDocumentSource  

廃止された同期 API。 Windows 10 の場合は、を参照してください `getHtmlPrintDocumentSourceAsync` 。 Windows 8 アプリと8.1 アプリの場合は、 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)の MSDN エントリを参照してください。  

### getHtmlPrintDocumentSourceAsync
印刷対象のソースコンテンツを返します。

#### パラメーター
`htmlDoc` チェックイン

|種類 | 説明 |
|:---- |:--- |
|Document | 印刷する HTML 文書。 これは、ルートドキュメント、iframe 内のドキュメント、ドキュメントフラグメント、または SVG ドキュメントにすることができます。 HtmlDoc は、要素ではなく、文書である必要があることに注意してください。

#### 例 1

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

#### 例 2

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

### getViewId 
複数のウィンドウのサポート。 

> [!NOTE] 
> Win 8.1 JavaScript の UWP アプリでは、depricated になった MSApp DOM Api を使用して複数のウィンドウがサポートされていました。 Windows 10 では、、、 `window.open` `window` および新しいを使用 `MSApp.getViewId` します。

| 説明 |Windows 10 | Windows 8.1 |  
|:---- |:---- |:--- |  
| 新しいウィンドウを作成する | [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) | [`MSApp.createNewView`](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
|新しい window オブジェクト | [`window`](https://developer.mozilla.org/docs/Web/API/Window) |[`MSAppView`](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  

```javascript
var retval = MSApp.getViewId(window); 
```

#### パラメーター
`window`

|種類 | 説明 |
|:---- |:--- |
|DOMString | DOM ドキュメントを含むウィンドウを表すオブジェクト。 | 

#### 戻り値

`viewId`

|型 | 説明 |
|:---- |:--- |
|Number | さまざまな api と共に使うことができ [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) ます。 

#### 注釈
[`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) [`window`](https://developer.mozilla.org/docs/Web/API/Window) 新しいウィンドウの作成にはを使用しますが、WinRT api を操作するには、API を追加し `MSApp.getViewId` ます。 `window`パラメーターとしてオブジェクトを受け取り、 `viewId` さまざまな api で使うことができる数値を返し [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) ます。 

##### Visibility の遅延 
WinRT のビューは通常は非表示になり、エンド開発者は、 `TryShowAsStandaloneAsync` 完全に準備ができたらビューを表示するために使用されます。 Web 環境では、 `window.open` ウィンドウがすぐに表示され、エンドユーザーはコンテンツの読み込みとレンダリングを監視できます。 新しい windows で WinRT のビューを操作し、すぐに表示されないようにするには、オプションを追加し `window.open` ます。 次に、例を示します。
`let newWindow = window.open("https://example.com", null, "msHideView=yes");`

##### 主要なウィンドウの相違点
OS によって最初に開かれるプライマリウィンドウは、開かれるセカンダリウィンドウとは動作が異なります。 

|説明 | プライマリ | セカンダリ |
|:---- |:--- |:--- |
|ウィンドウ。開く | 許可されます | Disallowed |
|ウィンドウを閉じます。 | アプリを閉じる | ウィンドウを閉じる |
| ナビゲーションの制限 | ACUR のみ | 制限なし |

セカンダリウィンドウを開くことを許可しない制約は、[フィードバック](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)に応じて将来変更される可能性があります。

##### 同じ元の通信制限 
同期、同じ元のウィンドウ、クロスウィンドウ、スクリプト呼び出しの適切なサポートを防ぐ困難な技術上の問題があります。 同じ元のウィンドウを開くと、1つのウィンドウのスクリプトは、他のウィンドウで関数を直接呼び出すことができ、一部の呼び出しが失敗します。 `postMessage` 通話は正常に機能します。可能であれば、問題を解決するために推奨される方法です。 この問題を改善するための作業は進行中です。


### isTaskScheduledAtPriorityOrHigher 
指定した優先度レベル以上で、保留中の作業があるかどうかを示すブール値を返します。

```javascript
var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
```

#### パラメーター
`priority` チェックイン

|種類 | 説明 |
|:---- |:--- |
|DOMString | 未解決のキューに入っている作業を照会するには、priority の値 ( [Msapp 定数](#msapp-constants)を参照) を指定します。

#### 戻り値
|型 | 説明 |
|:---- |:--- |
|ブール値 | `true`指定した優先度レベル以上のキューに入っている作業があるかどうかを返し `false` ます。

#### 注釈
この `isTaskScheduledAtPriorityOrHigher` メソッドは、javascript コードがさまざまな優先度レベル (以上) に保留中の作業があるかどうかを判断するための手段を提供します。これにより、呼び出し元の javascript コードが優先度の高い作業によって得られることが意図されています。

#### 例

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

### pageHandlesAllApplicationActivations アクティベーション
すべてのアクティブ化イベント (ie) の前に、開始パス (ページの読み込み) が更新されないようにするために使います (通知またはピン留めされたタイルをクリックします)。 

#### パラメーター

|種類 | 説明 |
|:---- |:--- |
ブール値 | `MSApp.pageHandlesAllApplicationActivations(true)`開始パス (ページの再読み込み) の更新を常にスキップして、アクティブ化されたイベントを発生させるには直接ジャンプし `WebUIApplication` ます。 すべてのページで、アクティブ化イベントを個別に処理する必要があります。 このメソッドをとして定義することによって `true` 、アクティブ化されたイベント (notificaiton など) をクリックしても、ページの読み込みを回避する単一ページアプリにとって重要な再読み込みはトリガーされません。

#### 例 

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

### suppressSubdownloadCredentialPrompts 
アプリで、リソースのダウンロード中に認証プロンプトが表示されるかどうかを制御します。

```javascript
MSApp.suppressSubdownloadCredentialPrompts(suppress); 
```

#### パラメーター
`suppress` チェックイン

|種類 | 説明 |
|:---- |:--- |
|ブール値 | 値が true の場合、認証のためのプロンプトは表示されません。 値が false の場合、ユーザーからの認証を求めるメッセージは表示されません。

#### Returan 値
なし。

#### 注釈
この `suppressSubdownloadCredentialPrompts` メソッドは、リソースのダウンロード中に、アプリで認証プロンプトが表示されないようにするかどうかを制御します。 既定の動作では、資格情報の入力は抑制されません。

`suppressSubdownloadCredentialPrompts` メールアプリなど、認証が必要な大量のリソースを読み込む可能性があるアプリ (各画像には、認証が必要な数の画像を含むニュースレターが含まれている場合があります) を使うことを目的としています。

資格情報の入力を求めるメッセージは、認証を必要とするリソースにアクセスするときに、サーバーに対して認証するためのダイアログを表示せず、リソースはダウンロードされません。 `suppressSubdownloadCredentialPrompts`プロキシ認証やクライアント証明要求のダイアログなどの他の確認できるプロンプトや、XHR への影響はありませんので注意してください。

`suppressSubdownloadCredentialPrompts`要素でホストされているコンテンツを含む、アプリケーション内のすべてのコンテンツに影響を与えることに注意 `webview` してください。
 
**重要:** 資格情報の確認の判断がキャッシュされます。 そのため、資格情報を抑制するためのプロンプトはすぐに有効になります。これを抑制した後で資格情報のプロンプトが表示されるようにするには、ドキュメントの再読み込みが必要な場合があります

#### 例

```javascript
/ Set to true to suppress potenial credential prompts:
MSApp.suppressSubdownloadCredentialPrompts(true); 
// Now one can load content or navigate iframe/webview to some other site.
```

### terminateApp
現在のアプリケーションを終了し、エラーレポートを生成します。 

```javascript
MSApp.terminateApp(error); 
```

#### パラメーター
`error` チェックイン

種類 | 説明 |
|:---- |:--- |
|エラー | `Error`終了をトリガーしたエラーを説明するために使うことができるオブジェクトです。 このオブジェクトには、 `Error` 数値、説明、スタックの各プロパティが含まれている必要があります。これらのプロパティがオブジェクトに含まれていない場合、エラーレポートは生成されません。

#### 戻り値
なし。

#### 注釈
この問題が報告された場合は、 `terminateApp` アプリの上位5つの問題のいずれかになります。アプリの [品質] ページに表示されます。

#### 例
次の例 `terminateApp` は、例外が発生したときに呼び出されます。 `Error`例外をキャッチするときに指定されたオブジェクトを使います。 

```javascript
try {  
        var obj2 = null;  
        obj2.val = 5;  
    }  
    catch(e) {  
        window.MSApp.terminateApp(e);  
    }  
```

### MSApp の定数
`execAsyncAtPriority`、、 `execAtPriority` `getCurrentPriority` 、およびに関連付けられた優先順位の値 `isTaskScheduldAtPriorityOrHigher` 。

#### 現在の顧客
`current`

|種類 | 説明 |
|:---- |:--- |
|DOMString | `current`適切なメソッド (「セクション」も参照) では、要求された操作を実行するときに、現在のコンテキストの優先度を使用します。

#### 高
`high`

|種類 | 説明 |
|:---- |:--- |
|DOMString | `high`適切なメソッド (「セクション」も参照) では、要求された操作を実行するときに、メソッドは通常の優先度よりも使用されます。また、既存の通常の優先順位の作業の前に操作がディスパッチされます。

#### アイドル
`idle`

|種類 | 説明 |
|:---- |:--- |
|DOMString | `ideal`適切なメソッド (「セクション」も参照) で使用すると、要求された操作を実行するときに、メソッドは通常の優先度よりも低い優先度を使用し、既存の通常の優先度作業の後に操作をディスパッチします。

#### 通常
`normal`

|種類 | 説明 |
|:---- |:--- |
|DOMString | `normal`適切なメソッド (「セクション」も参照) で使用すると、要求された操作を実行するときに、メソッドは既存の標準優先度を使います。

#### 例

```javascript
if (window.MSApp.CURRENT) {
  document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
}
```

#### 要件
|.IDL | Mshtml.dll |
|:---- |:--- |

## MSAppAsyncOperation

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```

### start
を起動 `MSAppAsyncOperation` します。

```javascript
var retval = MSAppAsyncOperation.start();
```

#### パラメーター
ありません。

#### 戻り値
なし。

#### プロパティ
`error` プロパティー

|種類 | 説明 |
|:---- |:--- |
|DOMError | のエラーを表し `MSAppAsyncOperation` ます。

```javascript
p = object.error
```

`oncomplete` プロパティー

|種類 | 説明 |
|:---- |:--- |
|EventHandler | イベントハンドラーを完了時に設定するためのプロパティ `MSAppAsyncOperation` です。

```javascript
p = object.oncomplete
```

`onerror` プロパティー

|種類 | 説明 |
|:---- |:--- |
|EventHandler | 中にエラーが発生したときにイベントハンドラーを設定するプロパティ `MSAppAsyncOperation` 。

```javascript
p = object.onerror
```

`readyState` プロパティー

|種類 | 説明 |
|:---- |:--- |
|Number | JavaScript を使った Windows アプリ内の非同期操作の状態を表します。 値は次のとおりです。開始 [0]、完了 [1]、エラー [2]。

```javascript
p = object.readyState
```

`result` プロパティー

|種類 | 説明 |
|:---- |:--- |
|任意 |の結果を表し `MSAppAsyncOperation` ます。

```javascript
p = object.result
```
