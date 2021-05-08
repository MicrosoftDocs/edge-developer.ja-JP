---
description: Microsoft Edge WebView2 Chromium DevTools プロトコル パッケージを使用して WebView2 アプリで Chrome DevTools プロトコルをNuGetする方法
title: WebView2 で Chrome DevTools プロトコルを使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Chrome DevTools プロトコル
ms.openlocfilehash: 86846ee195406f78d5fd7c369f375ed1e359101a
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536585"
---
# <a name="use-chromium-devtools-protocol-in-webview2"></a>WebView2 で Chromium DevTools プロトコルを使用する  

[DevTools プロトコルChromium Api][GitHubChromedevtoolsDevtoolsProtocol]は、ユーザー ベースのブラウザーをインストルメント、検査、デバッグ、およびプロファイルChromium提供します。  DevTools Chromiumは、\(Chromium\) DevTools のMicrosoft Edge基盤です。  WebView2 Chromium実装されていない機能については、DevTools プロトコルの一覧を使用します。  DevTools プロトコルの機能Chromium詳細については[、「DevTools プロトコルChromium」に移動します][GitHubChromedevtoolsDevtoolsProtocol]。  

> [!CAUTION]
> WebView2 Microsoft Edgeは、DevTools プロトコルを維持またはChromiumサポートしていない。  DevTools Chromiumは、プロジェクトのオープン ソースによってChromiumされます。  
> 
> 将来の WebView2 プラットフォーム機能に関する提案を送信するには [、[WebView フィードバック][GithubMicrosoftedgeWebview2feedback] ] に移動して問題を提出します。  

WebView2 で Chromium DevTools プロトコル API を使用するには、次のいずれかのアクションを使用します。  

*   [Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]パッケージ \(.NET\) をインストールNuGet使用します。  
*   次のいずれかの方法を実行します。  
    *   .NET:  [CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString], [GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]  
    *   Win32 C/C++:  [CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod], [ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]  
    
## <a name="use-devtoolsprotocolhelper-preview"></a>Use DevToolsProtocolHelper (Preview)

> [!NOTE]
> [Microsoft.Web.WebView2.DevToolsProtocolExtension][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet現在テクニカル プレビュー中です。  プレビュー中は、実稼働アプリでのパッケージの使用を控える必要があります。

[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]は、Chromium DevTools プロトコル機能に簡単にアクセスできる WebView2 チームによって作成された NuGet パッケージです。  次の例では、WebView2 コントロールの DevTools プロトコルChromium位置情報機能を使用する方法について説明します。  同様のパターンに従って、他の DevTools プロトコル機能Chromium使用できます。  

## <a name="step-1-create-a-webpage-to-find-your-geolocation"></a>手順 1: Web ページを作成して位置情報を検索する  

位置情報を検索 `HTML file` するを作成するには、アクションに従って完了します。  

1.  \(Visual Studio Code IDE\) を開きます。  
1.  新しいファイルを `.html` 作成します。  
1.  次のコード スニペットを新しいファイルにコピーして貼り付 `.html` けます。  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <title>Geolocation Finder</title>
    </head>
    <body>
        <button id="display">Display Location</button>
        <div id="message"></div>
    </body>
    
    <script>
        const btn = document.getElementById('display');
        // Find the user location.
        btn.addEventListener('click', function () {
            navigator.geolocation.getCurrentPosition(onSuccess, onError);
        });
        
        // Update message to display the latitude and longitude coordinates.
        function onSuccess(position) {
            const {latitude, longitude} = position.coords;
            message.textContent = `Your location: (${latitude},${longitude})`;
        }
        
        function onError() {
            message.textContent = `Operation Failed`;
        }
    </script>
    </html>
    ```  
    
1.  ファイル名を `.html` 使用してファイルを保存します `geolocation.html` 。  
1.  Microsoft Edge を開きます。  
1.  `geolocation.html` ファイルを開きます。  
1.  緯度と経度の座標を表示するには、[表示場所] **ボタンを選択** します。  位置情報を確認して比較するには、座標をコピーして貼り付けます [https://www.bing.com/maps][BingMaps] 。  
    
    :::image type="complex" source="./media/geolocater-browser.png" alt-text="ユーザーの位置情報座標を表示するMicrosoft Edge" lightbox="./media/geolocater-browser.png":::
       ユーザーの位置情報座標を表示するMicrosoft Edge  
    :::image-end:::  
    
## <a name="step-2-display-geolocationhtml-in-a-webview2"></a>手順 2: WebView2 geolocation.html を表示する  

1.  WebView2 アプリを作成するには、次の開始ガイドまたは WebView2 サンプルのいずれかを使用します。  
    *   [WebView2 の使用を開始する方法 (Windows フォーム)][Webview2GettingstartedWinforms]  
    *   [WPF の WebView2 の概要][Webview2GettingstartedWpf]  
    *   [WebView2 サンプル][GithubMicrosoftedgeWebview2samples]  
        
1.  WebView2 コントロールの初期ナビゲーションをに設定します `geolocation.html` 。  
    
    ```csharp
    webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    ```  
    
1.  ファイルが `geolocation.html` WebView2 コントロール アプリに表示されるのを確認します。  
    
    :::image type="complex" source="./media/initial-geolocate.png" alt-text="WebView2 コントロール geolocater.html ファイルを表示する" lightbox="./media/initial-geolocate.png":::
       `geolocation.html`WebView2 コントロール アプリにファイルを表示する  
    :::image-end:::  
    
## <a name="step-3-install-the-devtoolsprotocolhelper-nuget-package"></a>手順 3: DevToolsProtocolHelper パッケージをインストールNuGetする  

ダウンロードNuGetを使用します `Microsoft.Web.WebView2.DevToolsProtocolExtension` 。  パッケージをインストールするには、次の操作を実行します。  

1.  [パッケージ**Project**  >  **参照NuGet管理する] を**  >  **選択します**。  
1.  `Microsoft.Web.WebView2.DevToolsProtocolExtension` **Microsoft.Web.WebView2.DevToolsProtocolExtension Install を入力して選択**  >  **します**。   
    
:::image type="complex" source="./media/cdpnuget.png" alt-text="Microsoft.Web.WebView2.DevToolsProtocolExtension がページに表示Visual Studio NuGet パッケージ マネージャー" lightbox="./media/cdpnuget.png":::
   **Microsoft.Web.WebView2.DevToolsProtocolExtension**がページに表示Visual Studio NuGet パッケージ マネージャー  
:::image-end:::  

## <a name="step-4-use-devtools-protocol-helper"></a>手順 4: DevTools プロトコル ヘルパーを使用する  

1.  名前空間を `DevToolsProtocolExtension` プロジェクトに追加します。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    using Microsoft.Web.WebView2.Core.DevToolsProtocolExtension;
    ```  
    
1.  オブジェクトをインスタンス `DevToolsProtocolHelper` 化し、に移動します `geolocation.html` 。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webView.CoreWebView2.GetDevToolsProtocolHelper(); 
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    }
    ```  
    
1.  [setGeoLocationOverrideAsync メソッドを実行][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]します。  詳細については [、setGeolocationOverride に移動します][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webview.CoreWebView2.GetDevToolsProtocolHelper();
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
        
        // Latitude and longitude for Paris, France.
        double latitude = 48.857024082572565;  
        double longitude = 2.3161581601457386;  
        double accuracy = 1;
        await helper.Emulation.setGeolocationOverrideAsync(latitude, longitude, accuracy);
        
    }
    ```  
    
