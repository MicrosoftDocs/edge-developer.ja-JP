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
# <span data-ttu-id="a5e87-104">Windows 10 アプリ用 WebView (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="a5e87-104">WebView (EdgeHTML) for Windows 10 apps</span></span>

<span data-ttu-id="a5e87-105">WebView (EdgeHTML) コントロールでは、Windows 10 アプリで web コンテンツをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-105">The WebView (EdgeHTML) control enables you to host web content in your Windows 10 app.</span></span> 

<span data-ttu-id="a5e87-106">これは、次に説明するように、XAML 要素 ([ユニバーサル Windows プラットフォーム (UWP) アプリ](/uwp/api/Windows.UI.Xaml.Controls.WebView)と[WINDOWS フォームと WPF デスクトップアプリケーション](/windows/communitytoolkit/controls/wpf-winforms/webview)の場合)、または HTML 要素 (/DOM オブジェクト) (MSHTMLWebViewElement) として使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-106">You can use it as a XAML element (for [Universal Windows Platform (UWP) apps](/uwp/api/Windows.UI.Xaml.Controls.WebView) and [Windows Forms and WPF desktop applications](/windows/communitytoolkit/controls/wpf-winforms/webview)), or an HTML element (x-ms-webview)/DOM object (MSHTMLWebViewElement) for JavaScript-based Windows 10 apps, as described here.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="a5e87-107">イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-107">Events</span></span>**](#events) | <span data-ttu-id="a5e87-108">[departingFocus](#departingfocus)、 [mswebview・ fullfullscreenelementchanged](#mswebviewcontainsfullscreenelementchanged)、 [mswebviewcontentloading](#mswebviewcontentloading)、 [mswebviewdomcontentloaded](#mswebviewdomcontentloaded)、 [MSWebViewFrameContentLoading](#mswebviewframecontentloading)、 [mswebviewMSWebViewFrameNavigationStarting](#mswebviewframedomcontentloaded)、 [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected)、 [MSWebViewFrameNavigationCompleted](#mswebviewframenavigationcompleted) [mswebviewnavigationcompleted](#mswebviewnavigationcompleted)、mswebviewnavigationstarting、mswebviewnavigationstarting、 [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested)mswebviewの使い方[、](#mswebviewpermissionrequested)mswebviewprocessexMSWebViewFrameNavigationCompleted、 [MSWebViewProcessExited](#mswebviewprocessexited) [MSWebViewWebResourceRequested](#mswebviewwebresourcerequested)、 [mswebviewscriptnotify](#mswebviewscriptnotify)、 [MSWebViewUnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying)、 [MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsupportedurischemeidentified)、 [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified) [MSWebViewFrameNavigationStarting](#mswebviewframenavigationstarting) [MSWebViewNavigationStarting](#mswebviewnavigationstarting)</span><span class="sxs-lookup"><span data-stu-id="a5e87-108">[departingFocus](#departingfocus), [MSWebViewContainsFullScreenElementChanged](#mswebviewcontainsfullscreenelementchanged), [MSWebViewContentLoading](#mswebviewcontentloading), [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded), [MSWebViewFrameContentLoading](#mswebviewframecontentloading), [MSWebViewFrameDOMContentLoaded](#mswebviewframedomcontentloaded), [MSWebViewFrameNavigationCompleted](#mswebviewframenavigationcompleted), [MSWebViewFrameNavigationStarting](#mswebviewframenavigationstarting), [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected), [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted), [MSWebViewNavigationStarting](#mswebviewnavigationstarting), [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested), [MSWebViewPermissionRequested](#mswebviewpermissionrequested), [MSWebViewProcessExited](#mswebviewprocessexited), [MSWebViewWebResourceRequested](#mswebviewwebresourcerequested), [MSWebViewScriptNotify](#mswebviewscriptnotify), [MSWebViewUnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying), [MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsupportedurischemeidentified), [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified)</span></span>
| [**<span data-ttu-id="a5e87-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5e87-109">Methods</span></span>**](#methods) | <span data-ttu-id="a5e87-110">[Addweballowedobject](#addweballowedobject)、 [buildlocalstreamuri](#buildlocalstreamuri)、 [capturePreviewToBlobAsync](#capturepreviewtoblobasync)、 [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync)、 [invokeScriptAsync](#invokescriptasync)、 [getDeferredPermissionRequests](#getdeferredpermissionrequests)、 [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid)、 [goBack](#goback)、 [goforward](#goforward)、 [navigate](#navigate)、 [navigateFocus](#navigatefocus)、 [navigateTolocalStreamUri](#navigatetolocalstreamuri)、 [navigateToString](#navigatetostring)、 [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage)、 [refresh](#refresh)、 [stop](#stop)</span><span class="sxs-lookup"><span data-stu-id="a5e87-110">[addWebAllowedObject](#addweballowedobject), [buildlocalStreamUri](#buildlocalstreamuri), [capturePreviewToBlobAsync](#capturepreviewtoblobasync), [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync), [invokeScriptAsync](#invokescriptasync), [getDeferredPermissionRequests](#getdeferredpermissionrequests), [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid), [goBack](#goback), [goForward](#goforward), [navigate](#navigate), [navigateFocus](#navigatefocus), [navigateTolocalStreamUri](#navigatetolocalstreamuri), [navigateToString](#navigatetostring), [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage), [refresh](#refresh), [stop](#stop)</span></span> |
| [**<span data-ttu-id="a5e87-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a5e87-111">Properties</span></span>**](#properties) | <span data-ttu-id="a5e87-112">[canGoBack](#cangoback)、 [canGoForward](#cangoforward)、 [fullscreenelement](#containsfullscreenelement)、 [documenttitle](#documenttitle)、 [height](#height)、 [process](#process)、 [settings](#settings)、 [src](#src)、 [width](#width)</span><span class="sxs-lookup"><span data-stu-id="a5e87-112">[canGoBack](#cangoback), [canGoForward](#cangoforward), [containsFullScreenElement](#containsfullscreenelement), [documentTitle](#documenttitle), [height](#height), [process](#process), [settings](#settings), [src](#src), [width](#width)</span></span> |

## <span data-ttu-id="a5e87-113">構文</span><span class="sxs-lookup"><span data-stu-id="a5e87-113">Syntax</span></span>

```js
// Feature detect for webview support
if (MSHTMLWebViewElement) {
    let wv = document.createElement('x-ms-webview'); // Use CSS to set width, height and other styles
    wv.navigate("https://www.example.com");
    document.body.appendChild(wv);
}
```

## <span data-ttu-id="a5e87-114">注釈</span><span class="sxs-lookup"><span data-stu-id="a5e87-114">Remarks</span></span>

### <span data-ttu-id="a5e87-115">WebView と iframe</span><span class="sxs-lookup"><span data-stu-id="a5e87-115">WebView versus iframe</span></span>

<span data-ttu-id="a5e87-116">標準 HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)要素と同様に、WebView を使って、アプリパッケージから HTTP とローカルページ (*ms appx-web///*) 経由でリモートページを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-116">Like a standard HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe) element,  you can use WebView to load remote pages over HTTP and local pages (*ms-appx-web:///*) from your app package.</span></span> <span data-ttu-id="a5e87-117">ただし、WebView にも次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-117">However, the WebView can also:</span></span>

 - <span data-ttu-id="a5e87-118">[Applicationdata](/uwp/api/Windows.Storage.ApplicationData) (ローカル、ローミング、temp) フォルダーと[メモリ内ストリーム](/microsoft-edge/hosting/webview#buildlocalstreamuri)*(ms-\*\*ローカルストリーム:*////) からページとリソースをロードします。</span><span class="sxs-lookup"><span data-stu-id="a5e87-118">Load pages and resources from your [ApplicationData](/uwp/api/Windows.Storage.ApplicationData) (local, roaming, temp) folders (*ms-appdata:///*) and [in-memory streams](/microsoft-edge/hosting/webview#buildlocalstreamuri) (*ms-local-stream:///*)</span></span>

 - <span data-ttu-id="a5e87-119">ブラウザーのようなコントロールを提供します。これには、ナビゲーション履歴の[前後](#goback)[に移動](#goforward)したり、現在のページを[停止](#stop)または[更新](#refresh)したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-119">Provide browser-like controls: for going [back](#goback) and [forward](#goforward) in navigation history, and [stopping](#stop) or [refreshing](#refresh) the current page.</span></span> 

 - <span data-ttu-id="a5e87-120">[Web コンテンツのスクリーンショットをキャプチャ](#capturepreviewtoblobasync)して、Windows 10 アプリ[共有](/windows/uwp/app-to-app/share-data)コントラクトを簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-120">[Capture screenshots of web content](#capturepreviewtoblobasync) making it easy to implement the Windows 10 app [Share](/windows/uwp/app-to-app/share-data) contract.</span></span>

 - <span data-ttu-id="a5e87-121">Webview 内で実行される JavaScript コード ([Mswebviewscriptnotify](#mswebviewscriptnotify)) をアプリに対して実行し、アプリが Webview ([invokeScriptAsync](#invokescriptasync)) 内で javascript を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a5e87-121">Allow JavaScript code running within a webview to raise custom events ([MSWebViewScriptNotify](#mswebviewscriptnotify)) to your app, and allow your app to run JavaScript within the webview ([invokeScriptAsync](#invokescriptasync)).</span></span>

 - <span data-ttu-id="a5e87-122">適切に調整された webview コンテンツイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-122">Provide you with fine-tuned webview content events:</span></span>
    
    <span data-ttu-id="a5e87-123">WebView DOM イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-123">WebView DOM event</span></span> | <span data-ttu-id="a5e87-124">説明</span><span class="sxs-lookup"><span data-stu-id="a5e87-124">Description</span></span>
    --------- | ------
    [<span data-ttu-id="a5e87-125">MSWebViewNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="a5e87-125">MSWebViewNavigationStarting</span></span>](#mswebviewnavigationstarting) | <span data-ttu-id="a5e87-126">WebView が移動を開始していることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-126">Indicates the WebView is starting to navigate</span></span>
    [<span data-ttu-id="a5e87-127">MSWebViewContentLoading</span><span class="sxs-lookup"><span data-stu-id="a5e87-127">MSWebViewContentLoading</span></span>](#mswebviewcontentloading) | <span data-ttu-id="a5e87-128">HTML コンテンツがダウンロードされ、コントロールに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-128">The HTML content is downloaded and is being loaded into the control</span></span>
    [<span data-ttu-id="a5e87-129">MSWebViewDOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="a5e87-129">MSWebViewDOMContentLoaded</span></span>](#mswebviewdomcontentloaded) | <span data-ttu-id="a5e87-130">メイン DOM 要素の読み込みが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-130">Indicates that the main DOM elements have finished loading</span></span>
    [<span data-ttu-id="a5e87-131">MSWebViewNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="a5e87-131">MSWebViewNavigationCompleted</span></span>](#mswebviewnavigationcompleted) | <span data-ttu-id="a5e87-132">ナビゲーションが完了し、すべてのメディア要素がレンダリングされることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-132">Indicates the navigation is complete, and all media elements are rendered</span></span>
    [<span data-ttu-id="a5e87-133">MSWebViewUnviewableContentIdentified</span><span class="sxs-lookup"><span data-stu-id="a5e87-133">MSWebViewUnviewableContentIdentified</span></span>](#mswebviewunviewablecontentidentified) | <span data-ttu-id="a5e87-134">WebView でコンテンツが HTML ではなかった</span><span class="sxs-lookup"><span data-stu-id="a5e87-134">The WebView found the content was not HTML</span></span>
    [<span data-ttu-id="a5e87-135">UnsafeContentWarningDisplaying</span><span class="sxs-lookup"><span data-stu-id="a5e87-135">UnsafeContentWarningDisplaying</span></span>](#mswebviewunsafecontentwarningdisplaying) | <span data-ttu-id="a5e87-136">WebView には、Windows *SmartScreen フィルター*によって安全でないと報告されたコンテンツの警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-136">The WebView shows a warning page for content that was reported as unsafe by Windows *SmartScreen Filter*.</span></span>

    <span data-ttu-id="a5e87-137">...WebView に読み込まれる iframe コンテンツに対応する[イベント](#events)( [mswebview**Frame**navigationstarting 開始](#mswebviewframenavigationstarting)など) を含めます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-137">...including corresponding [events](#events) for iframe content loaded within a WebView (such as [MSWebView**Frame**NavigationStarting](#mswebviewframenavigationstarting) and so on.)</span></span>

### <span data-ttu-id="a5e87-138">印刷</span><span class="sxs-lookup"><span data-stu-id="a5e87-138">Printing</span></span>

<span data-ttu-id="a5e87-139">JavaScript を使った Windows アプリが印刷されると、 `<x-ms-webview>` タグが `<iframe>` 印刷前にタグに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-139">When a Windows app using JavaScript is printed, the `<x-ms-webview>` tags are transformed into `<iframe>` tags before printing.</span></span> <span data-ttu-id="a5e87-140">画面上での表示と印刷用の標準の違い以外に、要素に適用された CSS スタイル `<iframe>` は、から変換された元のスタイルに適用され `<iframe>` `<x-ms-webview>` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-140">Besides the normal difference between displaying on screen and rendered for print, CSS styles applied to `<iframe>` elements are then applicable to the `<iframe>` transformed from `<x-ms-webview>`.</span></span>

### <span data-ttu-id="a5e87-141">サービス員</span><span class="sxs-lookup"><span data-stu-id="a5e87-141">Service workers</span></span>

<span data-ttu-id="a5e87-142">[Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)(EdgeHTML 18) 以降では、 [Service worker は WebView コントロールでサポートされて](/microsoft-edge/dev-guide#service-workers)います (JavaScript を使った Microsoft Edge ブラウザーと Windows 10 アプリに加えています)。</span><span class="sxs-lookup"><span data-stu-id="a5e87-142">Starting with the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) (EdgeHTML 18), [service workers are supported in the WebView control](/microsoft-edge/dev-guide#service-workers) (in addition to the Microsoft Edge browser and Windows 10 apps with JavaScript).</span></span>

<span data-ttu-id="a5e87-143">x64 アプリアーキテクチャでは、サービスワーカーは WoW64 プロセスでサポートされていないため、ニュートラル (任意の CPU) または x64 パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-143">x64 app architectures require Neutral (Any CPU) or x64 packages, as service workers are not supported in WoW64 processes.</span></span> <span data-ttu-id="a5e87-144">(ディスク領域を節約するために、必須の Dll の WoW バージョンは、Windows にはネイティブでは含まれていません)。</span><span class="sxs-lookup"><span data-stu-id="a5e87-144">(To conserve disk space, the WoW version of the required DLLs are not natively included in Windows.)</span></span>

### <span data-ttu-id="a5e87-145">スレッドモデルと信頼性</span><span class="sxs-lookup"><span data-stu-id="a5e87-145">Threading model and reliability</span></span>

<span data-ttu-id="a5e87-146">WebView または markup を使って WebView を作成すると、 `document.createElement("x-ms-webview")` `<x-ms-webview>` アプリのプロセス内の新しい固有のスレッドで webview が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-146">Creating a WebView via `document.createElement("x-ms-webview")` or via `<x-ms-webview>` markup creates a WebView on a new unique thread in the app's process.</span></span> <span data-ttu-id="a5e87-147">新しい固有のスレッドで実行されている場合は、1つの WebView の長時間実行されるスクリプトが、アプリまたはその他の WebViews に応答できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-147">Running on a new unique thread means that long running script from one WebView is unable to hang the app or other WebViews.</span></span> <span data-ttu-id="a5e87-148">コンストラクターを使用して WebView を作成すると、 `new MSWebView()` 別の webview プロセスに webview が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-148">Creating a WebView via the `new MSWebView()` constructor creates a WebView in a separate WebView process.</span></span> <span data-ttu-id="a5e87-149">固有のプロセスで実行されている場合は、長時間実行されるスクリプトからの保護に加えて、アプリは WebView プロセスをクラッシュさせる web コンテンツからも保護されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-149">Running in a unique process means that in addition to protection from long running script, the app is also protected from web content that crashes the WebView process.</span></span> <span data-ttu-id="a5e87-150">このメソッドを使用して WebView を作成すると [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) 、別のプロセスでも webview が作成されますが、この呼び出し元は、webview プロセスでのプロセスの設定とグループ化の WebViews をより詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-150">Creating a WebView via the [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) method also creates a WebView in a separate process but allows the caller more control over process settings and grouping WebViews in WebView processes.</span></span> <span data-ttu-id="a5e87-151">詳細については、「`MSWebViewProcess`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-151">See `MSWebViewProcess` for more information.</span></span> 

### <span data-ttu-id="a5e87-152">WinRT API アクセス</span><span class="sxs-lookup"><span data-stu-id="a5e87-152">WinRT API access</span></span>

<span data-ttu-id="a5e87-153">UWP アプリでは、WebViews 内の HTML ドキュメントが WinRT Api にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-153">A UWP app may allow HTML documents inside WebViews to have access to WinRT APIs.</span></span> <span data-ttu-id="a5e87-154">これは、UWP アプリの Package.appxmanifest の Applicationcontenturirfactor要素の Rule 子要素の Rule 子要素の、WindowsRuntimeAccess 属性によって行われます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-154">This is via the WindowsRuntimeAccess attribute of the Rule child elements of the ApplicationContentUriRules element of the AppxManifest.xml of the UWP app.</span></span> <span data-ttu-id="a5e87-155">一致する Uri を持つ ' all ' と HTML ドキュメントへのアクセスを設定すると、WinRT を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-155">Set WindowsRuntimeAccess to 'all' and HTML documents with matching URIs will be allowed to use WinRT.</span></span> <span data-ttu-id="a5e87-156">これは、JavaScript UWP アプリでの HTML コンテンツへの WinRT アクセスの提供と同じであるため、詳細については、「 [PWA からの Winrt api の呼び出し](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-156">This is the same as providing WinRT access to HTML content in JavaScript UWP apps so see [Call WinRT APIs from your PWA](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa) for more information.</span></span>

<span data-ttu-id="a5e87-157">UI 関連の WinRT Api は、独自のスレッドで実行されている WebView から呼び出された場合に機能しないことがありますが、別の WebView プロセスで実行されている WebView から呼び出された場合に機能する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-157">UI related WinRT APIs may not work when called from a WebView running on its own thread but may work when called from a WebView running in a separate WebView process.</span></span> <span data-ttu-id="a5e87-158">独自の固有のスレッドで WebView を使う場合、そのスレッドはアプリの表示スレッドではありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-158">When using a WebView on its own unique thread, that thread is not the app's view thread.</span></span> <span data-ttu-id="a5e87-159">一部の UI 関連の WinRT Api は、アプリのビュースレッドから呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-159">Some UI related WinRT APIs require to be called from the app's view thread.</span></span> <span data-ttu-id="a5e87-160">別の WebView プロセスで作成された WebViews はビュースレッドで実行されるため、独自の固有のスレッドで実行されている WebView と同じ制限が表示されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-160">WebViews created in a separate WebView process do run on a view thread and so should not face the same restrictions as WebView's running on their own unique thread.</span></span> <span data-ttu-id="a5e87-161">WebView で UI 関連の WinRT Api を使うときに問題が発生した場合は、前に説明したように、独自の WebView プロセスで WebView を使っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-161">If you have trouble with UI related WinRT APIs in a WebView ensure that you're using a WebView in its own WebView process as described above.</span></span>

### <span data-ttu-id="a5e87-162">AppCache 記憶域の制限</span><span class="sxs-lookup"><span data-stu-id="a5e87-162">AppCache storage limitations</span></span>

<span data-ttu-id="a5e87-163">[HTML5 の仕様](https://go.microsoft.com/fwlink/p/?LinkId=228542)で定義されているアプリケーションキャッシュ API (または appcache) の JavaScript サポートを使用するアプリケーションは、使用可能な記憶域の制限を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-163">Applications using JavaScript support of the Application Cache API (or AppCache), as defined in the [HTML5 specification](https://go.microsoft.com/fwlink/p/?LinkId=228542), to create offline web applications must observe available storage limitations.</span></span> <span data-ttu-id="a5e87-164">これは、メモリ領域が限られているデバイスで特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-164">This is especially true in devices with limited memory space.</span></span> <span data-ttu-id="a5e87-165">AppCache のサイズに関する実際の制限は、常に、利用可能なディスク記憶域の機能です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-165">The practical limits on the size of the AppCache are always a function of available disk storage space.</span></span> <span data-ttu-id="a5e87-166">一般的なガイドラインを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-166">The general guidelines are shown below.</span></span>

| <span data-ttu-id="a5e87-167">ボリュームサイズ</span><span class="sxs-lookup"><span data-stu-id="a5e87-167">Volume size</span></span>         |<span data-ttu-id="a5e87-168">ドメインあたりの AppCache</span><span class="sxs-lookup"><span data-stu-id="a5e87-168">AppCache per domain</span></span> | <span data-ttu-id="a5e87-169">ユーザーごとの AppCache</span><span class="sxs-lookup"><span data-stu-id="a5e87-169">AppCache per user</span></span>   | 
|---------------|---------------|-------------------------|
<span data-ttu-id="a5e87-170">最大 4 GB</span><span class="sxs-lookup"><span data-stu-id="a5e87-170">Up to 4GB</span></span> | <span data-ttu-id="a5e87-171">トレイ</span><span class="sxs-lookup"><span data-stu-id="a5e87-171">10MB</span></span> | <span data-ttu-id="a5e87-172">50 MB</span><span class="sxs-lookup"><span data-stu-id="a5e87-172">50MB</span></span> |
<span data-ttu-id="a5e87-173">4GB から 16 gb</span><span class="sxs-lookup"><span data-stu-id="a5e87-173">4GB to 16GB</span></span> | <span data-ttu-id="a5e87-174">50 MB</span><span class="sxs-lookup"><span data-stu-id="a5e87-174">50MB</span></span> | <span data-ttu-id="a5e87-175">500MB</span><span class="sxs-lookup"><span data-stu-id="a5e87-175">500MB</span></span> | 
<span data-ttu-id="a5e87-176">16 GB ~ 32 GB</span><span class="sxs-lookup"><span data-stu-id="a5e87-176">16GB to 32 GB</span></span> | <span data-ttu-id="a5e87-177">50 MB</span><span class="sxs-lookup"><span data-stu-id="a5e87-177">50MB</span></span> | <span data-ttu-id="a5e87-178">1GB</span><span class="sxs-lookup"><span data-stu-id="a5e87-178">1GB</span></span> |

<span data-ttu-id="a5e87-179">すべての Windows 10 アプリは、同じ AppCache quota モデルを使用することを目的としているため、使用可能なディスク記憶域の制限は、デスクトップアプリと電話アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-179">All Windows10 apps are intended to use the same AppCache quota model, so the available disk storage limitation applies to both desktop and phone apps.</span></span> <span data-ttu-id="a5e87-180">また、 **WebView**の内部に読み込まれたページが 1 GB の*appcache* space を消費した後のハードリミットにもなります。この制限を超えた追加の*Appcache*記憶域への要求は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-180">The is also a hard limit after pages loaded inside **WebView** together have consumed 1 GB of *AppCache* space; requests for additional *AppCache* storage above this limit will be denied.</span></span> 

<span data-ttu-id="a5e87-181">詳細については、 [HTML webview コントロールのサンプル](https://go.microsoft.com/fwlink/p/?linkid=309825)を参照してください。また、JSBrowser で[WebView コントロール](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control)のドキュメントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a5e87-181">For more information, see the [HTML WebView control sample](https://go.microsoft.com/fwlink/p/?linkid=309825) and the JSBrowser's [Harnessing the WebView control](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control) documentation.</span></span>

## <span data-ttu-id="a5e87-182">イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-182">Events</span></span>

### <span data-ttu-id="a5e87-183">departingFocus</span><span class="sxs-lookup"><span data-stu-id="a5e87-183">departingFocus</span></span>

<span data-ttu-id="a5e87-184">**Webview**からアプリにフォーカスが移動したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-184">Indicates focus departing from the **webview** into the app.</span></span> <span data-ttu-id="a5e87-185">Webview の最上位レベルのドキュメントが departFocus を呼び出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-185">Fires when the webview's top level document calls window.departFocus.</span></span> <span data-ttu-id="a5e87-186">DepartingFocus イベントの FocusNavigationEvent args は departFocus に提供されるパラメーターと一致しますが、元のパラメーターは、webview のドキュメントの座標空間から webview ホストドキュメントの座標空間に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-186">The FocusNavigationEvent args in the departingFocus event match the parameters provided to departFocus except the origin parameters are translated from the webview's document's coordinate space to the coordinate space of the webview host document.</span></span> <span data-ttu-id="a5e87-187">ホストから webview にフォーカスを移動するには、navigateFocus メソッドと、対応するウィンドウの navigatingFocus イベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-187">See the webview.navigateFocus method and corresponding window navigatingFocus event for transferring focus from host to webview.</span></span> <span data-ttu-id="a5e87-188">このイベントを処理するキーボードまたはゲームパッドによるフォーカスナビゲーションの実装例については、「 [TVJS の方向ナビゲーションライブラリ](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-188">See the [TVJS's Direction Navigation library](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) for an example of an implementation of focus navigation via keyboard or gamepad that handles this event.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("departingFocus", handler);
webview.removeEventListener("departingFocus", handler);
```

#### <span data-ttu-id="a5e87-189">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-189">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-190">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-190">Interface</span></span>** | [<span data-ttu-id="a5e87-191">FocusNavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-191">FocusNavigationEvent</span></span>](./webview/FocusNavigationEvent.md) |
|**<span data-ttu-id="a5e87-192">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-192">Synchronous</span></span>** |<span data-ttu-id="a5e87-193">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-193">Yes</span></span> |    
|**<span data-ttu-id="a5e87-194">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-194">Bubbles</span></span>**     |<span data-ttu-id="a5e87-195">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-195">Yes</span></span> |   
|**<span data-ttu-id="a5e87-196">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-196">Cancelable</span></span>**  |<span data-ttu-id="a5e87-197">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-197">No</span></span> |            

### <span data-ttu-id="a5e87-198">Mswebviewの Fullfullscreenelementchanged</span><span class="sxs-lookup"><span data-stu-id="a5e87-198">MSWebViewContainsFullScreenElementChanged</span></span>

<span data-ttu-id="a5e87-199">**Webview**に現在フルスクリーン要素が含まれているかどうかの状態が変化したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-199">Occurs when the status changes of whether or not the **webview** currently contains a full screen element.</span></span> <span data-ttu-id="a5e87-200">現在の値には、Fullfullscreenelement プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="a5e87-200">Use the containsFullScreenElement property to the current value.</span></span> <span data-ttu-id="a5e87-201">ここでは、全画面表示の要素は、要素を使ったフルスクリーン要素の全画面表示の[api](https://developer.mozilla.org/docs/Web/API/Fullscreen_API)の概念を指します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-201">Full screen element here refers to the [Fullscreen DOM APIs](https://developer.mozilla.org/docs/Web/API/Fullscreen_API) notion of a full screen element via the element.requestFullScreen and document.exitFullScreen DOM functions.</span></span>

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

#### <span data-ttu-id="a5e87-202">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-202">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-203">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-203">Interface</span></span>** | **<span data-ttu-id="a5e87-204">イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-204">Event</span></span>** |
|**<span data-ttu-id="a5e87-205">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-205">Synchronous</span></span>** |<span data-ttu-id="a5e87-206">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-206">Yes</span></span> |    
|**<span data-ttu-id="a5e87-207">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-207">Bubbles</span></span>**     |<span data-ttu-id="a5e87-208">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-208">No</span></span> |   
|**<span data-ttu-id="a5e87-209">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-209">Cancelable</span></span>**  |<span data-ttu-id="a5e87-210">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-210">No</span></span> |  

### <span data-ttu-id="a5e87-211">MSWebViewContentLoading</span><span class="sxs-lookup"><span data-stu-id="a5e87-211">MSWebViewContentLoading</span></span>

<span data-ttu-id="a5e87-212">HTML コンテンツがダウンロードされ、コントロールに読み込まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-212">Indicates that the HTML content is downloaded and is being loaded into the control.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewContentLoading", handler);
webview.removeEventListener("MSWebViewContentLoading", handler);
```

#### <span data-ttu-id="a5e87-213">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-213">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-214">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-214">Interface</span></span>** | [<span data-ttu-id="a5e87-215">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-215">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-216">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-216">Synchronous</span></span>** |<span data-ttu-id="a5e87-217">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-217">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-218">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-218">Bubbles</span></span>**     |<span data-ttu-id="a5e87-219">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-219">No</span></span> |   
|**<span data-ttu-id="a5e87-220">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-220">Cancelable</span></span>**  |<span data-ttu-id="a5e87-221">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-221">No</span></span> |    

### <span data-ttu-id="a5e87-222">MSWebViewDOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="a5e87-222">MSWebViewDOMContentLoaded</span></span>

<span data-ttu-id="a5e87-223">メイン DOM 要素の読み込みが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-223">Indicates that the main DOM elements have finished loading.</span></span>


```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewDOMContentLoaded", handler);
```

#### <span data-ttu-id="a5e87-224">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-224">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-225">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-225">Interface</span></span>** | [<span data-ttu-id="a5e87-226">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-226">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-227">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-227">Synchronous</span></span>** |<span data-ttu-id="a5e87-228">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-228">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-229">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-229">Bubbles</span></span>**     |<span data-ttu-id="a5e87-230">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-230">No</span></span> |   
|**<span data-ttu-id="a5e87-231">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-231">Cancelable</span></span>**  |<span data-ttu-id="a5e87-232">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-232">No</span></span> |                 

### <span data-ttu-id="a5e87-233">MSWebViewFrameContentLoading</span><span class="sxs-lookup"><span data-stu-id="a5e87-233">MSWebViewFrameContentLoading</span></span>

<span data-ttu-id="a5e87-234">HTML コンテンツがダウンロードされ、コントロールに読み込まれていることを示し `<iframe>` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-234">Indicates that the HTML content downloaded and is being loaded into the `<iframe>` control.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameContentLoading", handler);
webview.removeEventListener("MSWebViewFrameContentLoading", handler);
```

#### <span data-ttu-id="a5e87-235">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-235">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-236">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-236">Interface</span></span>** | [<span data-ttu-id="a5e87-237">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-237">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-238">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-238">Synchronous</span></span>** |<span data-ttu-id="a5e87-239">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-239">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-240">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-240">Bubbles</span></span>**     |<span data-ttu-id="a5e87-241">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-241">No</span></span> |   
|**<span data-ttu-id="a5e87-242">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-242">Cancelable</span></span>**  |<span data-ttu-id="a5e87-243">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-243">No</span></span> |                 

### <span data-ttu-id="a5e87-244">Mswebviewフレーム Domcontentloaded</span><span class="sxs-lookup"><span data-stu-id="a5e87-244">MSWebViewFrameDOMContentLoaded</span></span>

<span data-ttu-id="a5e87-245">メイン DOM 要素がの読み込みを完了したことを示し `<iframe>` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-245">Indicates that the main DOM elements have finished loading in the `<iframe>`.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewFrameDOMContentLoaded", handler);
```

#### <span data-ttu-id="a5e87-246">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-246">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-247">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-247">Interface</span></span>** | [<span data-ttu-id="a5e87-248">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-248">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-249">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-249">Synchronous</span></span>** |<span data-ttu-id="a5e87-250">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-250">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-251">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-251">Bubbles</span></span>**     |<span data-ttu-id="a5e87-252">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-252">No</span></span> |   
|**<span data-ttu-id="a5e87-253">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-253">Cancelable</span></span>**  |<span data-ttu-id="a5e87-254">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-254">No</span></span> |    


### <span data-ttu-id="a5e87-255">MSWebViewFrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="a5e87-255">MSWebViewFrameNavigationCompleted</span></span>

<span data-ttu-id="a5e87-256">ナビゲーションが完了しており、すべてのメディア要素がでレンダリングされていることを示し `<iframe>` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-256">Indicates the navigation is complete, and all media elements are rendered in the `<iframe>`.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationCompleted", handler);
webview.removeEventListener("MSWebViewFrameNavigationCompleted", handler);
```

#### <span data-ttu-id="a5e87-257">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-257">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-258">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-258">Interface</span></span>** | [<span data-ttu-id="a5e87-259">NavigationCompletedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-259">NavigationCompletedEvent</span></span>](./webview/NavigationCompletedEvent.md) |
|**<span data-ttu-id="a5e87-260">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-260">Synchronous</span></span>** |<span data-ttu-id="a5e87-261">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-261">Yes</span></span> |    
|**<span data-ttu-id="a5e87-262">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-262">Bubbles</span></span>**     |<span data-ttu-id="a5e87-263">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-263">No</span></span> |   
|**<span data-ttu-id="a5e87-264">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-264">Cancelable</span></span>**  |<span data-ttu-id="a5e87-265">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-265">No</span></span> |       

### <span data-ttu-id="a5e87-266">MSWebViewFrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="a5e87-266">MSWebViewFrameNavigationStarting</span></span>

<span data-ttu-id="a5e87-267">`<iframe>` **Webview**内でナビゲートが開始されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-267">Indicates a `<iframe>` within a **webview** is starting to navigate.</span></span> <span data-ttu-id="a5e87-268">これは、ナビゲーションのためにネットワークからリソースを取得する前に発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-268">This is fired before obtaining any resources from the network for the navigation.</span></span> <span data-ttu-id="a5e87-269">ナビゲーションは、すべての MSWebViewFrameNavigationStarting イベントハンドラーが完了するまで開始されません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-269">The navigation is not started until all MSWebViewFrameNavigationStarting event handlers complete.</span></span> <span data-ttu-id="a5e87-270">このイベントは、cancellable によって呼び出され `eventArgs.preventDefault()` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-270">This event is cancellable via calling `eventArgs.preventDefault()`.</span></span> <span data-ttu-id="a5e87-271">キャンセルされた場合、WebView はナビゲーションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-271">If cancelled, the WebView will not perform the navigation.</span></span>


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

#### <span data-ttu-id="a5e87-272">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-272">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-273">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-273">Interface</span></span>** | [<span data-ttu-id="a5e87-274">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-274">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-275">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-275">Synchronous</span></span>** |<span data-ttu-id="a5e87-276">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-276">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-277">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-277">Bubbles</span></span>**     |<span data-ttu-id="a5e87-278">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-278">No</span></span> |   
|**<span data-ttu-id="a5e87-279">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-279">Cancelable</span></span>**  |<span data-ttu-id="a5e87-280">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-280">Yes</span></span> |                 
          
### <span data-ttu-id="a5e87-281">MSWebViewLongRunningScriptDetected</span><span class="sxs-lookup"><span data-stu-id="a5e87-281">MSWebViewLongRunningScriptDetected</span></span>

<span data-ttu-id="a5e87-282">**Webview**で中断されていないスクリプトの実行中に定期的に発生し、スクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-282">Occurs periodically during uninterrupted script execution in the **webview**, letting you halt the script.</span></span>

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

#### <span data-ttu-id="a5e87-283">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-283">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-284">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-284">Interface</span></span>** | [<span data-ttu-id="a5e87-285">LongRunningScriptDetectedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-285">LongRunningScriptDetectedEvent</span></span>](./webview/LongRunningScriptDetectedEvent.md) |
|**<span data-ttu-id="a5e87-286">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-286">Synchronous</span></span>** |<span data-ttu-id="a5e87-287">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-287">Yes</span></span> |    
|**<span data-ttu-id="a5e87-288">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-288">Bubbles</span></span>**     |<span data-ttu-id="a5e87-289">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-289">No</span></span> |   
|**<span data-ttu-id="a5e87-290">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-290">Cancelable</span></span>**  |<span data-ttu-id="a5e87-291">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-291">No</span></span> |            

### <span data-ttu-id="a5e87-292">MSWebViewNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="a5e87-292">MSWebViewNavigationCompleted</span></span>

<span data-ttu-id="a5e87-293">ナビゲーションが完了し、すべてのメディア要素がレンダリングされたか、またはナビゲーションエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-293">Indicates the navigation is complete, and all media elements are rendered or there was a navigation error.</span></span> <span data-ttu-id="a5e87-294">イベント引数 "CwebErrorStatus" プロパティを確認して、ナビゲーションが成功したかどうかを通知し、ナビゲーションエラーの詳細についてはプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-294">Check the event args isSuccess property to tell if the navigation was successful and the webErrorStatus property for details on the navigation error.</span></span> <span data-ttu-id="a5e87-295">URI の hostname が解決されない場合、または (URI のホスト名が解決されない場合)、ナビゲーションエラーは、Mswebviewnavigationstarted イベントの後に発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-295">Navigation errors can occur before obtaining any content from the network for instance if the hostname of a URI does not resolve in which case the MSWebViewNavigationStarted event will fire followed by the MSWebViewNavigationCompleted event.</span></span> <span data-ttu-id="a5e87-296">また、ナビゲーションエラーは、web サーバーからエラーページを受け取った後に発生する可能性があります。たとえば、HTTP サーバーから404のページを受け取ると、すべてのナビゲーションイベントが発生し、MSWebViewNavigationStarting、MSWebViewDOMContentLoaded、Mswebviewnavigationstarting が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-296">Navigation errors may also occur after receiving an error page from a web server, for instance a 404 page from an HTTP server in which case all navigation events will fire, MSWebViewNavigationStarting, MSWebViewContentLoading, MSWebViewDOMContentLoaded, and then MSWebViewNavigationCompleted.</span></span> <span data-ttu-id="a5e87-297">Web サーバーにエラーページが提供されていない場合にアプリのナビゲーションエラーページを表示するには、sharepoint によって提供されたエラーページが表示されていないことを示す、MSWebViewContentLoading が、失敗したナビゲーションに対して呼び出されていないかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-297">To provide an app navigation error page for cases where the web server hasn't provided an error page, you'll need to check if MSWebViewContentLoading hasn't fired for a failed navigation which indicates there is no server provided error page.</span></span>

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

#### <span data-ttu-id="a5e87-298">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-298">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-299">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-299">Interface</span></span>** | [<span data-ttu-id="a5e87-300">NavigationCompletedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-300">NavigationCompletedEvent</span></span>](./webview/NavigationCompletedEvent.md) |
|**<span data-ttu-id="a5e87-301">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-301">Synchronous</span></span>** |<span data-ttu-id="a5e87-302">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-302">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-303">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-303">Bubbles</span></span>**     |<span data-ttu-id="a5e87-304">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-304">No</span></span> |   
|**<span data-ttu-id="a5e87-305">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-305">Cancelable</span></span>**  |<span data-ttu-id="a5e87-306">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-306">No</span></span> |                 
         

### <span data-ttu-id="a5e87-307">MSWebViewNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="a5e87-307">MSWebViewNavigationStarting</span></span>

<span data-ttu-id="a5e87-308">**Webview**でナビゲートが開始されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-308">Indicates the **webview** is starting to navigate.</span></span> <span data-ttu-id="a5e87-309">これは、ナビゲーションのためにネットワークからリソースを取得する前に発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-309">This is fired before obtaining any resources from the network for the navigation.</span></span> <span data-ttu-id="a5e87-310">ナビゲーションは、すべての MSWebViewNavigationStarting ハンドラーが完了するまで開始されません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-310">The navigation is not started until all MSWebViewNavigationStarting event handlers complete.</span></span> <span data-ttu-id="a5e87-311">このイベントは、cancellable によって呼び出され `eventArgs.preventDefault()` ます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-311">This event is cancellable via calling `eventArgs.preventDefault()`.</span></span> <span data-ttu-id="a5e87-312">キャンセルされた場合、WebView はナビゲーションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-312">If cancelled, the WebView will not perform the navigation.</span></span>


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

#### <span data-ttu-id="a5e87-313">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-313">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-314">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-314">Interface</span></span>** | [<span data-ttu-id="a5e87-315">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-315">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-316">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-316">Synchronous</span></span>** |<span data-ttu-id="a5e87-317">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-317">No</span></span>  |    
|**<span data-ttu-id="a5e87-318">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-318">Bubbles</span></span>**     |<span data-ttu-id="a5e87-319">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-319">Yes</span></span> |   
|**<span data-ttu-id="a5e87-320">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-320">Cancelable</span></span>**  |<span data-ttu-id="a5e87-321">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-321">Yes</span></span> |      

### <span data-ttu-id="a5e87-322">MSWebViewNewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="a5e87-322">MSWebViewNewWindowRequested</span></span>

<span data-ttu-id="a5e87-323">**Webview**のコンテンツが新しいウィンドウを開こうとしているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-323">Raised when content in **webview** is trying to open a new window.</span></span> <span data-ttu-id="a5e87-324">イベントが取り消された場合、webview はユーザーの既定のブラウザーで新しいウィンドウ要求の URI を起動します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-324">If the event isn't cancelled the webview will launch the URI of the new window request in the user's default browser.</span></span>

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

#### <span data-ttu-id="a5e87-325">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-325">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-326">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-326">Interface</span></span>** | [<span data-ttu-id="a5e87-327">NavigationEventWithReferrer 元</span><span class="sxs-lookup"><span data-stu-id="a5e87-327">NavigationEventWithReferrer</span></span>](./webview/NavigationEventWithReferrer.md) |
|**<span data-ttu-id="a5e87-328">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-328">Synchronous</span></span>** |<span data-ttu-id="a5e87-329">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-329">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-330">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-330">Bubbles</span></span>**     |<span data-ttu-id="a5e87-331">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-331">No</span></span> |   
|**<span data-ttu-id="a5e87-332">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-332">Cancelable</span></span>**  |<span data-ttu-id="a5e87-333">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-333">Yes</span></span> |                 
           

### <span data-ttu-id="a5e87-334">MSWebViewPermissionRequested</span><span class="sxs-lookup"><span data-stu-id="a5e87-334">MSWebViewPermissionRequested</span></span>

<span data-ttu-id="a5e87-335">通常、エンドユーザーのアクセス許可を必要とする、 **webview**のコンテンツが機能 (位置情報やポインターロックアクセスなど) にアクセスしようとしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-335">Indicates that content in the **webview**  is trying to access functionality (such as geolocation, or pointer lock access) that normally requires end-user permissions.</span></span> <span data-ttu-id="a5e87-336">イベントハンドラーが登録されていない場合、またはイベントハンドラーによって eventArgs が呼び出されない場合 ()、defer ()、または deny () の場合、既定でアクセス許可要求は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-336">If no event handler is registered or if the event handler doesn't call eventArgs.permissionRequest.allow(), defer(), or deny(), then by default the permission request will be denied.</span></span> <span data-ttu-id="a5e87-337">インスタンスでアクセス許可が非同期で許可または拒否されるかどうかを判断する必要がある場合は、そのユーザーにメッセージを表示する必要がある場合は、eventArgs () を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-337">If you need to decide if permission is allowed or denied asynchronously for instance if you need to prompt the user, use eventArgs.permissionRequest.defer().</span></span> <span data-ttu-id="a5e87-338">アクセス許可要求は、getDeferredPermissionRequestById または getDeferredPermissionRequests を使って、対応する id 値を持つ DeferredPermissionRequest で allow () または deny () を呼び出すまで延期されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-338">The permission request will be deferred until you use webview.getDeferredPermissionRequestById or webview.getDeferredPermissionRequests and call allow() or deny() on the DeferredPermissionRequest with the corresponding id value.</span></span>

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

#### <span data-ttu-id="a5e87-339">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-339">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-340">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-340">Interface</span></span>** | [<span data-ttu-id="a5e87-341">PermissionRequestedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-341">PermissionRequestedEvent</span></span>](./webview/PermissionRequestedEvent.md) |
|**<span data-ttu-id="a5e87-342">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-342">Synchronous</span></span>** |<span data-ttu-id="a5e87-343">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-343">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-344">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-344">Bubbles</span></span>**     |<span data-ttu-id="a5e87-345">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-345">No</span></span> |   
|**<span data-ttu-id="a5e87-346">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-346">Cancelable</span></span>**  |<span data-ttu-id="a5e87-347">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-347">No</span></span> |    


### <span data-ttu-id="a5e87-348">Mswebviewプロセス</span><span class="sxs-lookup"><span data-stu-id="a5e87-348">MSWebViewProcessExited</span></span>

<span data-ttu-id="a5e87-349">**Webview**コンポーネントのプロセスが crashsed であることを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-349">Indicates that the **webview** component process crashsed.</span></span> <span data-ttu-id="a5e87-350">これは、アウトプロセスの WebView にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-350">This is only relevant for an out-of-process WebView.</span></span> <span data-ttu-id="a5e87-351">インプロセス WebView とは異なり、アウトプロセスの WebView を作成する方法については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-351">See the Remarks section for how to create an out-of-process WebView as opposed to an in-process WebView.</span></span> <span data-ttu-id="a5e87-352">このイベントが発生すると、対応する WebView はクラッシュ状態になります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-352">After this event fires, the corresponding WebView is put into a crashed state.</span></span> <span data-ttu-id="a5e87-353">最も一般的な WebView 固有のメソッドを呼び出したり、クラッシュした WebView のほとんどの WebView 固有のプロパティにアクセスすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-353">Calling most WebView specific methods or accessing most WebView specific properties on a crashed WebView will throw an exception.</span></span> <span data-ttu-id="a5e87-354">このイベントから回復するには、クラッシュした WebView を DOM から削除して、新しい WebView に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-354">To recover from this event, remove the crashed WebView from the DOM and replace it with a new WebView.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewProcessExited", handler);
webview.removeEventListener("MSWebViewProcessExited", handler);
```

#### <span data-ttu-id="a5e87-355">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-355">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-356">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-356">Interface</span></span>** | **<span data-ttu-id="a5e87-357">イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-357">Event</span></span>** |
|**<span data-ttu-id="a5e87-358">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-358">Synchronous</span></span>** |<span data-ttu-id="a5e87-359">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-359">Yes</span></span> |    
|**<span data-ttu-id="a5e87-360">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-360">Bubbles</span></span>**     |<span data-ttu-id="a5e87-361">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-361">No</span></span> |   
|**<span data-ttu-id="a5e87-362">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-362">Cancelable</span></span>**  |<span data-ttu-id="a5e87-363">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-363">No</span></span> |      


### <span data-ttu-id="a5e87-364">MSWebViewWebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="a5e87-364">MSWebViewWebResourceRequested</span></span>

<span data-ttu-id="a5e87-365">**Webview**要素内のページがリソースを要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-365">Raised when a page inside the **webview** element requests a resource.</span></span>

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

#### <span data-ttu-id="a5e87-366">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-366">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-367">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-367">Interface</span></span>** | [<span data-ttu-id="a5e87-368">WebResourceRequestedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-368">WebResourceRequestedEvent</span></span>](./webview/WebResourceRequestedEvent.md) |
|**<span data-ttu-id="a5e87-369">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-369">Synchronous</span></span>** |<span data-ttu-id="a5e87-370">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-370">Yes</span></span> |    
|**<span data-ttu-id="a5e87-371">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-371">Bubbles</span></span>**     |<span data-ttu-id="a5e87-372">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-372">No</span></span> |   
|**<span data-ttu-id="a5e87-373">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-373">Cancelable</span></span>**  |<span data-ttu-id="a5e87-374">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-374">No</span></span> |      


### <span data-ttu-id="a5e87-375">MSWebViewScriptNotify</span><span class="sxs-lookup"><span data-stu-id="a5e87-375">MSWebViewScriptNotify</span></span>

<span data-ttu-id="a5e87-376">**Webview**要素内のページから**ウィンドウ**を呼び出すときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-376">Raised when a page inside the **webview** element calls the **window.external.notify** method.</span></span> <span data-ttu-id="a5e87-377">この方法では、アプリの manifest's Applicationcontenturirfactorのルールと一致する Uri を含むドキュメント、または webview を設定することによって、プログラムによって許可されているドキュメントのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-377">The window.external.notify method is only available to documents with URIs that match rules in the app's manifest's ApplicationContentUriRules or that has been programatically allowed via setting webview.settings.isScriptNotifyAllowed to true.</span></span> <span data-ttu-id="a5e87-378">さらに、[外部] というウィンドウも表示できます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-378">Additionally window.external.notify is only available to the webview's top level document.</span></span>

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

#### <span data-ttu-id="a5e87-379">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-379">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-380">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-380">Interface</span></span>** | [<span data-ttu-id="a5e87-381">ScriptNotifyEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-381">ScriptNotifyEvent</span></span>](./webview/ScriptNotifyEvent.md) |
|**<span data-ttu-id="a5e87-382">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-382">Synchronous</span></span>** |<span data-ttu-id="a5e87-383">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-383">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-384">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-384">Bubbles</span></span>**     |<span data-ttu-id="a5e87-385">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-385">No</span></span> |   
|**<span data-ttu-id="a5e87-386">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-386">Cancelable</span></span>**  |<span data-ttu-id="a5e87-387">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-387">No</span></span> |      

### <span data-ttu-id="a5e87-388">MSWebViewUnsafeContentWarningDisplaying</span><span class="sxs-lookup"><span data-stu-id="a5e87-388">MSWebViewUnsafeContentWarningDisplaying</span></span>

<span data-ttu-id="a5e87-389">SmartScreen フィルターによって安全でないと報告されたコンテンツの警告ページ**が表示された**ときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-389">Occurs when the **webview** shows a warning page for content that was reported as unsafe by SmartScreen Filter.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
webview.removeEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
```

#### <span data-ttu-id="a5e87-390">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-390">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-391">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-391">Interface</span></span>** | **<span data-ttu-id="a5e87-392">イベント</span><span class="sxs-lookup"><span data-stu-id="a5e87-392">Event</span></span>** |
|**<span data-ttu-id="a5e87-393">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-393">Synchronous</span></span>** |<span data-ttu-id="a5e87-394">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-394">Yes</span></span> |    
|**<span data-ttu-id="a5e87-395">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-395">Bubbles</span></span>**     |<span data-ttu-id="a5e87-396">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-396">No</span></span> |   
|**<span data-ttu-id="a5e87-397">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-397">Cancelable</span></span>**  |<span data-ttu-id="a5e87-398">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-398">No</span></span> |    

### <span data-ttu-id="a5e87-399">MSWebViewUnsupportedUriSchemeIdentified</span><span class="sxs-lookup"><span data-stu-id="a5e87-399">MSWebViewUnsupportedUriSchemeIdentified</span></span>

<span data-ttu-id="a5e87-400">**Webview**でサポートされていない Uniform resource IDENTIFIER (URI) に移動したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-400">Raised when there is navigation to an Uniform Resource Identifier (URI) that the **webview** does not support.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
webview.removeEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
```

#### <span data-ttu-id="a5e87-401">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-401">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-402">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-402">Interface</span></span>** | [<span data-ttu-id="a5e87-403">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-403">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="a5e87-404">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-404">Synchronous</span></span>** |<span data-ttu-id="a5e87-405">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-405">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-406">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-406">Bubbles</span></span>**     |<span data-ttu-id="a5e87-407">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-407">No</span></span> |   
|**<span data-ttu-id="a5e87-408">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-408">Cancelable</span></span>**  |<span data-ttu-id="a5e87-409">あり</span><span class="sxs-lookup"><span data-stu-id="a5e87-409">Yes</span></span> |     

### <span data-ttu-id="a5e87-410">MSWebViewUnviewableContentIdentified</span><span class="sxs-lookup"><span data-stu-id="a5e87-410">MSWebViewUnviewableContentIdentified</span></span>

<span data-ttu-id="a5e87-411">**Webview**がサポートされていないコンテンツタイプで web コンテンツに移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-411">Raised when the **webview** attempts to navigate to web content with an unsupported content type.</span></span> <span data-ttu-id="a5e87-412">たとえば、現在、pdf は webview やナビゲーションでは現在サポートされていないため、PDF ドキュメントは移動せず、このイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-412">For example, PDFs are currently not supported by webview and navigations to PDF documents will not navigate and instead raise this event.</span></span>

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

#### <span data-ttu-id="a5e87-413">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a5e87-413">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-414">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5e87-414">Interface</span></span>** | [<span data-ttu-id="a5e87-415">UnviewableContentIdentifiedEvent</span><span class="sxs-lookup"><span data-stu-id="a5e87-415">UnviewableContentIdentifiedEvent</span></span>](./webview/UnviewableContentIdentifiedEvent.md) |
|**<span data-ttu-id="a5e87-416">同期</span><span class="sxs-lookup"><span data-stu-id="a5e87-416">Synchronous</span></span>** |<span data-ttu-id="a5e87-417">はい</span><span class="sxs-lookup"><span data-stu-id="a5e87-417">Yes</span></span>  |    
|**<span data-ttu-id="a5e87-418">バブル</span><span class="sxs-lookup"><span data-stu-id="a5e87-418">Bubbles</span></span>**     |<span data-ttu-id="a5e87-419">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-419">No</span></span> |   
|**<span data-ttu-id="a5e87-420">取り消し可能な</span><span class="sxs-lookup"><span data-stu-id="a5e87-420">Cancelable</span></span>**  |<span data-ttu-id="a5e87-421">なし</span><span class="sxs-lookup"><span data-stu-id="a5e87-421">No</span></span> |                 
         

## <span data-ttu-id="a5e87-422">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5e87-422">Methods</span></span>

### <span data-ttu-id="a5e87-423">Webview.addweballowedobject</span><span class="sxs-lookup"><span data-stu-id="a5e87-423">addWebAllowedObject</span></span>

<span data-ttu-id="a5e87-424">グローバルな Windows ランタイムオブジェクトを、 **webview**内のトップレベルドキュメントにグローバルパラメーターとして追加します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-424">Adds a native Windows Runtime object as a global parameter to the top-level document inside of a **webview**.</span></span>

<span data-ttu-id="a5e87-425">オブジェクトは、現在のドキュメントには挿入されませんが、webview でナビゲートする次のトップレベルのドキュメントになります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-425">The object is not injected into the current document, but rather the next top-level document to which the webview navigates.</span></span> <span data-ttu-id="a5e87-426">HTML ドキュメントのいずれかのスクリプトが実行される前にオブジェクトが挿入されるため、ドキュメントのグローバルスクリプトでオブジェクトに依存することができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-426">The object is injected before any script from the HTML document runs so you can rely on the object in your document's global script.</span></span>

<span data-ttu-id="a5e87-427">AddWebAllowedObject は、MSWebViewNavigationStarting イベントの間、または navigate メソッドを明示的に呼び出す前に使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-427">You should use addWebAllowedObject either during an MSWebViewNavigationStarting event or before explicitly calling a navigate method.</span></span> <span data-ttu-id="a5e87-428">この場合、オブジェクトは、対応するナビゲーションのドキュメントに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-428">In these cases the object is injected into the document of the corresponding navigation.</span></span> <span data-ttu-id="a5e87-429">他のコンテキストで通話を発信する場合、オブジェクトを挿入するドキュメントを特定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-429">Calling it in some other context, you don't have a way to be certain into what document you'll inject your object.</span></span>

<span data-ttu-id="a5e87-430">1つの行で addWebAllowedObject を複数回呼び出すと、複数のオブジェクトが文書に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-430">Calling addWebAllowedObject multiple times in a row will inject multiple objects into the document.</span></span> <span data-ttu-id="a5e87-431">明示的に通話を開始する前に、また対応する MSWebViewNavigationStarting イベント中にもう一度呼び出すと、両方の呼び出しが成功し、複数のオブジェクトが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-431">If you call it both before an explicit navigate call and then again during the corresponding MSWebViewNavigationStarting event, both calls will succeed and you'll have multiple objects injected.</span></span> <span data-ttu-id="a5e87-432">同じ name パラメーターを使用して複数の通話を発信する場合、前回の通話が優先され、その名前の前の呼び出しが無視されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-432">If you call multiple times with the same name parameter, the last call wins and the previous calls with that name are ignored.</span></span>

<span data-ttu-id="a5e87-433">移動に失敗した場合、またはリダイレクトされた場合、そのナビゲーションの addWebAllowedObject 呼び出しは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-433">If a navigate fails or is redirected, the addWebAllowedObject calls for that navigation are ignored.</span></span> <span data-ttu-id="a5e87-434">リダイレクトを処理する必要がある場合は、MSWebViewNavigationStarting 開始イベントウォッチをサブスクライブして、アプリケーションに適した条件に従って addWebAllowedObject をもう一度呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-434">If you want to handle redirects you can subscribe to the MSWebViewNavigationStarting event watch for redirects and call addWebAllowedObject again according to whatever criteria is appropriate for your application.</span></span> <span data-ttu-id="a5e87-435">同様に、ドキュメントは、addWebAllowedObject によって挿入されたオブジェクトを他の場所に移動すると、そのドキュメントには次のドキュメントに引き継がれません。そのためには、addWebAllowedObject を明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-435">Similarly, once a document navigates away any objects injected via addWebAllowedObject for that document will not carry over to the next document and you'll need to explicitly call addWebAllowedObject if you want them to carry over.</span></span>

<span data-ttu-id="a5e87-436">WinRT アクセスを持たないドキュメントに対して addWebAllowedObject を呼び出した場合、または[Applicationcontenturirfactorを使って Allowforwebonly アクセス](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule)が与えられている場合は、オブジェクトは、オブジェクトに対して、オブジェクトに対してのみ挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-436">If you call addWebAllowedObject for a document that has no WinRT access otherwise, or if it has [AllowForWebOnly access via ApplicationContentUriRules](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule) then the object will only be injected if the object has the Windows.Foundation.Metadata.AllowForWeb metadata attribute.</span></span> <span data-ttu-id="a5e87-437">それ以外の場合は、埋め込みは失敗し、JavaScript 開発者コンソールにエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-437">Otherwise injection will fail and an error will be reported to the JavaScript developer console.</span></span> <span data-ttu-id="a5e87-438">完全な WinRT アクセスを持つドキュメントで呼び出された場合は、AllowForWeb 属性に関係なく、そのオブジェクトが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-438">If called on a document that has full WinRT access, then the object will be injected regardless of the AllowForWeb attribute.</span></span> 

<span data-ttu-id="a5e87-439">さらに、オブジェクトは IAgileObject インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-439">Additionally, the object must implement the IAgileObject interface.</span></span> <span data-ttu-id="a5e87-440">これは、XAML と HTML の webview 要素がアプリの ASTA view スレッドで実行され、WebView の JavaScript スレッドが異なる ASTA スレッドであるため、可能であればアプリの表示スレッドをブロックすることなく、そのオブジェクトを JavaScript スレッドで実行できるようにすることをアプリ開発者に促します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-440">This is because the XAML and HTML webview elements run on their app's ASTA view threads and the WebView's JavaScript thread is a different ASTA thread and we want to encourage app developers to ensure their object can run on the JavaScript thread without blocking the app view thread if possible.</span></span>

<span data-ttu-id="a5e87-441">Name パラメーターは、有効な JavaScript プロパティ名である必要があります。そうでないと、呼び出しは通知なしで失敗します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-441">The name parameter must be a valid JavaScript property name otherwise the call will fail silently.</span></span> <span data-ttu-id="a5e87-442">グローバルオブジェクトに既に存在するプロパティの名前の場合、そのプロパティが構成可能であれば、そのプロパティは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-442">If the name is of a property that already exists on the global object then that property is overwritten if the property is configurable.</span></span> <span data-ttu-id="a5e87-443">グローバルオブジェクトの構成可能ではないプロパティは上書きされず、addWebAllowedObject 呼び出しは黙って失敗します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-443">Non-configurable properties on the global object are not overwritten and the addWebAllowedObject call fails silently.</span></span> <span data-ttu-id="a5e87-444">AddWebAllowedObject を使って作成された JavaScript プロパティは、書き込み可能、構成可能、列挙可能です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-444">JavaScript properties created via addWebAllowedObject are writable, configurable, and enumerable.</span></span>

```js
let name = "exampleProperty";
webview.addWebAllowedObject(name, applicationObject);
webview.navigate("https://example.com/"); // applicationObject will be available as window.exampleProperty on https://example.com
```

#### <span data-ttu-id="a5e87-445">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-445">Parameters</span></span>
*<span data-ttu-id="a5e87-446">name</span><span class="sxs-lookup"><span data-stu-id="a5e87-446">name</span></span>*
* <span data-ttu-id="a5e87-447">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-447">Type: **String**</span></span>
* <span data-ttu-id="a5e87-448">**Webview**でドキュメントに公開するオブジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="a5e87-448">The name of the object to expose to the document in the **webview**.</span></span>

*<span data-ttu-id="a5e87-449">applicationObject</span><span class="sxs-lookup"><span data-stu-id="a5e87-449">applicationObject</span></span>*
* <span data-ttu-id="a5e87-450">Type: **Object**</span><span class="sxs-lookup"><span data-stu-id="a5e87-450">Type: **Object**</span></span>
* <span data-ttu-id="a5e87-451">**Webview**でドキュメントに公開するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a5e87-451">The object to expose to the document in the **webview**.</span></span>

#### <span data-ttu-id="a5e87-452">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-452">Return value</span></span>
<span data-ttu-id="a5e87-453">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-453">This method does not return a value.</span></span>

#### <span data-ttu-id="a5e87-454">その他の機能と要件</span><span class="sxs-lookup"><span data-stu-id="a5e87-454">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-455">サポートされている最小クライアント数</span><span class="sxs-lookup"><span data-stu-id="a5e87-455">Minimum supported client</span></span>** |<span data-ttu-id="a5e87-456">Windows 10 [Windows ストアアプリのみ]</span><span class="sxs-lookup"><span data-stu-id="a5e87-456">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="a5e87-457">サポートされている最小のサーバー</span><span class="sxs-lookup"><span data-stu-id="a5e87-457">Minimum supported server</span></span>** |<span data-ttu-id="a5e87-458">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-458">None supported</span></span> |   
|**<span data-ttu-id="a5e87-459">サポートされている最小電話</span><span class="sxs-lookup"><span data-stu-id="a5e87-459">Minimum supported phone</span></span>**  |<span data-ttu-id="a5e87-460">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-460">None supported</span></span> |  

### <span data-ttu-id="a5e87-461">buildLocalStreamUri</span><span class="sxs-lookup"><span data-stu-id="a5e87-461">buildLocalStreamUri</span></span>

<span data-ttu-id="a5e87-462">[NavigateToLocalStreamUri](#methods)に渡すことができる URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-462">Creates a URI that you can pass to [navigateToLocalStreamUri](#methods).</span></span>

```js
var string = webview.buildLocalStreamUri(contentIdentifier, relativePath);
```

#### <span data-ttu-id="a5e87-463">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-463">Parameters</span></span>
*<span data-ttu-id="a5e87-464">contentIdentifier</span><span class="sxs-lookup"><span data-stu-id="a5e87-464">contentIdentifier</span></span>*
* <span data-ttu-id="a5e87-465">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-465">Type: **String**</span></span>
* <span data-ttu-id="a5e87-466">URI で参照されているコンテンツの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a5e87-466">A unique identifier for the content the URI is referencing.</span></span> <span data-ttu-id="a5e87-467">これにより、URI のルートが定義されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-467">This defines the root of the URI.</span></span>

*<span data-ttu-id="a5e87-468">relativePath</span><span class="sxs-lookup"><span data-stu-id="a5e87-468">relativePath</span></span>*
* <span data-ttu-id="a5e87-469">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-469">Type: **String**</span></span>
* <span data-ttu-id="a5e87-470">ルートを基準とした、リソースへのパス。</span><span class="sxs-lookup"><span data-stu-id="a5e87-470">The path to the resource, relative to the root.</span></span>

#### <span data-ttu-id="a5e87-471">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-471">Return value</span></span>
<span data-ttu-id="a5e87-472">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-472">Type: **String**</span></span>

<span data-ttu-id="a5e87-473">*ContentIdentifier*と*relativePath*の結合と正規化によって作成された URI。</span><span class="sxs-lookup"><span data-stu-id="a5e87-473">The URI created by combining and normalizing the *contentIdentifier* and *relativePath*.</span></span>

#### <span data-ttu-id="a5e87-474">例</span><span class="sxs-lookup"><span data-stu-id="a5e87-474">Example</span></span>

<span data-ttu-id="a5e87-475">次の例は、一般的なユースケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="a5e87-475">The following example illustrates a typical use case.</span></span> 

```js
var webview = document.createElement("x-ms-webview"); //Instantiate the webview element
var localStreamUri = webview.buildLocalStreamUri(contentIdentifier, relativePath); //Create URI to pass to navigateToLocalStreamUri method
webview.navigateToLocalStreamUri(localStreamUri, streamResolver); //Load the local web content 
```  

### <span data-ttu-id="a5e87-476">capturePreviewToBlobAsync</span><span class="sxs-lookup"><span data-stu-id="a5e87-476">capturePreviewToBlobAsync</span></span>

<span data-ttu-id="a5e87-477">現在の[webview 要素](./webview.md)のイメージを作成し、指定された image 要素に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-477">Creates an image of the current [webview element](./webview.md) and write it to the specified image element.</span></span>

```js
var capturePreviewToBlobAsync = webview.capturePreviewToBlobAsync();
```

#### <span data-ttu-id="a5e87-478">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-478">Parameters</span></span>
<span data-ttu-id="a5e87-479">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-479">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-480">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-480">Return value</span></span>
<span data-ttu-id="a5e87-481">Type: **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="a5e87-481">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="a5e87-482">完了時に、画像を含む**Blob**オブジェクトを提供する**MSWebViewAsyncOperation**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a5e87-482">An **MSWebViewAsyncOperation** object that, when it completes, provides a **Blob** object that contains the image.</span></span> <span data-ttu-id="a5e87-483">**CapturePreviewToBlobAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-483">When using **capturePreviewToBlobAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="a5e87-484">イベントハンドラーを適用した後で、 [MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md)オブジェクトの start メソッドを呼び出して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-484">After applying the event handlers, call the start method on the [MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md) object to execute the operation.</span></span>

### <span data-ttu-id="a5e87-485">captureSelectedContentToDataPackageAsync</span><span class="sxs-lookup"><span data-stu-id="a5e87-485">captureSelectedContentToDataPackageAsync</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a5e87-486">このメソッドは廃止され、既知の問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="a5e87-486">This method has been deprecated and has a known issue.</span></span> <span data-ttu-id="a5e87-487">このメソッドは、実稼働コードでは使わないでください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-487">Avoid using this method in your production code.</span></span> 

<span data-ttu-id="a5e87-488">**Webview**内で選択されたコンテンツを含む[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)を非同期的に取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-488">Asynchronously gets a [DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) that contains the selected content within the **webview**.</span></span>

```js
var msWebViewAsyncOperation = webview.captureSelectedContentToDataPackageAsync();
```

#### <span data-ttu-id="a5e87-489">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-489">Parameters</span></span>
<span data-ttu-id="a5e87-490">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-490">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-491">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-491">Return value</span></span>
<span data-ttu-id="a5e87-492">Type: **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="a5e87-492">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="a5e87-493">完了時に、画像を含む[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)オブジェクトを提供する**MSWebViewAsyncOperation**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a5e87-493">An **MSWebViewAsyncOperation** object that, when it completes, provides a [DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) object that contains the image.</span></span> <span data-ttu-id="a5e87-494">**CaptureSelectedContentToDataPackageAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-494">When using **captureSelectedContentToDataPackageAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="a5e87-495">イベントハンドラーを適用した後で、MSWebViewAsyncOperation オブジェクトの start メソッドを呼び出して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-495">After applying the event handlers, call the start method on the MSWebViewAsyncOperation object to execute the operation.</span></span>

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

### <span data-ttu-id="a5e87-496">invokeScriptAsync</span><span class="sxs-lookup"><span data-stu-id="a5e87-496">invokeScriptAsync</span></span>

<span data-ttu-id="a5e87-497">非同期操作として、指定されたスクリプト関数を現在読み込まれている HTML から特定の引数を指定して実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-497">As an asynchronous action, executes the specified script function from the currently loaded HTML, with specific arguments.</span></span>

```js
webview.invokeScriptAsync(functionName, ...args)
```

#### <span data-ttu-id="a5e87-498">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-498">Parameters</span></span>

**<span data-ttu-id="a5e87-499">functionName</span><span class="sxs-lookup"><span data-stu-id="a5e87-499">functionName</span></span>**
* <span data-ttu-id="a5e87-500">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-500">Type: **String**</span></span>
* <span data-ttu-id="a5e87-501">呼び出す関数の名前。</span><span class="sxs-lookup"><span data-stu-id="a5e87-501">The name of the function to invoke.</span></span> <span data-ttu-id="a5e87-502">これは、WebView の最上位レベルのドキュメントのグローバルウィンドウオブジェクトのプロパティ名です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-502">This is a property name on the global window object of the WebView's top level document.</span></span> <span data-ttu-id="a5e87-503">これは、eval や open などの組み込みのグローバル関数の場合もあります。グローバルウィンドウオブジェクトのスクリプト定義関数の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-503">This can be a built-in global function like eval or open, or it can be a script defined function on the global window object.</span></span> <span data-ttu-id="a5e87-504">WebView のトップレベルドキュメント内の関数のみを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-504">Only functions in the top level document of the WebView may be invoked.</span></span>

**<span data-ttu-id="a5e87-505">引数</span><span class="sxs-lookup"><span data-stu-id="a5e87-505">args</span></span>**
* <span data-ttu-id="a5e87-506">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-506">Type: **String**</span></span>
* <span data-ttu-id="a5e87-507">呼び出された関数に渡すオプションの文字列パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a5e87-507">Optional string parameters to pass to the invoked function.</span></span> <span data-ttu-id="a5e87-508">FunctionName の後、invokeScriptAsync に対する追加パラメーターは、呼び出された関数に渡される文字列です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-508">After functionName, any additional parameters to invokeScriptAsync are strings passed to the invoked function.</span></span>

#### <span data-ttu-id="a5e87-509">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-509">Return value</span></span>
<span data-ttu-id="a5e87-510">Type: **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="a5e87-510">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="a5e87-511">**InvokeScriptAsync**を使う場合は、操作を定義した後で成功とエラーのハンドラーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-511">When using **invokeScriptAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="a5e87-512">イベントハンドラーを適用した後、 **MSWebViewAsyncOperation**を呼び出して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-512">After applying the event handlers, call **MSWebViewAsyncOperation.start** to execute the operation.</span></span> <span data-ttu-id="a5e87-513">MSWebViewAsyncOperation の complete イベントが発生した場合、MSWebViewAsyncOperation の result プロパティは、関数を呼び出すときの文字列の戻り値になります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-513">If the MSWebViewAsyncOperation's complete event fires then the MSWebViewAsyncOperation's result property is the string return value from invoking the function.</span></span> <span data-ttu-id="a5e87-514">呼び出された関数の戻り値を使うと、WebView コンテンツが WebView ホストに同期された通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-514">Using the invoked function's return value allows for the WebView content to communication synchronously back to the WebView host.</span></span> <span data-ttu-id="a5e87-515">代わりに、WebView のコンテンツは、Web ビューのホストに非同期的に伝達されるようにするには、MSWebViewScriptNotify イベントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-515">To instead have the WebView content communicate asynchronously back to the WebView host see the MSWebViewScriptNotify event.</span></span> <span data-ttu-id="a5e87-516">呼び出された関数が未処理の例外をスローすると、MSWebViewAsyncOperation のエラーイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-516">If the function invoked throws an unhandled exception then the MSWebViewAsyncOperation's error event will fire.</span></span> 

```js
const functionName = "eval";
const args = ["'Current URL: ' + document.location.href"];

const asyncOp = webview.invokeScriptAsync(functionName, ...args);

asyncOp.onerror = () => console.error("Error: " + asyncOp.error);
asyncOp.oncomplete = () => console.log("Result: " + asyncOp.result); // Logs 'Current URL: about:blank'
asyncOp.start();
```

### <span data-ttu-id="a5e87-517">getDeferredPermissionRequests</span><span class="sxs-lookup"><span data-stu-id="a5e87-517">getDeferredPermissionRequests</span></span>

<span data-ttu-id="a5e87-518">**Webview**コントロール内のコンテンツによって発行される、延期されたアクセス許可要求の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-518">Returns a list of deferred permission requests issued by content in the **webview** control.</span></span>

```js
var sequence<PermissionRequest> = x-ms-webview.getDeferredPermissionRequests();
```

#### <span data-ttu-id="a5e87-519">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-519">Parameters</span></span>
<span data-ttu-id="a5e87-520">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-520">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-521">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-521">Return value</span></span>
<span data-ttu-id="a5e87-522">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span><span class="sxs-lookup"><span data-stu-id="a5e87-522">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span></span>

<span data-ttu-id="a5e87-523">指定した延期アクセス許可要求。</span><span class="sxs-lookup"><span data-stu-id="a5e87-523">The specified deferred permission request.</span></span>

#### <span data-ttu-id="a5e87-524">その他の機能と要件</span><span class="sxs-lookup"><span data-stu-id="a5e87-524">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-525">サポートされている最小クライアント数</span><span class="sxs-lookup"><span data-stu-id="a5e87-525">Minimum supported client</span></span>** |<span data-ttu-id="a5e87-526">Windows 10 [Windows ストアアプリのみ]</span><span class="sxs-lookup"><span data-stu-id="a5e87-526">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="a5e87-527">サポートされている最小のサーバー</span><span class="sxs-lookup"><span data-stu-id="a5e87-527">Minimum supported server</span></span>** |<span data-ttu-id="a5e87-528">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-528">None supported</span></span>|   
|**<span data-ttu-id="a5e87-529">サポートされている最小電話</span><span class="sxs-lookup"><span data-stu-id="a5e87-529">Minimum supported phone</span></span>**  |<span data-ttu-id="a5e87-530">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-530">None supported</span></span> |    


### <span data-ttu-id="a5e87-531">getDeferredPermissionRequestById</span><span class="sxs-lookup"><span data-stu-id="a5e87-531">getDeferredPermissionRequestById</span></span>

<span data-ttu-id="a5e87-532">指定された延期アクセス許可要求を返します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-532">Returns the specified deferred permission request.</span></span> 

```js
var deferredPermissionRequest = x-ms-webview.getDeferredPermissionRequestById(id);
```

#### <span data-ttu-id="a5e87-533">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-533">Parameters</span></span>
*<span data-ttu-id="a5e87-534">id</span><span class="sxs-lookup"><span data-stu-id="a5e87-534">id</span></span>*
* <span data-ttu-id="a5e87-535">種類:**符号なし長**</span><span class="sxs-lookup"><span data-stu-id="a5e87-535">Type: **unsigned long**</span></span>
* <span data-ttu-id="a5e87-536">取得する延期されたアクセス許可要求の ID です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-536">The ID of the deferred permission request you wish to get.</span></span>

#### <span data-ttu-id="a5e87-537">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-537">Return value</span></span>
<span data-ttu-id="a5e87-538">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span><span class="sxs-lookup"><span data-stu-id="a5e87-538">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span></span>

<span data-ttu-id="a5e87-539">指定した延期アクセス許可要求。</span><span class="sxs-lookup"><span data-stu-id="a5e87-539">The specified deferred permission request.</span></span>

#### <span data-ttu-id="a5e87-540">その他の機能と要件</span><span class="sxs-lookup"><span data-stu-id="a5e87-540">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="a5e87-541">サポートされている最小クライアント数</span><span class="sxs-lookup"><span data-stu-id="a5e87-541">Minimum supported client</span></span>** |<span data-ttu-id="a5e87-542">Windows 10 [Windows ストアアプリのみ]</span><span class="sxs-lookup"><span data-stu-id="a5e87-542">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="a5e87-543">サポートされている最小のサーバー</span><span class="sxs-lookup"><span data-stu-id="a5e87-543">Minimum supported server</span></span>** |<span data-ttu-id="a5e87-544">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-544">None supported</span></span>|   
|**<span data-ttu-id="a5e87-545">サポートされている最小電話</span><span class="sxs-lookup"><span data-stu-id="a5e87-545">Minimum supported phone</span></span>**  |<span data-ttu-id="a5e87-546">サポートなし</span><span class="sxs-lookup"><span data-stu-id="a5e87-546">None supported</span></span> | 

### <span data-ttu-id="a5e87-547">goBack</span><span class="sxs-lookup"><span data-stu-id="a5e87-547">goBack</span></span>

<span data-ttu-id="a5e87-548">ナビゲーション履歴で、 **webview**を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-548">Navigates the **webview** to the previous page in the navigation history.</span></span> 

```js
webview.goBack();
```

#### <span data-ttu-id="a5e87-549">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-549">Parameters</span></span>
<span data-ttu-id="a5e87-550">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-550">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-551">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-551">Return value</span></span>
<span data-ttu-id="a5e87-552">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-552">This method does not return a value.</span></span>

### <span data-ttu-id="a5e87-553">goForward</span><span class="sxs-lookup"><span data-stu-id="a5e87-553">goForward</span></span>

<span data-ttu-id="a5e87-554">**Webview**をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-554">Navigates the **webview** to the next page in the navigation history.</span></span> 

```js
webview.goForward();
```

#### <span data-ttu-id="a5e87-555">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-555">Parameters</span></span>
<span data-ttu-id="a5e87-556">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-556">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-557">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-557">Return value</span></span>
<span data-ttu-id="a5e87-558">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-558">This method does not return a value.</span></span>

### <span data-ttu-id="a5e87-559">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="a5e87-559">navigate</span></span>

<span data-ttu-id="a5e87-560">指定した Uniform Resource Identifier (URI) で HTML コンテンツを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-560">Loads the HTML content at the specified Uniform Resource Identifier (URI).</span></span> 

```js
webview.navigate(uri);
```

#### <span data-ttu-id="a5e87-561">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-561">Parameters</span></span>

**<span data-ttu-id="a5e87-562">uri</span><span class="sxs-lookup"><span data-stu-id="a5e87-562">uri</span></span>**
* <span data-ttu-id="a5e87-563">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-563">Type: **String**</span></span>
* <span data-ttu-id="a5e87-564">読み込む URI。</span><span class="sxs-lookup"><span data-stu-id="a5e87-564">The URI to load.</span></span>

#### <span data-ttu-id="a5e87-565">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-565">Return value</span></span>
<span data-ttu-id="a5e87-566">このメソッドは値を返しません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-566">This  method does not return a value.</span></span>

### <span data-ttu-id="a5e87-567">navigateFocus</span><span class="sxs-lookup"><span data-stu-id="a5e87-567">navigateFocus</span></span>

<span data-ttu-id="a5e87-568">**Webview**にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-568">Navigates focus onto the **webview**.</span></span> <span data-ttu-id="a5e87-569">Webview の最上位レベルのドキュメントの window's イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-569">Fires the webview's top level document's window's navigatingfocus event.</span></span> <span data-ttu-id="a5e87-570">Navigatingfocus イベントで使われている FocusNavigationEvent args は、元のパラメーターを除いて navigateFocus に提供されているパラメーターと一致しますが、元のパラメーターは、ホストドキュメントの座標空間から webview の最上位レベルのドキュメントの座標空間に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-570">The FocusNavigationEvent args used in the navigatingfocus event match the parameters provided to navigateFocus except the origin parameters are translated from the host document's coordinate space to the coordinate space of the webview's top level document.</span></span> <span data-ttu-id="a5e87-571">Webview からホストにフォーカスを転送するには、webview departingFocus イベントと対応する departFocus メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-571">See the webview departingFocus event and corresponding window.departFocus method for transferring focus from the webview to the host.</span></span> <span data-ttu-id="a5e87-572">この方法を使用するキーボードまたはゲームパッドによるフォーカスナビゲーションの実装例については、「 [TVJS の方向ナビゲーションライブラリ](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-572">See the [TVJS's Direction Navigation library](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) for an example of an implementation of focus navigation via keyboard or gamepad that uses this method.</span></span>

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

#### <span data-ttu-id="a5e87-573">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-573">Parameters</span></span>
*<span data-ttu-id="a5e87-574">ナビゲーションの理由</span><span class="sxs-lookup"><span data-stu-id="a5e87-574">navigationReason</span></span>*
* <span data-ttu-id="a5e87-575">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-575">Type: **String**</span></span>
* <span data-ttu-id="a5e87-576">ナビゲーションの理由。</span><span class="sxs-lookup"><span data-stu-id="a5e87-576">The reason for the navigation.</span></span> <span data-ttu-id="a5e87-577">値は、"left"、"up"、"right"、または "down" のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-577">The value should be either "left", "up", "right", or "down".</span></span> <span data-ttu-id="a5e87-578">フォーカスが現在フォーカスされている要素から移動する方向です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-578">It is the direction in which focus is moving away from the currently focused element.</span></span>

*<span data-ttu-id="a5e87-579">cdn</span><span class="sxs-lookup"><span data-stu-id="a5e87-579">origin</span></span>*
* <span data-ttu-id="a5e87-580">Type: **Object**</span><span class="sxs-lookup"><span data-stu-id="a5e87-580">Type: **Object**</span></span>
* <span data-ttu-id="a5e87-581">ナビゲーションの起点。</span><span class="sxs-lookup"><span data-stu-id="a5e87-581">The origin of the navigation.</span></span> <span data-ttu-id="a5e87-582">プロパティが "原点左"、"原点の先頭"、"原点の幅"、"原点の高さ" というプロパティを持つ JavaScript オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a5e87-582">This is a JavaScript object with properties "originLeft", "originTop", "originWidth", and "originHeight".</span></span> <span data-ttu-id="a5e87-583">これらの値は、フォーカスが移動する現在フォーカスのある要素の位置とサイズを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e87-583">These values should describe the position and size of the currently focused element away from which focus is moving.</span></span>

#### <span data-ttu-id="a5e87-584">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-584">Return value</span></span>
<span data-ttu-id="a5e87-585">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-585">This method does not return a value.</span></span>

### <span data-ttu-id="a5e87-586">navigateToLocalStreamUri</span><span class="sxs-lookup"><span data-stu-id="a5e87-586">navigateToLocalStreamUri</span></span>

<span data-ttu-id="a5e87-587">[**Uritostreamresolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync)を使って、指定された URI でローカル web コンテンツを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-587">Loads local web content at the specified URI using a [**UriToStreamResolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync).</span></span>

```js
webview.navigateToLocalStreamUri(source, streamResolver); 
```

#### <span data-ttu-id="a5e87-588">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-588">Parameters</span></span>

*<span data-ttu-id="a5e87-589">ソース</span><span class="sxs-lookup"><span data-stu-id="a5e87-589">source</span></span>*
* <span data-ttu-id="a5e87-590">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-590">Type: **String**</span></span>
* <span data-ttu-id="a5e87-591">読み込むローカルの HTML コンテンツを識別する ms ローカルストリーム URI。</span><span class="sxs-lookup"><span data-stu-id="a5e87-591">An ms-local-stream URI identifying the local HTML content to load.</span></span> <span data-ttu-id="a5e87-592">この文字列は、 [**Buildlocalstreamuri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri)を使って作成します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-592">Create this string using [**buildLocalStreamUri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri).</span></span>

*<span data-ttu-id="a5e87-593">streamResolver</span><span class="sxs-lookup"><span data-stu-id="a5e87-593">streamResolver</span></span>*
* <span data-ttu-id="a5e87-594">種類: any</span><span class="sxs-lookup"><span data-stu-id="a5e87-594">Type: any</span></span>
* <span data-ttu-id="a5e87-595">URI をストリームに変換して読み込むリゾルバー。</span><span class="sxs-lookup"><span data-stu-id="a5e87-595">A resolver that converts the URI into a stream to load.</span></span>

#### <span data-ttu-id="a5e87-596">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-596">Return value</span></span>
<span data-ttu-id="a5e87-597">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-597">This method does not return a value.</span></span>

### <span data-ttu-id="a5e87-598">navigateToString</span><span class="sxs-lookup"><span data-stu-id="a5e87-598">navigateToString</span></span>

<span data-ttu-id="a5e87-599">指定した HTML コンテンツを新しい文書として読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a5e87-599">Loads the specified HTML content as a new document.</span></span> 

```js
webview.navigateToString(contents);
```

#### <span data-ttu-id="a5e87-600">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-600">Parameters</span></span>

*<span data-ttu-id="a5e87-601">数式</span><span class="sxs-lookup"><span data-stu-id="a5e87-601">contents</span></span>*
* <span data-ttu-id="a5e87-602">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-602">Type: **String**</span></span>
* <span data-ttu-id="a5e87-603">表示する HTML コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a5e87-603">The HTML content to display.</span></span>

#### <span data-ttu-id="a5e87-604">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-604">Return value</span></span>
<span data-ttu-id="a5e87-605">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-605">This method does not return a value.</span></span>

### <span data-ttu-id="a5e87-606">navigateWithHttpRequestMessage</span><span class="sxs-lookup"><span data-stu-id="a5e87-606">navigateWithHttpRequestMessage</span></span>

<span data-ttu-id="a5e87-607">Webview を、POST 要求と HTTP ヘッダー付きの Uniform Resource Identifier (URI) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-607">Navigates the webview to a Uniform Resource Identifier (URI) with a POST request and HTTP headers.</span></span> 

```js
webview.navigateWithHttpRequestMessage(requestMessage);
```

#### <span data-ttu-id="a5e87-608">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-608">Parameters</span></span>

*<span data-ttu-id="a5e87-609">サーバーから</span><span class="sxs-lookup"><span data-stu-id="a5e87-609">requestMessage</span></span>*
* <span data-ttu-id="a5e87-610">Type: **HttpRequestMessage**</span><span class="sxs-lookup"><span data-stu-id="a5e87-610">Type: **HttpRequestMessage**</span></span>
* <span data-ttu-id="a5e87-611">HTTP 要求の詳細。</span><span class="sxs-lookup"><span data-stu-id="a5e87-611">The details of the HTTP request.</span></span> 

#### <span data-ttu-id="a5e87-612">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-612">Return value</span></span>
<span data-ttu-id="a5e87-613">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-613">This method does not return a value.</span></span>

#### <span data-ttu-id="a5e87-614">注釈</span><span class="sxs-lookup"><span data-stu-id="a5e87-614">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a5e87-615">この要求に、認証資格情報などのヘッダーを追加する場合は、以降の子要求にもそのヘッダーが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-615">If you add additional headers to this request, such as authentication credentials, remember that those headers will also be included with any subsequent child requests.</span></span> <span data-ttu-id="a5e87-616">機密情報が誤って開示されないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-616">Use caution to prevent accidental disclosure of confidential or personal information.</span></span> 


### <span data-ttu-id="a5e87-617">非</span><span class="sxs-lookup"><span data-stu-id="a5e87-617">refresh</span></span> 

<span data-ttu-id="a5e87-618">**Webview**内の現在のコンテンツを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="a5e87-618">Reloads the current content in the **webview**.</span></span> 

```js
webview.refresh();
```

#### <span data-ttu-id="a5e87-619">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-619">Parameters</span></span>
<span data-ttu-id="a5e87-620">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-620">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-621">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-621">Return value</span></span>
<span data-ttu-id="a5e87-622">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-622">This method does not return a value.</span></span>


### <span data-ttu-id="a5e87-623">stop</span><span class="sxs-lookup"><span data-stu-id="a5e87-623">stop</span></span>

<span data-ttu-id="a5e87-624">現在の**webview**ナビゲーションまたはダウンロードを中断します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-624">Halts the current **webview** navigation or download.</span></span> 

```js
webview.stop();
```

#### <span data-ttu-id="a5e87-625">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5e87-625">Parameters</span></span>
<span data-ttu-id="a5e87-626">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-626">This method has no parameters.</span></span>

#### <span data-ttu-id="a5e87-627">戻り値</span><span class="sxs-lookup"><span data-stu-id="a5e87-627">Return value</span></span>
<span data-ttu-id="a5e87-628">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e87-628">This method does not return a value.</span></span>


## <span data-ttu-id="a5e87-629">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a5e87-629">Properties</span></span>

### <span data-ttu-id="a5e87-630">canGoBack</span><span class="sxs-lookup"><span data-stu-id="a5e87-630">canGoBack</span></span>

<span data-ttu-id="a5e87-631">**Webview**が後方に移動できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-631">Gets a value that indicates whether the **webview** can navigate backward.</span></span>

<span data-ttu-id="a5e87-632">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-632">This property is read-only.</span></span>

```js
var canGoBack = webview.canGoBack;
```

#### <span data-ttu-id="a5e87-633">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-633">Property value</span></span>
<span data-ttu-id="a5e87-634">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="a5e87-634">Type: **Boolean**</span></span>

<span data-ttu-id="a5e87-635">**Webview**を後方に移動できる場合は**True** 。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-635">**True** if the **webview** can navigate backward; otherwise, **false**.</span></span>

### <span data-ttu-id="a5e87-636">canGoForward</span><span class="sxs-lookup"><span data-stu-id="a5e87-636">canGoForward</span></span>

<span data-ttu-id="a5e87-637">**Webview**を前方に移動できるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-637">Gets a value that indicates whether the **webview** can navigate forward.</span></span>

<span data-ttu-id="a5e87-638">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-638">This property is read-only.</span></span>

```js
var canGoForward = webview.canGoForward;
```

#### <span data-ttu-id="a5e87-639">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-639">Property value</span></span>
<span data-ttu-id="a5e87-640">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="a5e87-640">Type: **Boolean**</span></span>

<span data-ttu-id="a5e87-641">次に、 **webview**を移動できる場合は**True** 。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-641">**True** if the **webview** can navigate forward; otherwise, **false**.</span></span>

### <span data-ttu-id="a5e87-642">containsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="a5e87-642">containsFullScreenElement</span></span>

<span data-ttu-id="a5e87-643">**Webview**に全画面をサポートする要素が含まれているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-643">Gets a value that indicates whether the **webview** contains an element that supports full screen.</span></span> <span data-ttu-id="a5e87-644">詳細については、Mswebview・ Fullfullelementchanged イベントに関する情報をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5e87-644">See the MSWebViewContainsFullScreenElementChanged event for more info.</span></span>

<span data-ttu-id="a5e87-645">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-645">This property is read-only.</span></span>

```js
var containsFullScreenElement = webview.containsFullScreenElement;
```

#### <span data-ttu-id="a5e87-646">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-646">Property value</span></span>
<span data-ttu-id="a5e87-647">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="a5e87-647">Type: **Boolean**</span></span>

<span data-ttu-id="a5e87-648">全画面表示をサポートする要素が**webview**に含まれている場合は**True**です。それ以外の場合は**false**です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-648">**True** if the **webview** contains an element that supports full screen; otherwise, **false**.</span></span>


### <span data-ttu-id="a5e87-649">documentTitle</span><span class="sxs-lookup"><span data-stu-id="a5e87-649">documentTitle</span></span>

<span data-ttu-id="a5e87-650">**Webview**に現在表示されているページのタイトルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-650">Gets the title of the page currently displayed in the **webview**.</span></span> 

<span data-ttu-id="a5e87-651">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-651">This property is read-only.</span></span>

```js
var documentTitle = webview.documentTitle;
```

#### <span data-ttu-id="a5e87-652">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-652">Property value</span></span>
<span data-ttu-id="a5e87-653">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-653">Type: **String**</span></span>

<span data-ttu-id="a5e87-654">ページタイトル。</span><span class="sxs-lookup"><span data-stu-id="a5e87-654">The page title.</span></span>

### <span data-ttu-id="a5e87-655">height</span><span class="sxs-lookup"><span data-stu-id="a5e87-655">height</span></span>

<span data-ttu-id="a5e87-656">**Webview**の高さを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-656">Gets or sets the height of the **webview**.</span></span> 

```js
var height = webview.height;
webview.height = height;

```

#### <span data-ttu-id="a5e87-657">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-657">Property value</span></span>
<span data-ttu-id="a5e87-658">種類:**数値**</span><span class="sxs-lookup"><span data-stu-id="a5e87-658">Type: **Number**</span></span>

<span data-ttu-id="a5e87-659">**Webview**の高さです。</span><span class="sxs-lookup"><span data-stu-id="a5e87-659">The height of the **webview**.</span></span> 


### <span data-ttu-id="a5e87-660">プロセス</span><span class="sxs-lookup"><span data-stu-id="a5e87-660">process</span></span>

<span data-ttu-id="a5e87-661">**Webview**プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-661">Gets the **webview** process.</span></span>

<span data-ttu-id="a5e87-662">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-662">This property is read-only.</span></span>

```js
var process = webview.process;
webview.process = process;
```

#### <span data-ttu-id="a5e87-663">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-663">Property value</span></span>
<span data-ttu-id="a5e87-664">種類: [Mswebviewprocess](./webview/MSWebViewProcess.md)</span><span class="sxs-lookup"><span data-stu-id="a5e87-664">Type: [MSWebViewProcess](./webview/MSWebViewProcess.md)</span></span>


### <span data-ttu-id="a5e87-665">設定</span><span class="sxs-lookup"><span data-stu-id="a5e87-665">settings</span></span>

<span data-ttu-id="a5e87-666">**Webview**機能を有効または無効にするプロパティを含む[Mswebviewsettings](./webview/MSWebViewSettings.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-666">Gets a [MSWebViewSettings](./webview/MSWebViewSettings.md) object that contains properties to enable or disable **webview** features.</span></span>

<span data-ttu-id="a5e87-667">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a5e87-667">This property is read-only.</span></span>

```js
var settings = webview.settings;
webview.settings = settings;
```

#### <span data-ttu-id="a5e87-668">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-668">Property value</span></span>
<span data-ttu-id="a5e87-669">種類: [Mswebviewsettings](./webview/MSWebViewSettings.md)</span><span class="sxs-lookup"><span data-stu-id="a5e87-669">Type: [MSWebViewSettings](./webview/MSWebViewSettings.md)</span></span>

<span data-ttu-id="a5e87-670">**Webview**機能を有効または無効にするプロパティが含まれている[Mswebviewsettings](./webview/MSWebViewSettings.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a5e87-670">A [MSWebViewSettings](./webview/MSWebViewSettings.md) object that contains properties to enable or disable **webview** features.</span></span>

### <span data-ttu-id="a5e87-671">src</span><span class="sxs-lookup"><span data-stu-id="a5e87-671">src</span></span>

<span data-ttu-id="a5e87-672">**Webview**コントロールに表示される HTML コンテンツの Uniform resource IDENTIFIER (URI) ソースを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-672">Gets or sets the Uniform Resource Identifier (URI) source of the HTML content to display in the **webview** control.</span></span> 

```js
var src = webview.src;
webview.src = src;
```

#### <span data-ttu-id="a5e87-673">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-673">Property value</span></span>
<span data-ttu-id="a5e87-674">種類:**文字列**</span><span class="sxs-lookup"><span data-stu-id="a5e87-674">Type: **String**</span></span>

<span data-ttu-id="a5e87-675">**Webview**コントロールに表示される HTML コンテンツの URI ソース。</span><span class="sxs-lookup"><span data-stu-id="a5e87-675">The URI source of the HTML content to display in the **webview** control.</span></span> 


### <span data-ttu-id="a5e87-676">width</span><span class="sxs-lookup"><span data-stu-id="a5e87-676">width</span></span>

<span data-ttu-id="a5e87-677">**Webview**の幅を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a5e87-677">Gets or sets the width of the **webview**.</span></span>

```js
var width = webview.width;
webview.width = width;
```

#### <span data-ttu-id="a5e87-678">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="a5e87-678">Property value</span></span>
<span data-ttu-id="a5e87-679">種類:**数値**</span><span class="sxs-lookup"><span data-stu-id="a5e87-679">Type: **Number**</span></span>

<span data-ttu-id="a5e87-680">**Webview**の幅。</span><span class="sxs-lookup"><span data-stu-id="a5e87-680">The width of the **webview**.</span></span>
