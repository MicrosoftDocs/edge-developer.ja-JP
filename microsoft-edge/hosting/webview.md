---
description: WebView (EdgeHTML) コントロールを使用して、Windows 10 アプリの web コンテンツをホストする
title: Microsoft Edge WebView for Windows 10 アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: x-ms-webview、MSHTMLWebViewElement、webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 08efb1bb87877e0b11cbc3bee1061f9be6c9ab3f
ms.sourcegitcommit: 831fc41ea347e2d1160b1804fb5e5a427dc3070d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "10629550"
---
# Windows 10 アプリ用 WebView (EdgeHTML)

WebView (EdgeHTML) コントロールでは、Windows 10 アプリで web コンテンツをホストすることができます。 

これは、次に説明するように、XAML 要素 ([ユニバーサル Windows プラットフォーム (UWP) アプリ](/uwp/api/Windows.UI.Xaml.Controls.WebView)と[WINDOWS フォームと WPF デスクトップアプリケーション](/windows/communitytoolkit/controls/wpf-winforms/webview)の場合)、または HTML 要素 (/DOM オブジェクト) (MSHTMLWebViewElement) として使うことができます。

| | |
|-|-|
| [**イベント**](#events) | [departingFocus](#departingfocus)、 [mswebview・ fullfullscreenelementchanged](#mswebviewcontainsfullscreenelementchanged)、 [mswebviewcontentloading](#mswebviewcontentloading)、 [mswebviewdomcontentloaded](#mswebviewdomcontentloaded)、 [MSWebViewFrameContentLoading](#mswebviewframecontentloading)、 [mswebviewMSWebViewFrameNavigationStarting](#mswebviewframedomcontentloaded)、 [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected)、 [MSWebViewFrameNavigationCompleted](#mswebviewframenavigationcompleted) [mswebviewnavigationcompleted](#mswebviewnavigationcompleted)、mswebviewnavigationstarting、mswebviewnavigationstarting、 [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested)mswebviewの使い方[、](#mswebviewpermissionrequested)mswebviewprocessexMSWebViewFrameNavigationCompleted、 [MSWebViewProcessExited](#mswebviewprocessexited) [MSWebViewWebResourceRequested](#mswebviewwebresourcerequested)、 [mswebviewscriptnotify](#mswebviewscriptnotify)、 [MSWebViewUnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying)、 [MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsupportedurischemeidentified)、 [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified) [MSWebViewFrameNavigationStarting](#mswebviewframenavigationstarting) [MSWebViewNavigationStarting](#mswebviewnavigationstarting)
| [**メソッド**](#methods) | [Addweballowedobject](#addweballowedobject)、 [buildlocalstreamuri](#buildlocalstreamuri)、 [capturePreviewToBlobAsync](#capturepreviewtoblobasync)、 [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync)、 [invokeScriptAsync](#invokescriptasync)、 [getDeferredPermissionRequests](#getdeferredpermissionrequests)、 [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid)、 [goBack](#goback)、 [goforward](#goforward)、 [navigate](#navigate)、 [navigateFocus](#navigatefocus)、 [navigateTolocalStreamUri](#navigatetolocalstreamuri)、 [navigateToString](#navigatetostring)、 [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage)、 [refresh](#refresh)、 [stop](#stop) |
| [**プロパティ**](#properties) | [canGoBack](#cangoback)、 [canGoForward](#cangoforward)、 [fullscreenelement](#containsfullscreenelement)、 [documenttitle](#documenttitle)、 [height](#height)、 [process](#process)、 [settings](#settings)、 [src](#src)、 [width](#width) |

## 構文

```js
// Feature detect for webview support
if (MSHTMLWebViewElement) {
    let wv = document.createElement('x-ms-webview'); // Use CSS to set width, height and other styles
    wv.navigate("https://www.example.com");
    document.body.appendChild(wv);
}
```

## 注釈

### WebView と iframe

標準 HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)要素と同様に、WebView を使って、アプリパッケージから HTTP とローカルページ (*ms appx-web///*) 経由でリモートページを読み込むことができます。 ただし、WebView にも次のような方法があります。

 - [Applicationdata](/uwp/api/Windows.Storage.ApplicationData) (ローカル、ローミング、temp) フォルダーと[メモリ内ストリーム](/microsoft-edge/hosting/webview#buildlocalstreamuri)*(ms-**ローカルストリーム:*////) からページとリソースをロードします。

 - ブラウザーのようなコントロールを提供します。これには、ナビゲーション履歴の[前後](#goback)[に移動](#goforward)したり、現在のページを[停止](#stop)または[更新](#refresh)したりすることができます。 

 - [Web コンテンツのスクリーンショットをキャプチャ](#capturepreviewtoblobasync)して、Windows 10 アプリ[共有](/windows/uwp/app-to-app/share-data)コントラクトを簡単に実装できます。

 - Webview 内で実行される JavaScript コード ([Mswebviewscriptnotify](#mswebviewscriptnotify)) をアプリに対して実行し、アプリが Webview ([invokeScriptAsync](#invokescriptasync)) 内で javascript を実行できるようにします。

 - 適切に調整された webview コンテンツイベントを提供します。
    
    WebView DOM イベント | 説明
    --------- | ------
    [MSWebViewNavigationStarting](#mswebviewnavigationstarting) | WebView が移動を開始していることを示します。
    [MSWebViewContentLoading](#mswebviewcontentloading) | HTML コンテンツがダウンロードされ、コントロールに読み込まれます。
    [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded) | メイン DOM 要素の読み込みが完了したことを示します。
    [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted) | ナビゲーションが完了し、すべてのメディア要素がレンダリングされることを示します。
    [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified) | WebView でコンテンツが HTML ではなかった
    [UnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying) | WebView には、Windows *SmartScreen フィルター*によって安全でないと報告されたコンテンツの警告ページが表示されます。

    ...WebView に読み込まれる iframe コンテンツに対応する[イベント](#events)( [mswebview**Frame**navigationstarting 開始](#mswebviewframenavigationstarting)など) を含めます。

### 印刷

JavaScript を使った Windows アプリが印刷されると、 `<x-ms-webview>` タグが `<iframe>` 印刷前にタグに変換されます。 画面上での表示と印刷用の標準の違い以外に、要素に適用された CSS スタイル `<iframe>` は、から変換された元のスタイルに適用され `<iframe>` `<x-ms-webview>` ます。

### サービス員

[Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)(EdgeHTML 18) 以降では、 [Service worker は WebView コントロールでサポートされて](/microsoft-edge/dev-guide#service-workers)います (JavaScript を使った Microsoft Edge ブラウザーと Windows 10 アプリに加えています)。

x64 アプリアーキテクチャでは、サービスワーカーは WoW64 プロセスでサポートされていないため、ニュートラル (任意の CPU) または x64 パッケージが必要です。 (ディスク領域を節約するために、必須の Dll の WoW バージョンは、Windows にはネイティブでは含まれていません)。

### スレッドモデルと信頼性

WebView または markup を使って WebView を作成すると、 `document.createElement("x-ms-webview")` `<x-ms-webview>` アプリのプロセス内の新しい固有のスレッドで webview が作成されます。 新しい固有のスレッドで実行されている場合は、1つの WebView の長時間実行されるスクリプトが、アプリまたはその他の WebViews に応答できないことを意味します。 コンストラクターを使用して WebView を作成すると、 `new MSWebView()` 別の webview プロセスに webview が作成されます。 固有のプロセスで実行されている場合は、長時間実行されるスクリプトからの保護に加えて、アプリは WebView プロセスをクラッシュさせる web コンテンツからも保護されることを意味します。 このメソッドを使用して WebView を作成すると [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) 、別のプロセスでも webview が作成されますが、この呼び出し元は、webview プロセスでのプロセスの設定とグループ化の WebViews をより詳細に制御できます。 詳細については、「`MSWebViewProcess`」を参照してください。 

### WinRT API アクセス

UWP アプリでは、WebViews 内の HTML ドキュメントが WinRT Api にアクセスできるようにすることができます。 これは、UWP アプリの Package.appxmanifest の Applicationcontenturirfactor要素の Rule 子要素の Rule 子要素の、WindowsRuntimeAccess 属性によって行われます。 一致する Uri を持つ ' all ' と HTML ドキュメントへのアクセスを設定すると、WinRT を使うことができます。 これは、JavaScript UWP アプリでの HTML コンテンツへの WinRT アクセスの提供と同じであるため、詳細については、「 [PWA からの Winrt api の呼び出し](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa)」をご覧ください。

UI 関連の WinRT Api は、独自のスレッドで実行されている WebView から呼び出された場合に機能しないことがありますが、別の WebView プロセスで実行されている WebView から呼び出された場合に機能する可能性があります。 独自の固有のスレッドで WebView を使う場合、そのスレッドはアプリの表示スレッドではありません。 一部の UI 関連の WinRT Api は、アプリのビュースレッドから呼び出す必要があります。 別の WebView プロセスで作成された WebViews はビュースレッドで実行されるため、独自の固有のスレッドで実行されている WebView と同じ制限が表示されないようにする必要があります。 WebView で UI 関連の WinRT Api を使うときに問題が発生した場合は、前に説明したように、独自の WebView プロセスで WebView を使っていることを確認してください。

### AppCache 記憶域の制限

[HTML5 の仕様](https://go.microsoft.com/fwlink/p/?LinkId=228542)で定義されているアプリケーションキャッシュ API (または appcache) の JavaScript サポートを使用するアプリケーションは、使用可能な記憶域の制限を遵守する必要があります。 これは、メモリ領域が限られているデバイスで特に当てはまります。 AppCache のサイズに関する実際の制限は、常に、利用可能なディスク記憶域の機能です。 一般的なガイドラインを以下に示します。

| ボリュームサイズ         |ドメインあたりの AppCache | ユーザーごとの AppCache   | 
|---------------|---------------|-------------------------|
最大 4 GB | トレイ | 50 MB |
4GB から 16 gb | 50 MB | 500MB | 
16 GB ~ 32 GB | 50 MB | 1GB |

すべての Windows 10 アプリは、同じ AppCache quota モデルを使用することを目的としているため、使用可能なディスク記憶域の制限は、デスクトップアプリと電話アプリの両方に適用されます。 また、 **WebView**の内部に読み込まれたページが 1 GB の*appcache* space を消費した後のハードリミットにもなります。この制限を超えた追加の*Appcache*記憶域への要求は拒否されます。 

詳細については、 [HTML webview コントロールのサンプル](https://go.microsoft.com/fwlink/p/?linkid=309825)を参照してください。また、JSBrowser で[WebView コントロール](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control)のドキュメントを使用しています。

## イベント

### departingFocus

**Webview**からアプリにフォーカスが移動したことを示します。 Webview の最上位レベルのドキュメントが departFocus を呼び出したときに発生します。 DepartingFocus イベントの FocusNavigationEvent args は departFocus に提供されるパラメーターと一致しますが、元のパラメーターは、webview のドキュメントの座標空間から webview ホストドキュメントの座標空間に変換されます。 ホストから webview にフォーカスを移動するには、navigateFocus メソッドと、対応するウィンドウの navigatingFocus イベントを参照してください。 このイベントを処理するキーボードまたはゲームパッドによるフォーカスナビゲーションの実装例については、「 [TVJS の方向ナビゲーションライブラリ](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)」を参照してください。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("departingFocus", handler);
webview.removeEventListener("departingFocus", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [FocusNavigationEvent](./webview/FocusNavigationEvent.md) |
|**同期** |はい |    
|**バブル**     |あり |   
|**取り消し可能な**  |なし |            

### Mswebviewの Fullfullscreenelementchanged

**Webview**に現在フルスクリーン要素が含まれているかどうかの状態が変化したときに発生します。 現在の値には、Fullfullscreenelement プロパティを使います。 ここでは、全画面表示の要素は、要素を使ったフルスクリーン要素の全画面表示の[api](https://developer.mozilla.org/docs/Web/API/Fullscreen_API)の概念を指します。

```js
function containsFullScreenElementChangedHandler(eventInfo) {
    const applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
    if (webview.containsFullScreenElement) {
        webview.classList.add("fullscreen"); // Have the webview fill the app view
        applicationView.tryEnterFullScreenMode(); // Have the app view fill the screen
    }
    else {
        webview.classList.remove("fullscreen"); // Return webview to normal
        applicationView.exitFullScreenMode(); // Return app view to normal
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewContainsFullScreenElementChanged", containsFullScreenElementChangedHandler);
webview.removeEventListener("MSWebViewContainsFullScreenElementChanged", containsFullScreenElementChangedHandler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | **イベント** |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |  

### MSWebViewContentLoading

HTML コンテンツがダウンロードされ、コントロールに読み込まれていることを示します。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewContentLoading", handler);
webview.removeEventListener("MSWebViewContentLoading", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |    

### MSWebViewDOMContentLoaded

メイン DOM 要素の読み込みが完了したことを示します。


```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewDOMContentLoaded", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |                 

### MSWebViewFrameContentLoading

HTML コンテンツがダウンロードされ、コントロールに読み込まれていることを示し `<iframe>` ます。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameContentLoading", handler);
webview.removeEventListener("MSWebViewFrameContentLoading", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |                 

### Mswebviewフレーム Domcontentloaded

メイン DOM 要素がの読み込みを完了したことを示し `<iframe>` ます。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewFrameDOMContentLoaded", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |    


### MSWebViewFrameNavigationCompleted

ナビゲーションが完了しており、すべてのメディア要素がでレンダリングされていることを示し `<iframe>` ます。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationCompleted", handler);
webview.removeEventListener("MSWebViewFrameNavigationCompleted", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationCompletedEvent](./webview/NavigationCompletedEvent.md) |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |       

### MSWebViewFrameNavigationStarting

`<iframe>` **Webview**内でナビゲートが開始されていることを示します。 これは、ナビゲーションのためにネットワークからリソースを取得する前に発生します。 ナビゲーションは、すべての MSWebViewFrameNavigationStarting イベントハンドラーが完了するまで開始されません。 このイベントは、cancellable によって呼び出され `eventArgs.preventDefault()` ます。 キャンセルされた場合、WebView はナビゲーションを実行しません。


```js
function frameNavigationStartingHandler(navigationEventArgs) {
    // Cancel all navigations that don't meet some criteria.
    if (!navigationEventArgs.uri.startsWith("https://example.com/")) {
        navigationEventArgs.preventDefault();
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationStarting", frameNavigationStartingHandler);
webview.removeEventListener("MSWebViewFrameNavigationStarting", frameNavigationStartingHandler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |あり |                 
          
### MSWebViewLongRunningScriptDetected

**Webview**で中断されていないスクリプトの実行中に定期的に発生し、スクリプトを停止します。

```js
function handler(eventInfo) {
    const stopPageScriptThreshold = 5 * 1000;
    if (eventInfo.executionTime > stopPageScriptThreshold) {
        eventInfo.stopPageScriptExecution = true; // Stop the long running script if it goes over our threshold
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewLongRunningScriptDetected", handler);
webview.removeEventListener("MSWebViewLongRunningScriptDetected", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [LongRunningScriptDetectedEvent](./webview/LongRunningScriptDetectedEvent.md) |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |            

### MSWebViewNavigationCompleted

ナビゲーションが完了し、すべてのメディア要素がレンダリングされたか、またはナビゲーションエラーが発生したことを示します。 イベント引数 "CwebErrorStatus" プロパティを確認して、ナビゲーションが成功したかどうかを通知し、ナビゲーションエラーの詳細についてはプロパティを確認します。 URI の hostname が解決されない場合、または (URI のホスト名が解決されない場合)、ナビゲーションエラーは、Mswebviewnavigationstarted イベントの後に発生します。 また、ナビゲーションエラーは、web サーバーからエラーページを受け取った後に発生する可能性があります。たとえば、HTTP サーバーから404のページを受け取ると、すべてのナビゲーションイベントが発生し、MSWebViewNavigationStarting、MSWebViewDOMContentLoaded、Mswebviewnavigationstarting が読み込まれます。 Web サーバーにエラーページが提供されていない場合にアプリのナビゲーションエラーページを表示するには、sharepoint によって提供されたエラーページが表示されていないことを示す、MSWebViewContentLoading が、失敗したナビゲーションに対して呼び出されていないかどうかを確認する必要があります。

```js
let hasContent = false;
webview.addEventListener("MSWebViewNavigationStarting", () => { hasContent = false; });
webview.addEventListener("MSWebViewContentLoading", () => { hasContent = true; });

webview.addEventListener("MSWebViewNavigationCompleted", navigationCompletedEventArgs => {
    // Navigation failures may or may not come after getting an error page from the web server.
    // We keep track of the ContentLoading event with hasContent to tell if we have an error page from the server.
    // So we only navigate to our app error page when there's no server provided error page.
    if (!navigationCompletedEventArgs.isSuccess && !hasContent) {
        // Pass our failed URI and error details in the query and the error page script can read it as appropriate.
        webview.navigate("ms-appx-web:///appErrorPage.html?" + 
            "uri=" + encodeURIComponent(navigationCompletedEventArgs.uri) + "&" +
            "webErrorStatus=" + encodeURIComponent(navigationCompletedEventArgs.webErrorStatus));
    }
});
 
// addEventListener syntax
webview.addEventListener("MSWebViewNavigationCompleted", handler);
webview.removeEventListener("MSWebViewNavigationCompleted", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationCompletedEvent](./webview/NavigationCompletedEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |                 
         

### MSWebViewNavigationStarting

**Webview**でナビゲートが開始されていることを示します。 これは、ナビゲーションのためにネットワークからリソースを取得する前に発生します。 ナビゲーションは、すべての MSWebViewNavigationStarting ハンドラーが完了するまで開始されません。 このイベントは、cancellable によって呼び出され `eventArgs.preventDefault()` ます。 キャンセルされた場合、WebView はナビゲーションを実行しません。


```js
function navigationStartingHandler(navigationEventArgs) {
    // Cancel all navigations that don't meet some criteria.
    if (!navigationEventArgs.uri.startsWith("https://example.com/")) {
        navigationEventArgs.preventDefault();
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewNavigationStarting", navigationStartingHandler);
webview.removeEventListener("MSWebViewNavigationStarting", navigationStartingHandler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |なし  |    
|**バブル**     |あり |   
|**取り消し可能な**  |あり |      

### MSWebViewNewWindowRequested

**Webview**のコンテンツが新しいウィンドウを開こうとしているときに発生します。 イベントが取り消された場合、webview はユーザーの既定のブラウザーで新しいウィンドウ要求の URI を起動します。

```js
function handler(eventInfo) {
    // Prevent the webview from opening URIs in the default browser.
    eventInfo.preventDefault();
    
    // Only allow https://example.com/ to open new windows.
    if (eventInfo.referer === "https://example.com/") {
        // Perform some custom handling of the URI.
        openUri(eventInfo.uri);
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewNewWindowRequested", handler);
webview.removeEventListener("MSWebViewNewWindowRequested", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEventWithReferrer 元](./webview/NavigationEventWithReferrer.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |あり |                 
           

### MSWebViewPermissionRequested

通常、エンドユーザーのアクセス許可を必要とする、 **webview**のコンテンツが機能 (位置情報やポインターロックアクセスなど) にアクセスしようとしていることを示します。 イベントハンドラーが登録されていない場合、またはイベントハンドラーによって eventArgs が呼び出されない場合 ()、defer ()、または deny () の場合、既定でアクセス許可要求は拒否されます。 インスタンスでアクセス許可が非同期で許可または拒否されるかどうかを判断する必要がある場合は、そのユーザーにメッセージを表示する必要がある場合は、eventArgs () を使用します。 アクセス許可要求は、getDeferredPermissionRequestById または getDeferredPermissionRequests を使って、対応する id 値を持つ DeferredPermissionRequest で allow () または deny () を呼び出すまで延期されます。

```js
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    switch (permissionRequest.type) {
        case "geolocation":
        case "media":
        case "pointerlock":
        case "webnotifications":
        case "screen":
        case "immersiveview":
            if (permissionRequest.uri.startsWith("https://www.example.com/")) {
                // Implicitly trust particular URI
                permissionRequest.allow();
            }
            else if (permissionRequest.uri.startsWith("https://")) {
                // Defer the request so we can ask the user to allow or deny the request
                permissionRequest.defer();
                // Later we'll need to use webview.getDeferredPermissionRequestById for this
                // request and call allow or deny.
                promptUserForDeferredPermissionRequest(
                    permissionRequest.id,
                    permissionRequest.uri,
                    permissionRequest.type);
            }
            else {
                // Implicitly deny non-https URIs
                permissionRequest.deny();
            }
            break;

        case "unlimitedIndexedDBQuota":
        default:
            permissionRequest.deny();
            break;
    }
});

// addEventListener syntax
webview.addEventListener("MSWebViewPermissionRequested", handler);
webview.removeEventListener("MSWebViewPermissionRequested", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [PermissionRequestedEvent](./webview/PermissionRequestedEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |    


### Mswebviewプロセス

**Webview**コンポーネントのプロセスが crashsed であることを示します。 これは、アウトプロセスの WebView にのみ関連します。 インプロセス WebView とは異なり、アウトプロセスの WebView を作成する方法については、「解説」を参照してください。 このイベントが発生すると、対応する WebView はクラッシュ状態になります。 最も一般的な WebView 固有のメソッドを呼び出したり、クラッシュした WebView のほとんどの WebView 固有のプロパティにアクセスすると、例外がスローされます。 このイベントから回復するには、クラッシュした WebView を DOM から削除して、新しい WebView に置き換えます。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewProcessExited", handler);
webview.removeEventListener("MSWebViewProcessExited", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | **イベント** |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |      


### MSWebViewWebResourceRequested

**Webview**要素内のページがリソースを要求したときに発生します。

```js
// A handler that completes synchronously with a custom HTTP response built from a string.
function handlerWithSyncString(webResourceRequestedEventArgs) {
    // Only provide custom HTTP responses for particular HTTP requests
    if (webResourceRequestedEventArgs.args.request.requestUri.absoluteUri === "https://www.bing.com/") {
        const Http = Windows.Web.Http;
        // Create the custom response using a string
        webResourceRequestedEventArgs.args.response = new Http.HttpResponseMessage(Http.HttpStatusCode.ok);
        webResourceRequestedEventArgs.args.response.content = new Http.HttpStringContent("<H1>Example</H1>");
    }
});

// A more complicated handler that completes asynchronously with a custom HTTP response built from a stream.
function handlerWithAsyncStream(webResourceRequestedEventArgs) {
    // Only provide custom HTTP responses for particular HTTP requests
    if (webResourceRequestedEventArgs.args.request.requestUri.absoluteUri === "https://www.bing.com/") {
        // Take a deferral on the WebResourceRequested event so that we can create the custom HTTP response asynchronously.
        const deferral = webResourceRequestedEventArgs.args.getDeferral();

        // Use fetch to get a Blob of the content of the URI
        fetch("ms-appx:///replacement.html").then(fetchResponse => {
            return fetchResponse.blob();
        }).then(fetchResponseBlob => {
            const Http = Windows.Web.Http;
            webResourceRequestedEventArgs.args.response = new Http.HttpResponseMessage(
                Http.HttpStatusCode.ok);

            // Use Blob.msDetachStream to convert the Blob to a Windows.Storage.Streams.IInputStream
            webResourceRequestedEventArgs.args.response.content = new Http.HttpStreamContent(
                fetchResponseBlob.msDetachStream());

        }).finally(() => {
            // Use a finally call to complete the deferral so even if there is an error we will unblock the event.
            deferral.complete();
        });
    }
});
 
// addEventListener syntax
webview.addEventListener("MSWebViewWebResourceRequested", handler);
webview.removeEventListener("MSWebViewWebResourceRequested", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [WebResourceRequestedEvent](./webview/WebResourceRequestedEvent.md) |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |      


### MSWebViewScriptNotify

**Webview**要素内のページから**ウィンドウ**を呼び出すときに発生します。 この方法では、アプリの manifest's Applicationcontenturirfactorのルールと一致する Uri を含むドキュメント、または webview を設定することによって、プログラムによって許可されているドキュメントのみを使用できます。 さらに、[外部] というウィンドウも表示できます。

```js
webview.addEventListener("MSWebViewScriptNotify", eventInfo => {
    console.log("The URI " + eventInfo.callingUri + 
        " has sent notification " + eventInfo.value);
});

// Allow the next URI to which we navigate access to window.external.notify
webview.settings.isScriptNotifyAllowed = true;
webview.navigate("https://example.com/");

webview.addEventListener("MSWebViewNavigationCompleted", () => {
    // Inject script to the webview that will send a notification back.
    const asyncOp = webview.invokeScriptAsync("eval", "window.external.notify('example notification')");
    asyncOp.start();
});
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [ScriptNotifyEvent](./webview/ScriptNotifyEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |      

### MSWebViewUnsafeContentWarningDisplaying

SmartScreen フィルターによって安全でないと報告されたコンテンツの警告ページ**が表示された**ときに発生します。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
webview.removeEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | **イベント** |
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |    

### MSWebViewUnsupportedUriSchemeIdentified

**Webview**でサポートされていない Uniform resource IDENTIFIER (URI) に移動したときに発生します。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
webview.removeEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [NavigationEvent](./webview/NavigationEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |あり |     

### MSWebViewUnviewableContentIdentified

**Webview**がサポートされていないコンテンツタイプで web コンテンツに移動しようとしたときに発生します。 たとえば、現在、pdf は webview やナビゲーションでは現在サポートされていないため、PDF ドキュメントは移動せず、このイベントが発生します。

```js
function handler(args) {
    if (args.mediaType === "application/pdf") {
        Windows.System.Launcher.launchUriAsync(new Windows.Foundation.Uri(args.uri));
    }
}

// addEventListener syntax
webview.addEventListener("MSWebViewUnviewableContentIdentified", handler);
webview.removeEventListener("MSWebViewUnviewableContentIdentified", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | [UnviewableContentIdentifiedEvent](./webview/UnviewableContentIdentifiedEvent.md) |
|**同期** |はい  |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |                 
         

## メソッド

### Webview.addweballowedobject

グローバルな Windows ランタイムオブジェクトを、 **webview**内のトップレベルドキュメントにグローバルパラメーターとして追加します。

オブジェクトは、現在のドキュメントには挿入されませんが、webview でナビゲートする次のトップレベルのドキュメントになります。 HTML ドキュメントのいずれかのスクリプトが実行される前にオブジェクトが挿入されるため、ドキュメントのグローバルスクリプトでオブジェクトに依存することができます。

AddWebAllowedObject は、MSWebViewNavigationStarting イベントの間、または navigate メソッドを明示的に呼び出す前に使う必要があります。 この場合、オブジェクトは、対応するナビゲーションのドキュメントに挿入されます。 他のコンテキストで通話を発信する場合、オブジェクトを挿入するドキュメントを特定する方法はありません。

1つの行で addWebAllowedObject を複数回呼び出すと、複数のオブジェクトが文書に挿入されます。 明示的に通話を開始する前に、また対応する MSWebViewNavigationStarting イベント中にもう一度呼び出すと、両方の呼び出しが成功し、複数のオブジェクトが挿入されます。 同じ name パラメーターを使用して複数の通話を発信する場合、前回の通話が優先され、その名前の前の呼び出しが無視されます。

移動に失敗した場合、またはリダイレクトされた場合、そのナビゲーションの addWebAllowedObject 呼び出しは無視されます。 リダイレクトを処理する必要がある場合は、MSWebViewNavigationStarting 開始イベントウォッチをサブスクライブして、アプリケーションに適した条件に従って addWebAllowedObject をもう一度呼び出すことができます。 同様に、ドキュメントは、addWebAllowedObject によって挿入されたオブジェクトを他の場所に移動すると、そのドキュメントには次のドキュメントに引き継がれません。そのためには、addWebAllowedObject を明示的に呼び出す必要があります。

WinRT アクセスを持たないドキュメントに対して addWebAllowedObject を呼び出した場合、または[Applicationcontenturirfactorを使って Allowforwebonly アクセス](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule)が与えられている場合は、オブジェクトは、オブジェクトに対して、オブジェクトに対してのみ挿入されます。 それ以外の場合は、埋め込みは失敗し、JavaScript 開発者コンソールにエラーが報告されます。 完全な WinRT アクセスを持つドキュメントで呼び出された場合は、AllowForWeb 属性に関係なく、そのオブジェクトが挿入されます。 

さらに、オブジェクトは IAgileObject インターフェイスを実装する必要があります。 これは、XAML と HTML の webview 要素がアプリの ASTA view スレッドで実行され、WebView の JavaScript スレッドが異なる ASTA スレッドであるため、可能であればアプリの表示スレッドをブロックすることなく、そのオブジェクトを JavaScript スレッドで実行できるようにすることをアプリ開発者に促します。

Name パラメーターは、有効な JavaScript プロパティ名である必要があります。そうでないと、呼び出しは通知なしで失敗します。 グローバルオブジェクトに既に存在するプロパティの名前の場合、そのプロパティが構成可能であれば、そのプロパティは上書きされます。 グローバルオブジェクトの構成可能ではないプロパティは上書きされず、addWebAllowedObject 呼び出しは黙って失敗します。 AddWebAllowedObject を使って作成された JavaScript プロパティは、書き込み可能、構成可能、列挙可能です。

```js
let name = "exampleProperty";
webview.addWebAllowedObject(name, applicationObject);
webview.navigate("https://example.com/"); // applicationObject will be available as window.exampleProperty on https://example.com
```

#### パラメーター
*name*
* 種類:**文字列**
* **Webview**でドキュメントに公開するオブジェクトの名前。

*applicationObject*
* Type: **Object**
* **Webview**でドキュメントに公開するオブジェクト。

#### 戻り値
このメソッドに戻り値はありません。

#### その他の機能と要件

|            |      |
|------------|------|
|**サポートされている最小クライアント数** |Windows 10 [Windows ストアアプリのみ] |    
|**サポートされている最小のサーバー** |サポートなし |   
|**サポートされている最小電話**  |サポートなし |  

### buildLocalStreamUri

[NavigateToLocalStreamUri](#methods)に渡すことができる URI を作成します。

```js
var string = webview.buildLocalStreamUri(contentIdentifier, relativePath);
```

#### パラメーター
*contentIdentifier*
* 種類:**文字列**
* URI で参照されているコンテンツの一意の識別子。 これにより、URI のルートが定義されます。

*relativePath*
* 種類:**文字列**
* ルートを基準とした、リソースへのパス。

#### 戻り値
種類:**文字列**

*ContentIdentifier*と*relativePath*の結合と正規化によって作成された URI。

#### 例

次の例は、一般的なユースケースを示しています。 

```js
var webview = document.createElement("x-ms-webview"); //Instantiate the webview element
var localStreamUri = webview.buildLocalStreamUri(contentIdentifier, relativePath); //Create URI to pass to navigateToLocalStreamUri method
webview.navigateToLocalStreamUri(localStreamUri, streamResolver); //Load the local web content 
```  

### capturePreviewToBlobAsync

現在の[webview 要素](./webview.md)のイメージを作成し、指定された image 要素に書き込みます。

```js
var capturePreviewToBlobAsync = webview.capturePreviewToBlobAsync();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
Type: **MSWebViewAsyncOperation**

完了時に、画像を含む**Blob**オブジェクトを提供する**MSWebViewAsyncOperation**オブジェクト。 **CapturePreviewToBlobAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。 イベントハンドラーを適用した後で、 [MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md)オブジェクトの start メソッドを呼び出して操作を実行します。

### captureSelectedContentToDataPackageAsync 

> [!IMPORTANT]
> このメソッドは廃止され、既知の問題が発生しています。 このメソッドは、実稼働コードでは使わないでください。 

**Webview**内で選択されたコンテンツを含む[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)を非同期的に取得します。

```js
var msWebViewAsyncOperation = webview.captureSelectedContentToDataPackageAsync();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
Type: **MSWebViewAsyncOperation**

完了時に、画像を含む[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)オブジェクトを提供する**MSWebViewAsyncOperation**オブジェクト。 **CaptureSelectedContentToDataPackageAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。 イベントハンドラーを適用した後で、MSWebViewAsyncOperation オブジェクトの start メソッドを呼び出して操作を実行します。

```js
 var operation = webview.captureSelectedContentToDataPackageAsync();
    operation.oncomplete = function () {
        // operation.result is a package object that contains the selected data.
        var url = URL.createObjectURL(operation.result, { oneTimeOnly: true });
        // After converting the package to a URI, put it in an image element.
        document.getElementById('webviewPreview').src = url;
    };
    operation.start();  

```

### invokeScriptAsync

非同期操作として、指定されたスクリプト関数を現在読み込まれている HTML から特定の引数を指定して実行します。

```js
webview.invokeScriptAsync(functionName, ...args)
```

#### パラメーター

**functionName**
* 種類:**文字列**
* 呼び出す関数の名前。 これは、WebView の最上位レベルのドキュメントのグローバルウィンドウオブジェクトのプロパティ名です。 これは、eval や open などの組み込みのグローバル関数の場合もあります。グローバルウィンドウオブジェクトのスクリプト定義関数の場合もあります。 WebView のトップレベルドキュメント内の関数のみを呼び出すことができます。

**引数**
* 種類:**文字列**
* 呼び出された関数に渡すオプションの文字列パラメーター。 FunctionName の後、invokeScriptAsync に対する追加パラメーターは、呼び出された関数に渡される文字列です。

#### 戻り値
Type: **MSWebViewAsyncOperation**

**InvokeScriptAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。 イベントハンドラーを適用した後、 **MSWebViewAsyncOperation**を呼び出して操作を実行します。 MSWebViewAsyncOperation の complete イベントが発生した場合、MSWebViewAsyncOperation の result プロパティは、関数を呼び出すときの文字列の戻り値になります。 呼び出された関数の戻り値を使うと、WebView コンテンツが WebView ホストに同期された通信を行うことができます。 代わりに、WebView のコンテンツは、Web ビューのホストに非同期的に伝達されるようにするには、MSWebViewScriptNotify イベントを参照してください。 呼び出された関数が未処理の例外をスローすると、MSWebViewAsyncOperation のエラーイベントが発生します。 

```js
const functionName = "eval";
const args = ["'Current URL: ' + document.location.href"];

const asyncOp = webview.invokeScriptAsync(functionName, ...args);

asyncOp.onerror = () => console.error("Error: " + asyncOp.error);
asyncOp.oncomplete = () => console.log("Result: " + asyncOp.result); // Logs 'Current URL: about:blank'
asyncOp.start();
```

### getDeferredPermissionRequests

**Webview**コントロール内のコンテンツによって発行される、延期されたアクセス許可要求の一覧を返します。

```js
var sequence<PermissionRequest> = x-ms-webview.getDeferredPermissionRequests();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)

指定した延期アクセス許可要求。

#### その他の機能と要件

|            |      |
|------------|------|
|**サポートされている最小クライアント数** |Windows 10 [Windows ストアアプリのみ] |    
|**サポートされている最小のサーバー** |サポートなし|   
|**サポートされている最小電話**  |サポートなし |    


### getDeferredPermissionRequestById

指定された延期アクセス許可要求を返します。 

```js
var deferredPermissionRequest = x-ms-webview.getDeferredPermissionRequestById(id);
```

#### パラメーター
*id*
* 種類:**符号なし長**
* 取得する延期されたアクセス許可要求の ID です。

#### 戻り値
Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)

指定した延期アクセス許可要求。

#### その他の機能と要件

|            |      |
|------------|------|
|**サポートされている最小クライアント数** |Windows 10 [Windows ストアアプリのみ] |    
|**サポートされている最小のサーバー** |サポートなし|   
|**サポートされている最小電話**  |サポートなし | 

### goBack

ナビゲーション履歴で、 **webview**を前のページに移動します。 

```js
webview.goBack();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
このメソッドに戻り値はありません。

### goForward

**Webview**をナビゲーション履歴の次のページに移動します。 

```js
webview.goForward();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
このメソッドに戻り値はありません。

### ナビゲート

指定した Uniform Resource Identifier (URI) で HTML コンテンツを読み込みます。 

```js
webview.navigate(uri);
```

#### パラメーター

**uri**
* 種類:**文字列**
* 読み込む URI。

#### 戻り値
このメソッドは値を返しません。

### navigateFocus

**Webview**にフォーカスを移動します。 Webview の最上位レベルのドキュメントの window's イベントを発生させます。 Navigatingfocus イベントで使われている FocusNavigationEvent args は、元のパラメーターを除いて navigateFocus に提供されているパラメーターと一致しますが、元のパラメーターは、ホストドキュメントの座標空間から webview の最上位レベルのドキュメントの座標空間に変換されます。 Webview からホストにフォーカスを転送するには、webview departingFocus イベントと対応する departFocus メソッドを参照してください。 この方法を使用するキーボードまたはゲームパッドによるフォーカスナビゲーションの実装例については、「 [TVJS の方向ナビゲーションライブラリ](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)」を参照してください。

```js
const activeElementBounds = document.activeElement.getBoundingClientRect();
const origin = { 
    originLeft: activeElementBounds.left,
    originTop: activeElementBounds.top,
    originWidth: activeElementBounds.width,
    originHeight: activeElementBounds.height
};
webview.navigateFocus(navigationReason, origin);
```

#### パラメーター
*ナビゲーションの理由*
* 種類:**文字列**
* ナビゲーションの理由。 値は、"left"、"up"、"right"、または "down" のいずれかである必要があります。 フォーカスが現在フォーカスされている要素から移動する方向です。

*cdn*
* Type: **Object**
* ナビゲーションの起点。 プロパティが "原点左"、"原点の先頭"、"原点の幅"、"原点の高さ" というプロパティを持つ JavaScript オブジェクトです。 これらの値は、フォーカスが移動する現在フォーカスのある要素の位置とサイズを記述する必要があります。

#### 戻り値
このメソッドに戻り値はありません。

### navigateToLocalStreamUri

[**Uritostreamresolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync)を使って、指定された URI でローカル web コンテンツを読み込みます。

```js
webview.navigateToLocalStreamUri(source, streamResolver); 
```

#### パラメーター

*ソース*
* 種類:**文字列**
* 読み込むローカルの HTML コンテンツを識別する ms ローカルストリーム URI。 この文字列は、 [**Buildlocalstreamuri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri)を使って作成します。

*streamResolver*
* 種類: any
* URI をストリームに変換して読み込むリゾルバー。

#### 戻り値
このメソッドに戻り値はありません。

### navigateToString

指定した HTML コンテンツを新しい文書として読み込みます。 

```js
webview.navigateToString(contents);
```

#### パラメーター

*数式*
* 種類:**文字列**
* 表示する HTML コンテンツ。

#### 戻り値
このメソッドに戻り値はありません。

### navigateWithHttpRequestMessage

Webview を、POST 要求と HTTP ヘッダー付きの Uniform Resource Identifier (URI) に移動します。 

```js
webview.navigateWithHttpRequestMessage(requestMessage);
```

#### パラメーター

*サーバーから*
* Type: **HttpRequestMessage**
* HTTP 要求の詳細。 

#### 戻り値
このメソッドに戻り値はありません。

#### 注釈

> [!WARNING]
> この要求に、認証資格情報などのヘッダーを追加する場合は、以降の子要求にもそのヘッダーが含まれていることに注意してください。 機密情報が誤って開示されないように注意してください。 


### 非 

**Webview**内の現在のコンテンツを再読み込みします。 

```js
webview.refresh();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
このメソッドに戻り値はありません。


### stop

現在の**webview**ナビゲーションまたはダウンロードを中断します。 

```js
webview.stop();
```

#### パラメーター
このメソッドにはパラメーターはありません。

#### 戻り値
このメソッドに戻り値はありません。


## プロパティ

### canGoBack

**Webview**が後方に移動できるかどうかを示す値を取得します。

このプロパティは読み取り専用です。

```js
var canGoBack = webview.canGoBack;
```

#### プロパティ値
種類:**ブール**型

**Webview**を後方に移動できる場合は**True** 。それ以外の場合は**false**です。

### canGoForward

**Webview**を前方に移動できるかどうかを示す値を取得します。

このプロパティは読み取り専用です。

```js
var canGoForward = webview.canGoForward;
```

#### プロパティ値
種類:**ブール**型

次に、 **webview**を移動できる場合は**True** 。それ以外の場合は**false**です。

### containsFullScreenElement

**Webview**に全画面をサポートする要素が含まれているかどうかを示す値を取得します。 詳細については、Mswebview・ Fullfullelementchanged イベントに関する情報をご覧ください。

このプロパティは読み取り専用です。

```js
var containsFullScreenElement = webview.containsFullScreenElement;
```

#### プロパティ値
種類:**ブール**型

全画面表示をサポートする要素が**webview**に含まれている場合は**True**です。それ以外の場合は**false**です。


### documentTitle

**Webview**に現在表示されているページのタイトルを取得します。 

このプロパティは読み取り専用です。

```js
var documentTitle = webview.documentTitle;
```

#### プロパティ値
種類:**文字列**

ページタイトル。

### height

**Webview**の高さを取得または設定します。 

```js
var height = webview.height;
webview.height = height;

```

#### プロパティ値
種類:**数値**

**Webview**の高さです。 


### プロセス

**Webview**プロセスを取得します。

このプロパティは読み取り専用です。

```js
var process = webview.process;
webview.process = process;
```

#### プロパティ値
種類: [Mswebviewprocess](./webview/MSWebViewProcess.md)


### 設定

**Webview**機能を有効または無効にするプロパティを含む[Mswebviewsettings](./webview/MSWebViewSettings.md)オブジェクトを取得します。

このプロパティは読み取り専用です。

```js
var settings = webview.settings;
webview.settings = settings;
```

#### プロパティ値
種類: [Mswebviewsettings](./webview/MSWebViewSettings.md)

**Webview**機能を有効または無効にするプロパティが含まれている[Mswebviewsettings](./webview/MSWebViewSettings.md)オブジェクト。

### src

**Webview**コントロールに表示される HTML コンテンツの Uniform resource IDENTIFIER (URI) ソースを取得または設定します。 

```js
var src = webview.src;
webview.src = src;
```

#### プロパティ値
種類:**文字列**

**Webview**コントロールに表示される HTML コンテンツの URI ソース。 


### width

**Webview**の幅を取得または設定します。

```js
var width = webview.width;
webview.width = width;
```

#### プロパティ値
種類:**数値**

**Webview**の幅。