1.  アプリを実行します。  
1.  パリ、フランスの座標を表示するには、[表示場所] **ボタンを選択** します。  
    
    :::image type="complex" source="./media/finallocation-cdp.png" alt-text="パリの座標.html WebView2 コントロールにファイルを表示する" lightbox="./media/finallocation-cdp.png":::
       パリの `.html` 座標を使用して WebView2 コントロールにファイルを表示する  
    :::image-end:::  
    
## <a name="file-a-chromium-devtools-protocol-bug"></a>DevTools Chromiumのバグをファイルする  

WebView2 チームは、DevTools プロトコルChromium所有しています。  

> [!IMPORTANT]
> フィードバックとバグを問題Chromiumに直接送信します。  

DevTools プロトコルのChromiumまたは問題をファイルするには、次のアクションを実行します。  

1.  バグ レポート [をファイルします][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]。  
1.  [[WebView フィードバック] に移動し][GithubMicrosoftedgeWebview2feedback]、新しい問題を開きます。  
    
## <a name="see-also"></a>関連項目  

*   [WebView2 サンプル][GithubMicrosoftedgeWebview2samples]  
    
 <!-- links -->  

[Webview2GettingstartedWinforms]: /microsoft-edge/webview2/gettingstarted/winforms "WebView2 の使用を開始する方法 (Windows フォーム |Microsoft Docs"  
[Webview2GettingstartedWpf]: /microsoft-edge/webview2/gettingstarted/wpf "WPF の WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2.getdevtoolsprotocoleventreceiver?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2.GetDevToolsProtocolEventReceiver(String) メソッドの|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString]: /dotnet/api/microsoft.web.webview2.core.corewebview2.calldevtoolsprotocolmethodasync?view=webview2-dotnet-1.0.774.44&preserve-view=true#Microsoft_Web_WebView2_Core_CoreWebView2_CallDevToolsProtocolMethodAsync_System_String_System_String_ "CoreWebView2.CallDevToolsProtocolMethodAsync(String, String) メソッドの|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-1.0.774.44&preserve-view=true#calldevtoolsprotocolmethod "CallDevToolsProtocolMethod - インターフェイス ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-1.0.774.44&preserve-view=true "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  

[BingMaps]: https://www.bing.com/maps "Bing地図"  

[GitHubChromedevtoolsDevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコル |GitHub"  
[GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]: https://chromedevtools.github.io/devtools-protocol/tot/Emulation/#method-setGeolocationOverride "エミュレーション.setGeolocationOverride - Chrome DevTools プロトコル |GitHub"  

[GithubMicrosoftedgeWebview2feedback]: https://github.com/MicrosoftEdge/WebView2Feedback "WebView フィードバック |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 のサンプル |GitHub"  

[ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]: https://bugs.chromium.org/p/chromium/issues/entry?components=Platform%3EDevTools%3EPlatform "バグ レポート|Chromiumバグ"  

[NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]: https://www.nuget.org/packages/Microsoft.Web.WebView2.DevToolsProtocolExtension "Microsoft.Web.WebView2.DevToolsProtocolExtension |NuGetQA ギャラリー"  
